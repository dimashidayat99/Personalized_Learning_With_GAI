# Generative Adversarial Network (GAN)

<p align="middle">
<img src=https://github.com/dimashidayat99/Personalized_Learning_With_GAI/blob/main/model/GAN/framework/GAN_framework.png>
</p>
<p align="middle">
    <em>GAN Model Framework.</em>
</p>

# Data Preparation

The GAN model takes only user entity data as input. To obtain the historical course sequences from the user entity, the data was prepared based on several steps namely data
sampling, feature selection, data transformation, data encoding, and data splitting.

1. Sampling: The preparation begins with data sampling where only five to ten courses in the sequence and 30% of the data was selected as a sample. The filtering and sampling of the data in such a way help to reduce the huge number volume and size of data which helps to reduce the complexity of data pre-processing and the modelling. The number of courses was reduced from 706 courses in the dataset to 660 courses in the sample data.

2. Feature Selection & Data Transformation: The specific feature was selected manually whereas in this case, the selected feature was the course order feature. The length course sequence will vary from five to ten courses, to make a new dataframe, the zero padding technique was applied to make sure the length of the course sequence will be the same in all instances. The zero was left padded into the data so that the final course in the sequence would be in the final position of the sequence. The fixed size of the input is necessary because the artificial neural network requires a fixed size of input data. 

3. Data Encoding: The zero-padded data was encoded using label encoder where the course ID was transformed into a numerical value. The data was encoded a second time by using one-hot encoding for better data representation. 

4. Data Splitting: The data was split into X and Y components where X component will be the course sequence from the first course until the penultimate course in the course sequences and Y is the final course in the course sequence. Then, the data was split into train and test data with 80% of the data will become train data while 20% of the data will become test data.

Overall, the final result of data preparation is one hot encoded course sequence data for ten-course sequences for X and Y components for training and testing data. Where the X component will have 5949 features and the Y component will have 661 features which represent one hot encoded data for nine course sequences and one hot encoded data for final courses respectively.

# Modelling
The conventional GAN model contains two main components which are the generator component and discriminator component. Each component will have different architectures of neural networks. 

## Generator
The generator component takes the X component of training data of historical course sequences as input. The generator component consists of four layers namely which are one input layer, two hidden layers, and one output layer (predictive layer).
  
1. Input Layer: The neurons of the input layer will follow the input size of training data. In this case, the input layer will have 5949 neurons.
    
2. Hidden Layers: Each hidden layers were created using a dense layer where the first hidden layer consists of 50 neurons and the second hidden layer consist of 25 neurons. Both hidden layers will use the Rectified Linear Unit (ReLU) as an activation function. The small number of neurons is selected to avoid the high training time of the model since there is a total of six models will be created.
    
3. Output Layer: The output layer was created using a dense layer that has 661 neurons with a softmax activation function. The softmax activation function will provide the output of the generator with a probability distribution over all courses.
  
4. Model Complication: At this point, the generator output which is the predicted course can be seen as a probability distribution of courses. The generator model was compiled with Adam optimizer and the loss metric of mean absolute error.

The output from the generator was combined with the X component of training data of historical sequence forming generated course sequences. On the other hand, the X component of training data and the Y component of training data also will be combined forming the actual course sequences. Both generated course sequences and actual course sequences will become input in the discriminator component.

## Discriminator

The discriminator network also consists of four layers which are one input layer, two hidden layers, and one output layer.
  
1. Input Layer: The input layer will have 6610 neurons since the input of the discriminators is the complete course sequences from combined course sequences as mentioned before.
  
2. Hidden Layers: The hidden layer was created based on the dense layer where the first hidden layer consists of 25 neurons and the second hidden layer consists of 50 neurons. Both hidden layers will use the ReLU activation function. A similar reason is used for having a small number of neurons which is to avoid high training time.
  
3. Output Layer: The output layer was created using a dense layer that has one neuron with a sigmoid activation function. Using the sigmoid activation function, the output from the discriminator will return any floating-point number to predict the probability of binary variables which in this case, the binary variables are real or fake.
  
4. Model Compilation: The discriminator model will be compiled with Adam optimizer, loss function of binary cross-entropy, and metrics of mean absolute error.

Both generated course sequences and actual course sequences become the input of the discriminator and the discriminator will discriminate whether the generated course sequences are real or fake.

## The GAN Model

Both the generator and discriminator network were combined forming the GAN model. Note that the output from the generator requires to be integrated with X component of the training data. Therefore, a preprocessing layer was created between the generator network and the discriminator network. The pre-processing layer is created by using the Lambda layer which helps to concatenate the X component of training data and generated data from generator output. The GAN model was compiled with Adam optimizer and loss function of mean absolute error. 

### Working Princple

Both components of GAN which are the generator and discriminator were trained alternatively for 50 epochs. The overall process of the GAN model starts from the generator network and takes input from the X component to produce a probability distribution of the final course across all courses. The X component of one hot encoded course sequence training data will be combined with the generated final course probability to form the generated course sequences. On the other hand, the X component of training data will be combined with the Y component of training data to form actual course sequences. Then, the discriminator network will take both generated and actual course sequence data as input. The discriminator will evaluate the rationality of the generated course sequences based on actual course sequences. The evaluation results will be sent back to the generator to escort and lead the learning of the following round. The discriminator will be updated by improving the discriminative ability and capacity based on a comparison of generated course sequences and actual course sequences. In this case, the generator and multiple discriminators will play the min-max game where the generator and multiple discriminators compete with each other to improve and outperform each other in a mutual reinforcement way. After training is completed, the X component test data will be input into the GAN model to predict the final courses. The courses with the five highest probability scores were chosen. The Y component of the actual final course and the top five predicted courses were evaluated based on the performance metrics.


