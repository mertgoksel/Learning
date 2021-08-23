# K nearest neighbours

Knn is a classification algorithm that has not much maths. Basically it looks at the already known knowledge, given new knowledge tries to find the nearest k amount of neighbours then the highest amount of neighbours of the same category wins thus assigning that class to observation.

For exp: 

50 observations with 4 classes (A,B,C,D), New observations 10 nearest neighbours consist of;

- 4 A
- 5 B
- 1 C

Thus we assign B to the new observation. 

The only different able thing in this algorithm is the method to calculate the distances.

There are many ways, namely:

- Manhattan Method
- Euclidean Method
- Minkowski Method
- mahalanobis distance
- etc...

Euclidean distance is the most known way as its the main way that is used in calculus and analytical geometry.