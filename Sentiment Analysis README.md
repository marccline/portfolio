#### INTRODUCTION
This project uses Neural Network to classify book reviews as either positive or negative. The following was done: 
1. Get the dataset
2. Preprocessing the Data
3. Build the Model
4. Train the model
5. Test the Model
6. Predict Something

This project uses a small portion of the Multi-Domain Sentiment Dataset, which contains product reviews from Amazon. 

#### GET AND EXPLORE DATASET
Originally there were two test files, one that holds all the positive reviews, and the other holding all the negative reviews.

The mean review size of the dataset is 24.676519799219186 characters per review. Standard deviation of dataset is : 11.284051928842775. The number of unique words in the dataset is 1676 words.

#### PRE-PROCESSING
First we need to make all reviews the same length, then padd the training sequences. The training/test split is 80/20.

#### BUILD AND TUNE MODEL
###### The Model
The project utilizes the Keras sequential model with the following:

Embedding layer (input_dim = 5000, output_dim = 20, input_length = 4). After some tweaking, the output dimension of 20 was found to be optimal.
SpacialDropout Layer (0.2)
BatchNormalization
LSTM Layer (32)
Dense Layer
###### Train Model
Batch sizes of 10, 25, 50, 100 were used to train the model, (epochs=5), with the following results:

Batch size = 10 : val_accuracy = 0.6017
Batch size = 25 : val_accuracy = 0.6100
Batch size = 50 : val_accuracy = 0.6184
Batch size = 100 : val_accuracy = 0.6100
Batch size 50 gives the most accurate reslt.

###### Model Summary
The model is not particularly accurate.

precision    recall  f1-score   support

       0       0.64      0.50      0.56       178
       1       0.59      0.72      0.65       181

accuracy                           0.61       359
macro avg      0.61      0.61      0.60       359
weighted avg   0.61      0.61      0.61       359

###### Model Accuracy
The training data are most accurate at 4 epochs at around 0.67, while in constrast, the test data is most accurate at epoch = 2.

###### Model Loss
The model loss for the test data is higher than the training data, both being high. As the number of epochs increase, the model loss for the training data is consistent at around 0.58. The model loss for te test data consistently increases slighly from around 0.61-0.62.

