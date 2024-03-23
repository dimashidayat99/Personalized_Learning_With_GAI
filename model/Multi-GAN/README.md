# Multiple Generative Adversarial Network (Multi-GAN)

<p align="middle">
<img src=https://github.com/dimashidayat99/Personalized_Learning_With_GAI/blob/main/model/Multi-GAN/framework/Multi-GAN_framework.png>
</p>
<p align="middle">
    <em>Multi-GAN Model Framework.</em>
</p>

# Data Preparation

The process of data preparation for the Multi-GAN model is almost similar to the process
of data preparation of the GAN model where the data was prepared based on several steps namely data sampling, feature selection, data transformation, data encoding, data scaling, and data splitting.

1. Sampling: The user entity underwent a sampling process by only considering 30% of course sequences of five to ten courses.
  
2. Feature Selection: The data went through feature selection where only the course order feature was selected.

3. Data Transformation: The data was transformed by using the zero padding technique.

4. Data Encoding: The zero-padded data was encoded by using a label encoder. 

5. Data Scaling: The data was scaled by using a min max scaler.

6. Data Splitting: The data was split into X and Y components where X component will be the first nine course sequences and Y is the final course in the course sequence. Then, the data was split into train and test data with 80% of the data will become train data while 20% of the data will become test data.
   
Overall, the final result of data preparation is scaled data which have a floating-point number between zero to one for ten-course sequences for X and Y components for training and testing data. Due to the absence of one hot encoding process, the X component will have nine features indicating nine-course sequences and the Y component will have one feature indicating one final course.

# Modelling
Since there is an absence of one hot encoding in the data preparation of the Multi-GAN model. The architecture of the model will be a bit different. Since the processed data have only ten features in total representing the course sequences, the architecture of the generator and discriminator network in the Multi-GAN model is simpler compared to the generator and discriminator network in the GAN model. 

## Generator
The generator component has only three layers which are one input layer, one hidden and one output layer.

1. Input Layer: The input layer consists of nine neurons that represent the features of input data which in this case is X component of processed data.

2. Hidden Layer: The hidden layer consists of 20 neurons with a ReLU activation function. Since the input data is less complex, a smaller number of neurons should be enough to give a proper prediction.

3. Output Layer: The output layer consists of one neuron which represents the one number of feature (final course) of the Y component of processed data. The activation function used in the output layer is the sigmoid activation function which gives the output in the form of any floating-point number in the range of zero to one representing the scaled value of the predicted final course.

The prediction of the final course will be similar to multi-label classification. The generator model is compiled with Adam optimizer and the loss metric of mean absolute error.

## Discriminator

The discriminator network also consists of four layers which are one input layer, two hidden layers, and one output layer.

Input Layer: The input layer have 10 neurons since the input of the discriminators is the complete course sequences from combined X and Y component.

Hidden Layers: The hidden layer was created based on the dense layer where the first hidden layer consists of 25 neurons and the second hidden layer consists of 50 neurons. Both hidden layers use the ReLU activation function.

Output Layer: The output layer was created using a dense layer that has one neuron with a sigmoid activation function. Using the sigmoid activation function, the output from the discriminator will return any floating-point number to predict the probability of binary variables which in this case, the binary variables are real or fake.

Model Compilation: The discriminator model was compiled with Adam optimizer, loss function of binary cross-entropy, and metrics of mean absolute error.

## Multi-GAN Model

Both the generator and discriminator network were combined forming the GAN model. The GAN model was compiled with Adam optimizer and loss function of mean absolute error. Both components of GAN which are the generator and discriminator were trained alternatively for 100 epochs. The GAN architecture in the Multi-GAN model predicts only one recommended course. To obtain more than one, multiple GAN architecture is required. In the Multi-GAN model, there are five GAN architectures to predict five recommended courses. In general, multiple GAN architectures will form a recommendation engine (model) whereas in this study, five GAN architectures will form a recommendation engine to predict five recommended courses. The code of whole process can be found in the file of ["Multi-GAN_Educational_Recommendation_System"](https://github.com/dimashidayat99/Personalized_Learning_With_GAI/blob/main/model/Multi-GAN/code/Multi-GAN_Educational_Recommendation_System.ipynb) in the `code` [directory](https://github.com/dimashidayat99/Personalized_Learning_With_GAI/blob/main/model/Multi-GAN/code).
