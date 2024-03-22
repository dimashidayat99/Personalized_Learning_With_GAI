# Multi-Discriminators Generative Adversarial Network (MDGAN)
# Data Preparation

The MDGAN model require three different data which are user entity data, school course relation data and teacher course relation data. Each data will be processed differently. 

1. User Entity: The data preparation process of user entity data in the MDGAN model will be exactly same as in data preparation process of user entity data in the GAN. Where the data preparation of user entity begins with data sampling which take 30% of courses sequences of five to ten sequences. Then, fature of the data was selected to only courses sequences feature. Next, the data was transformed using zero padding techniques. After that, the data was encoded by using label encoding. After the label encoding process, the encoded course sequences data was copied to be used in the data preparation for school course relation data and teacher course relation data. 

2. School-Course Relation: The data preparation for school course relation data begins with data transformation where the data was transformed into dictionary with key and value of course and school respectively. The dictionary of course school was encoded by using label encoding. By using the copied data of encoded course sequences data, the course ID in the encoded course sequences data was encoded to encoded school ID from the encoded course-school dictionary forming course-school sequences data. The course-school sequences data in general consist of schools sequences based on courses sequences. In simple word, course-school sequences data was formed by changing value of course ID in the courses sequences data with the school ID based on the course-school dictionary.
  
3. Teacher-Course Relation: For the teacher course relation data, the data preparation process will be exactly the same as data preparation process of school course relation data where the teacher course relation data was transformed and encoded forming encoded course teacher dictionary. Then, the course ID in the copied data of encoded course sequences was changed to teacher ID. As now, the output of data preparation process for user entity data, school course relation data and teacher course relation data will be in the form of encoded courses sequences data, encoded course-school sequences data and course-teacher sequences data respectively.

All these data were encoded second time by using one hot encoding for better data representation. Then, all three data were split into X and Y component where X component will be first nine course and Y component will be the final course (tenth course). Finally, all three data were split into train and test data with 80% of the data will become train data while 20% of the data will become test data

# Modelling
The MDGAN architecture consist of generator component and multiple discriminators component. 

## Generator
The generator network consist of three layer which are one input layer, one hidden layer and one output layer. 

1. Input Layer: The input layer was created using dense layer which consist of nine neurons represent nine features of input data of courses sequences.

2. Hidden Layers: The hidden layer also created by using dense layer which consist of ten neurons with linear activation layer. Since the architecture of MDGAN is complex, only small number of neuron will be used to avoid high training time.

3. Output Layer: The output layer is also created by using dense layer with one neuron and softmax activation function.

4. Model Complication: The generator model is compiled with loss function of mean absolute error and optimization with adam optimizer. 

## Discriminators
The MDGAN model in this study will use three discriminators. All the three discriminator used the same neural network architecture. The discriminator architecture consist of four layer which are one input layer, two hidden layer and one output layer. 

1. Input Layer: The input layer was created by using dense layer with ten neurons which represent the ten features of course sequences data.

2. The both hidden layer will also use dense layer with 25 and 50 neurons for first hidden layer and second hidden layer respectively. Both hidden layer use ReLU activation function.

3. Output Layer: The output layer was created using a dense layer that has one neuron with a sigmoid activation function. 

4. Model Compilation: The discriminator model will be compiled with loss function of binary cross-entropy, metrics of mean absolute error and optimization of adam
optimizer.

## The MDGAN Model

The generator component and three discriminator components will be combine together
forming Multiple Discriminator GAN (MDGAN). Similarly, the output from generator was
combined with the X component of train data which require a lambda layer to concatenate
the data forming generated course sequence. The generated course sequence and real
course sequence will become input to discriminator one which discriminate the generated
course sequence data with real course sequence data. The generated course sequence data
will require other some preparation to become input for discriminator two and three. In
this case, some pre-processing layer by using lambda layer were developed to processed
the generated course sequence data. For discriminator two, data will be processed by six pre-processing layer which for inverse scaling which transformed the scaled data become
unscaled data; data type transformation which transform data type from float to integer;
course-school encoding which encode the data to change course ID to school ID; datatype
transformation which change the data type from integer to float and concatenate the X
component of course-school sequence data with the processed generated data to form
generated data in the form of course-school sequence. Similar principle, the generated
course-school sequence data together with real course-school sequence data will become
input to discriminator two. The pre-processing layer was built for course-teacher sequence
data. Similarly, the generated course-teacher sequence data will become input along with
real course-teacher sequence data. The output from discriminator was concatenate using
concatenate layer and it was connected to the final layer of dense layer with one neuron.
The MDGAN was compiled by using loss function of binary crossentropy and adam
optimizer. The model was run for only 10 epoch due to time consuming.
