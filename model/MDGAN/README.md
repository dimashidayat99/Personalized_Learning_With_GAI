# Multi-Discriminators Generative Adversarial Network (MDGAN)

<p align="middle">
<img src=https://github.com/dimashidayat99/Personalized_Learning_With_GAI/blob/main/model/MDGAN/framework/MDGAN_framework.png>
</p>
<p align="middle">
    <em>MDGAN Model Framework.</em>
</p>

# Data Preparation

The MDGAN model requires three different data which are user entity data, school-course relation data, and teacher-course relation data. Each data will be processed differently. 

1. User Entity: The data preparation process of user entity data in the MDGAN model will be the same as in the data preparation process of user entity data in the GAN. Where the data preparation of the user entity begins with data sampling which takes 30% of course sequences of five to ten sequences. Then, the feature of the course order was selected. Next, the data was transformed using zero padding techniques. After that, the data was encoded by using label encoding. After the label encoding process, the encoded course sequences data was copied to be used in the data preparation for school-course relation data and teacher-course relation data. 

2. School-Course Relation: The data preparation for school course relation data begins with data transformation where the data was transformed into a dictionary with the keys and values of course ID and school ID respectively. The dictionary of course-school was encoded by using label encoding. By using the copied data of encoded course sequences data, the course ID in the course sequences data (copied data) was changed to school ID by using the encoded course-school dictionary forming course-school sequences data. In simple words, course-school sequences data was formed by changing the value of the course ID in the course sequences data with the value of the school ID based on the course-school dictionary.
  
3. Teacher-Course Relation: For the teacher-course relation data, the data preparation process will be the same as the data preparation process of school course relation data where the teacher-course relation data was transformed and encoded forming an encoded course-teacher dictionary. Then, the course ID in the copied data of encoded course sequences was changed to the teacher ID.

As of now, the output of the data preparation process for user entity data, school course relation data and teacher course relation data is in the form of encoded course sequences data, encoded course-school sequences data, and course-teacher sequences data respectively. All these data were encoded a second time by using one-hot encoding for better data representation. Then, all three data were split into X and Y components where the X component will be the first nine courses and the Y component is the final course (tenth course). Finally, all three data were split into train and test data with 80% of the data will become train data while 20% of the data will become test data

# Modelling
The MDGAN architecture consist of generator component and multiple discriminators component. 

## Generator
The generator network consists of three layers which are one input layer, three hidden layers, and one output layer. 

1. Input Layer: The input layer was created using a dense layer that consists of nine neurons representing nine features of input data of course sequences.

2. Hidden Layers: The hidden layer was created by using a dense layer that consists of ten neurons with a linear activation layer. The first two hidden layers were connected to batch normalization to normalize the activations of the previous layer, which can help with training by reducing internal covariate shifts and improving gradient flow. Since the architecture of MDGAN is complex, only a small number of neurons was used to avoid high training time. 

3. Output Layer: The output layer was created by using a dense layer with one neuron and softmax activation function.

4. Model Complication: The generator model was compiled with loss function of mean absolute error and optimization with Adam optimizer. 

## Discriminators
The MDGAN model in this study uses three discriminators. All three discriminators use the same neural network architecture. The discriminator architecture consists of four layers which are one input layer, two hidden layers, and one output layer. 

1. Input Layer: The input layer was created by using a dense layer with ten neurons which represent the ten features of course sequences data.

2. Hidden Layers: Both hidden layers were created using a dense layer with 25 and 50 neurons for the first hidden layer and second hidden layer respectively. Both hidden layers use the ReLU activation function. The first dense layer was connected to the dropout layer which helps prevent overfitting by reducing co-adaptation of neurons. Each hidden layer is connected to batch normalization to normalize the activations of the previous layer, which can help with training by reducing internal covariate shifts and improving gradient flow.

3. Output Layer: The output layer was created using a dense layer that has one neuron with a sigmoid activation function. 

4. Model Compilation: The discriminator model was compiled with the loss function of binary cross-entropy, metrics of mean absolute error, and optimization of Adam.
optimizer.

## The MDGAN Model

The generator component and three discriminator components were combined together forming Multiple Discriminators GAN (MDGAN). The output from the generator was combined with the X component of train data which requires a lambda layer to concatenate the data forming the generated course sequence. 

The generated course sequence and actual course sequence become the input to discriminator one which discriminates the generated course sequence data with the actual course sequence data. The generated course sequence data require some preparation to become input for discriminators two and three. In this case, some preprocessing layers by using the lambda layer were developed to process the generated course sequence data. 

For discriminator two, the data was processed by two preprocessing layers for transferring the cumulative probability of courses to schools and concatenating the X component of course-school sequence data with the processed generated data to form generated data in the form of course-school sequence. The generated course-school sequence data together with actual course-school sequence data become input to discriminator two.

For discriminatory three, similar to discriminator two, the data was processed by two preprocessing layers for transferring the cumulative probability of courses to teachers and concatenating the X component of course-teacher sequence data with the processed generated data to form generated data in the form of course-teacher sequence. Similarly, the generated course-teacher sequence data becomes input along with actual course-teacher sequence data. 

The output from discriminators was concatenated using the concatenate layer and it was connected to the final layer of the dense layer with one neuron of sigmoid activation function. The MDGAN was compiled by using the loss function of binary cross-entropy and Adam optimizer. The model was trained for 50 epochs. After training was completed, the X component test data was input into the MDGAN model to predict the final courses. The courses with the five highest probability scores were chosen. The Y component of the actual final course and the top five predicted courses were evaluated based on the performance metrics. The code of whole process can be found in the file of ["MDGAN_Educational_Recommendation_System"](https://github.com/dimashidayat99/Personalized_Learning_With_GAI/blob/main/model/MDGAN/code/MDGAN_Educational_Recommendation_System.ipynb) in the `code` [directory](https://github.com/dimashidayat99/Personalized_Learning_With_GAI/blob/main/model/MDGAN/code).

