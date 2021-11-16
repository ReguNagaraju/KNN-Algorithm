# KNN-Algorithm

K-Nearest Neighbour: The Distance-Based Machine Learning Algorithm.

Introduction
The abbreviation KNN stands for “K-Nearest Neighbour”. It is a supervised machine learning algorithm. The algorithm can be used to solve both classification and regression problem statements.

The number of nearest neighbours to a new unknown variable that has to be predicted or classified is denoted by the symbol ‘K’.

Let’s take a good look at a related real-world scenario before we get started with this awesome algorithm.

We are often notified that you share many characteristics with your nearest peers, whether it be your thinking process, working etiquettes, philosophies, or other factors. As a result, we build friendships with people we deem similar to us.

The KNN algorithm employs the same principle. Its aim is to locate all of the closest neighbours around a new unknown data point in order to figure out what class it belongs to. It’s a distance-based approach.

Consider the diagram below; it is straightforward and easy for humans to identify it as a “Cat” based on its closest allies. This operation, however, cannot be performed directly by the algorithm.

KNN calculates the distance from all points in the proximity of the unknown data and filters out the ones with the shortest distances to it. As a result, it’s often referred to as a distance-based algorithm.

In order to correctly classify the results, we must first determine the value of K (Number of Nearest Neighbours).

In the following diagram, the value of K is 5. Since there are four cats and just one dog in the proximity of the five closest neighbours, the algorithm would predict that it is a cat based on the proximity of the five closest neighbors in the red circle’s boundaries.

![image](https://user-images.githubusercontent.com/92477493/141942191-3ff1588f-4eae-4be4-bffb-de77c5a1345c.png)


Here, ‘K’ is the hyperparameter for KNN. For proper classification/prediction, the value of K must be fine-tuned.

But, How do we select the right value of K?
We don’t have a particular method for determining the correct value of K. Here, we’ll try to test the model’s accuracy for different K values. The value of K that delivers the best accuracy for both training and testing data is selected.

Note!!
It is recommended to always select an odd value of K ~ 
When the value of K is set to even, a situation may arise in which the elements from both groups are equal. In the diagram below, elements from both groups are equal in the internal “Red” circle (k == 4).

In this condition, the model would be unable to do the correct classification for you. Here the model will randomly assign any of the two classes to this new unknown data.

Choosing an odd value for K is preferred because such a state of equality between the two classes would never occur here. Due to the fact that one of the two groups would still be in the majority, the value of K is selected as odd.

![image](https://user-images.githubusercontent.com/92477493/141942343-6c648753-2b2e-4a41-8a5a-43d9390fa81e.png)

The impact of selecting a smaller or larger K value on the model

Larger K value: The case of underfitting occurs when the value of k is increased. In this case, the model would be unable to correctly learn on the training data.
Smaller k value: The condition of overfitting occurs when the value of k is smaller. The model will capture all of the training data, including noise. The model will perform poorly for the test data in this scenario.

![image](https://user-images.githubusercontent.com/92477493/141942418-17691e5b-702b-4fdf-9d1c-ecb7902a5955.png)


How does KNN work for ‘Classification’ and ‘Regression’ problem statements?
Classification~
When the problem statement is of ‘classification’ type, KNN tends to use the concept of “Majority Voting”. Within the given range of K values, the class with the most votes is chosen.

Consider the following diagram, in which a circle is drawn within the radius of the five closest neighbours. Four of the five neighbours in this neighbourhood voted for ‘RED,’ while one voted for ‘WHITE.’ It will be classified as a ‘RED’ wine based on the majority votes.

![image](https://user-images.githubusercontent.com/92477493/141942506-d54c5a1b-adac-47ea-a881-e3992d46638d.png)

Real-world example:
Several parties compete in an election in a democratic country like India. Parties compete for voter support during election campaigns. The public votes for the candidate with whom they feel more connected.

When the votes for all of the candidates have been recorded, the candidate with the most votes is declared as the election’s winner.

Regression~
KNN employs a mean/average method for predicting the value of new data. Based on the value of K, it would consider all of the nearest neighbours.

The algorithm attempts to calculate the mean for all the nearest neighbours’ values until it has identified all the nearest neighbours within a certain range of the K value.

Consider the diagram below, where the value of k is set to 3. It will now calculate the mean (52) based on the values of these neighbours (50, 55, and 51) and allocate this value to the unknown data.

![image](https://user-images.githubusercontent.com/92477493/141942957-c0f9d0c4-bde4-4f53-bb61-3c28cc7bf50e.png)


Impact of Imbalanced dataset and Outliers on KNN
Imbalanced dataset~
When dealing with an imbalanced data set, the model will become biased. Consider the example shown in the diagram below, where the “Yes” class is more prominent.

As a consequence, the bulk of the closest neighbours to this new point will be from the dominant class. Because of this, we must balance our data set using either an “Upscaling” or “Downscaling” strategy.

![image](https://user-images.githubusercontent.com/92477493/141943059-fd3a513a-e59f-4ae9-b603-f6088a5f6fb5.png)


Outliers~
Outliers are the points that differ significantly from the rest of the data points.

The outliers will impact the classification/prediction of the model. The appropriate class for the new data point, according to the following diagram, should be “Category B” in green.

The model, however, would be unable to have the appropriate classification due to the existence of outliers. As a result, removing outliers before using KNN is recommended.

![image](https://user-images.githubusercontent.com/92477493/141943158-3a3c0c6a-00a7-4ab1-956b-47983e10d6e3.png)

Importance of scaling down the numeric variables to the same level
Data has 2 parts: –
1) Magnitude
2) Unit
For instance; if we say 20 years then “20” is the magnitude here and “years” is its unit.
Since it is a distance-dependent algorithm, KNN selects the neighbours in the closest vicinity based solely on the magnitude of the data.  Have a look at the diagram below; the data is not scaled, so it can not find the closest neighbours correctly.  As a consequence, the outcome will be influenced.

![image](https://user-images.githubusercontent.com/92477493/141943237-58a84849-aac1-4dd7-8470-123467377109.png)

The data values in the previous figure have now been scaled down to the same level in the following example. Based on the scaled distance, all of the closest neighbours would be accurately identified.

![image](https://user-images.githubusercontent.com/92477493/141943300-06891b20-dd99-4eeb-a299-3e1f1b9dd916.png)



