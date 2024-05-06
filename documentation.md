# CS470 Final Project

## Overview
The requirements for this project were to implement three different algorithms used for machine learning:
* Naive Bayes
* K Nearest Neighbors
* Logistic Regression
The program is written using the Python language. The algorithms needed to be implemented from scratch. No machine learning libraries are to be used for computation.

## Implementations
### Naive Bayes
For this implementation, I separated the process between calculating the likelihood of each attribute and performing the test on the dataset. For the likelihood part, I first calculated the total number of emails that were spam and not spam for each attribute. Then I summed up the indexes of the attribute column that didn't contain 0 for a value and then calculated the probability of it being an attribute of spam and not spam and returned those two values. The function is used on every iterated attribute from the dataset.
For the classifier, I iterated through the rows of the test set and calculated the logarithm probability of the indexed attribute being spam. The probability of the email being spam and the probability of the email being not spam are calculated and the higher probability gets predicted.

### K Nearest Neighbors
This algorithm was split into two functions. Euclidean Distance and Prediction. The distance implementation is just the Python version of the Euclidean distance function. it sums the squared difference between two points and square roots the sum.
The training function iterates through the testing set of emails and first calculates the Euclidean distance between each attribute in the email. Then the distances are sorted and the nearest neighbors are indexed to epsilon. The prediction is then calculated and appended to the results.

### Logistic Regression
This function is split into five parts. Sigmoid calculation, cost calculation, gradient descent, training, and prediction.
Sigmoid just returns 1 divided by 1 added to the exponent of the negative parameter 'z'.
The cost function takes the length of y, calculated sigmoid, and returns -1 over the length of y multiplied by the sum of y multiplied by the log of sigmoid plus 1 subtracted from y multiplied by the log of 1 minus sigmoid.
Gradient Descent iterates through a given amount where the sigmoid, gradient, theta, and cost are calculated and then the cost is appended to a list.
The training function calculates the intercept for the conceptual plot and then concatenates the intercept with x_train. Theta is calculated and gradient descent is then performed.
The prediction function calculates the intercept of the test dataset, then concatenates it with the set itself, and returns its predictions.

## Performance
For performance, I have only been able to get the Naive Bayes algorithm to work properly. My accuracy is 58% with 2 false positives and 919 accurate positive predictions. I was unable to implement threading for K nearest Neighbors and in turn the program takes too much time to process as it is running sequentially and I can't assess the results. For Logistic Regression, I am having problems with the correct indexing and how it interacts with the logic of my code, and in turn I haven't been able to gather complete results for assessment.
