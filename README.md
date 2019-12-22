# musk-molecules-classification
Classifiacation of molecules as MUSK or non-MUSK using machine learning model.


DATASET DETAILS AND PREPROCESSING :

   The dataset contains 6598 rows and 170 columns where each row is an instance of a molecule and its features . Each molecules has          
169 attributes where each attribute is described as –

   Attribute 1 – ID
   Attribute 2 – molecule name
   Attribute 3 – conformation name
   Attribute 4 to 169 – f1 to f166 (features of each molecules)
   Attribute 170  –  Class (1 for Musk and 0 for non Musk)

So before selecting the model and architecture we need to preprocess the data and convert it to X features and Y labels which can
be provided to the model as input. So I took the 4 to 169 columns as X features and 170th column as Y label. The features here are
in integer type so I converted the features into float type. The features are merely in the range of 360 to -360, so normalization
is not required. 

MODEL DESCRIPTION :

   After preprocessing the data and extracting features and labels from it I distributed the data into training and cross
validation data (randomly 0.2 is selected for cross validation).
Now finally the model selection can be done. So I tested different architectures and algorithms such as ANN,CNN and RNN but the
maximum and efficiency is gained while using the simple artificial neural network architecture. This architecture consists of 8
layers including the input and output layers and 6 hidden layers. The layer details are mentioned below – 

_________________________________________________________________
Layer (type)                 Output Shape              Param #   
=================================================================
input_7 (InputLayer)         (None, 166)               0         
_________________________________________________________________
Hidden_Layer_1 (Dense)       (None, 600)               100200    
_________________________________________________________________
Hidden_Layer_2 (Dense)       (None, 500)               300500    
_________________________________________________________________
Hidden_Layer_3 (Dense)       (None, 500)               250500    
_________________________________________________________________
Hidden_Layer_4 (Dense)       (None, 500)               250500    
_________________________________________________________________
Hidden_Layer_5 (Dense)       (None, 300)               150300    
_________________________________________________________________
Hidden_Layer_6 (Dense)       (None, 50)                15050     
_________________________________________________________________
Output_Layer (Dense)         (None, 1)                 51        
=================================================================
Total params: 1,067,101
Trainable params: 1,067,101
Non-trainable params: 0
_________________________________________________________________


   The reason behind choosing this architecture because this gives a good accuracy over the data and is very computationally simple and efficient as compared to CNN and RNN. While training the model I have used the following settings –

   Learning rate = 0.0000001
   optimizer = Adam
   loss function = binary cross entropy
   epochs = 20
   batch size = 1000

PERFORMANCE MEASURES :

   After using the artificial neural network model using the above mention settings, I have obtained the following performance measurements –

   Training accuracy –  0.9930
   Training loss –  0.0191
   validation accuracy –  0.9886
   Validation loss -  0.0343

________________________________________________________________________________________________________________________________
