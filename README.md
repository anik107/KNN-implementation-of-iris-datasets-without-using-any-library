![0_NHgarBuqh9-a-3LV](https://user-images.githubusercontent.com/55916366/161840775-10861e36-f9d6-452a-9e32-3dfa2d07ed5d.png)
K-Nearest Neighbours (KNN) is definatley one of my favourite Algorithms in Machine Learning because it is just so intuitive and simple to understand and yet an essential algorithm to study.

So let’s start with the implementation of KNN. It really involves just 3 simple steps:
  1.Calculate the distance(Euclidean, Manhattan, etc) between a test data point and every training data point. This is to see who is closer and who is far by how much.
  2.Sort the distances and pick K nearest distances(first K entries) from it. Those will be K closest neighbors to your given test data point.
  3.Get the labels of the selected K neighbors. The most common label(label with a majority vote) will be the predicted label for our test data point.

Repeat everything above for all the test data points in your test set.

We will define a class ‘KNN’ inside which we will define every essential function that will make our algorithm work. We will be having the following methods inside our class.
  1. fit: As discussed earlier, it’ll just keep the data with itself, since KNN does not perform any explicit training process.
  2. Distance: We will calculate Euclidean distance here.
  3. Predict: This is the phase where we will predict the class for our testing instance using the complete training data. We will implement the 3 stepped process discusses above in this method.

What about ‘K’ ?: The most important guy here is K, we will pass ‘K’ as an argument while initializing the object for our KNN class(inside __init__)

Predict method runs a loop for every test data point, each time calculating distance between the test instance and every training instance. It stores distance and index of the training data together in a 2D list. It then sorts that list based on distance and then updates the list keeping only the K shortest distances(along with their indices) in the list.
It then pulls out labels corresponding to those K nearest data points and checks which label has the majority using Counter. That majority label becomes the label of the test data point.
