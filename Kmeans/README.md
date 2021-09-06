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

# Methods for initials

## For k parameter selection

There are 2 ways for this;

- Elbow Method (naive)
- Silhouette Method (better)

### Elbow Method

- The Squared Error for each point is the square of the distance of the point from its representation i.e. its predicted cluster center.

- The WSS score is the sum of these Squared Errors for all the points.

- Any distance metric like the Euclidean Distance or the Manhattan Distance can be used.

If the plot for wss does not give a clear answer, then use silhouette method.

### Silhoutette Method

Using the formula (b(i) - a(i))/max(b(i), a(i)) The highest valued k will be used

In this formula:

- a(i) "mean intra-cluster distance" = mean distance of all same cluster instances to the point i
- b(i) "mean nearest-cluster distance" = mean distance of all centroids to the point i

## For initial centroids

Will use Kmeans++ algorithm for this:

- Randomly select the first centroid from the data points.

- For each data point compute its distance from the nearest, previously chosen centroid.

- Select the next centroid from the data points such that the probability of choosing a point as centroid is directly proportional to its distance from the nearest, previously chosen centroid. (i.e. the point having maximum distance from the nearest centroid is most likely to be selected next as a centroid)

- Repeat steps 2 and 3 until k centroids have been sampled