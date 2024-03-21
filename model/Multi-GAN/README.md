# Multiple Generative Adversarial Network (Multi-GAN)
# Data Preparation

The process of data preparation for Multi-GAN model is almost similar with the process
of data preparation of GAN model where the user entity will undergo sampling process by
only consider 30% of course sequences of five to ten course. Then, the data will undergo
feature selection where only course order feature will be selected. Next, the data will be
transform by using zero padding technique. The zero padded data will be encoded by using
label encoder. The different of data preparation between MUlti-GAN model and GAN
model is start from label encoded zero padded data where in GAN model, the data will
undergo another data encoding. Hoever, in this model, the data will undergo data scaling
process by using min max scaler. Finally, the data splitting process will be remain the
same. Overall, the final result of data preparation is scaled data which have floating-point
number between zero to one for ten course sequences for X and Y component for training
and testing data. Due to absent of one hot encoding process, the X component will have
nine features indicating nine courses sequences and Y component will have one feature
indicating one final course.

# Modelling
Since there is absent of one hot encoding in the data preparation of Multi-GAN model.
The architecture of the model will be a bit different. Since the processed data have only ten
features in total which representing the courses sequences, the architecture of generator and discriminator network in Multi-GAN model is simpler compared to generator and
discriminator network in GAN model. The generator component have only three layer
which are one input layer, one hidden and one output layer. The input layer consist of nine
neurons which represent the features of input data which in this case is X component of
processed data. The hidden layer consist of 20 neurons with RelU activation function.
Since the input data is less complex, smaller number of neurons should be enough to give
proper prediction. The output layer consist of one neuron which represent the one number
of feature (final course) of Y component of processed data. The activation function used
in the output layer is sigmoid activation function which give the output in the form of any
floating-point number in the range of zero to one representing the scaled value of predicted
final course. In this case, the prediction of final course will be similar as multi-label
classification. The generator model is compiled with adam optimizer and the loss metric
of mean absolute error.

The architecture of discriminator network in Multi-GAN model is similar with the
architecture of discriminator network except for the number of neurons in the input layer
where the number of neurons in input layer is set to be ten which represent the length of
course sequence in the processed data. Except from the number of neurons in the input
layer, the other parameters of the model will be similar with GAN model such as model
compilation, loss function, optimizer, additional pre-processing layer and number of epoch. The GAN architecture in Multi-GAN model predict only one recommended course. In
order to obtained more than one, multiple GAN architecture is required. In Multi-GAN
model, there are five GAN architecture to predict five recommended course. In general,
multiple GAN architecture will form a recommendation engine (model) where in this study,
five GAN architecture will form a recommendation engine to predict five recommended
course. 
