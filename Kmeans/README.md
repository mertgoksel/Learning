# Kmeans Clustering

The most basic clustering method there is

Only use to get a rough idea about tresholds and nothing else. Terrible for non absolutely evident data.

# Method

K-Means is actually one of the simplest unsupervised clustering algorithm. Assume we have input data points x1,x2,x3,…,xn and value of K(the number of clusters needed). We follow the below procedure:

- Pick K points as the initial centroids from the data set, either randomly or the first K.

- Find the Euclidean distance of each point in the data set with the identified K points — cluster centroids.

- Assign each data point to the closest centroid using the distance found in the previous step.

- Find the new centroid by taking the average of the points in each cluster group.

- Repeat 2 to 4 for a fixed number of iteration or till the centroids don’t change.