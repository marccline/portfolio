# IMAGE PROCESSING
#### INTRODUCTION
The MNIST database of handwritten digits has a training set of 60,000 examples, and a test set of 10,000 examples. It is a subset of a larger set available from NIST. The digits have been size-normalised and centred in a fixed-size image.

This project uses and compares two machine learning algorithms, Random Forest and Bagging. 

#### -1- Random Forest
RANDOM FOREST was chosen as the decorrelating of trees results in the reduction of variance, making the average of the resulting trees more reliable.
MAX_DEPTH parameter was chosen. Max_depth is defined as the longest path between the root node and the leaf node, and we can set a limit up to what depth we want every tree in the random forest to grow.
As per the graph below, max_depth = 8 is an appropriate value as the curve is starting to flatten out here.
Confusion Matrix: The model performed relatively accurately (0.9226740310446624). This can be seen by the large numbers on the diagonal with much smaller values everywhere else. The number 9 struggled the most, misclassifying the number 4 66 times, 7 40 times, and 8 27 times. The number 8 performed second worst with regards to overall misclassification (111), while number 7 misclassified number 9 31 times, and the number 2 misclassified the number 7 23 times.
Accuracy: 0.9702885439481954
precision: 0.9702885439481954
recall: 0.9702885439481954
fscore: 0.9702885439481954

#### -2- Bagging
Bagging helps in the reduction of variance, hence eliminating the overfitting.
Max_samples parameter chosen. This determines what fraction of the original dataset is given to any individual tree. We want to ascertain whether we can allocate a lesser fraction of bootstrapped data to each decision tree. As a result, the training time of the Random Forest model will be reduced drastically.
Attempt to use the GridSearchCV module to ascertain the best max_samples value was unsuccessful (my computer not powerful enough to process), so the value was attained manually (0.3 returning the highest accuracy value):

max_samples = 0.1: Accuracy ensemble: 0.9272450242834016 max_samples = 0.3: Accuracy ensemble: 0.9353394914770022 max_samples = 0.5: Accuracy ensemble: 0.9320064755737549 max_samples = 0.7: Accuracy ensemble: 0.932196933625369 max_samples = 0.9: Accuracy ensemble: 0.9276259403866298

Confusion Matrix: The model performed relatively accurately (Accuracy=0.9353394914770022). This can be seen by the large numbers on the diagonal with much smaller values everywhere else. The number 9 struggled the most, misclassifying the number 4 51 times, 7 31 times, and 8 26 times. The number 5 performed second worst with regards to overall misclassification (82).
Accuracy: 0.9353394914770022
precision: 0.9353394914770022
recall: 0.9353394914770022
fscore: 0.9353394914770022

#### Findings
The Confusion Matrix of the Bagging model performed better than the one of the Random Forest model. However, the f-score value was higher for random forest (0.9702885439481954 vs 0.9353394914770022), thus indicating that the random forest performed better than the bagging model.

