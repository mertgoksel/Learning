# Principal Component Analysis

Lets us know how each feature affect the predictions and how much. The main point is to reduce dimensions from n to 2 so that more can be done with the data more easily.

# Method

- Take the average of all features

- Shift all values around the average point as origin.

- Find the linear regression line (using mean squared error method) that goest through origin (aka average point, aka only have the slope and intercept 0) may use gradient descent. Call this regressor line Principal component 1. The slope of PC1 will give us the knowledge about which feature has more spread by looking at the linear combination (aka pythagoras).

- PC2 is the perpendacular line from the origin to the PC1. (if more than 1 feature, then use gradient descent till n-1th PC and the final will again be the perpendacular aka PCN)

- Now shift everything again having PC1 as x and PC2 as y axis.

- Now that u have all the pcs, look at the sum of squares of distances of points to that pc line. Whichever is smaller has more weigth on explaining data.

- Now look for the pc pair that covers most of the data. Using the sum of squares to those pcs specifically draw a coordinate system for every sample with their respected distances to the pcs.

Voila! Now you have a 2d graph that explains majority of your data which can be visualised and interpretted much easier and efficiently.

## Difference between PCA and LDA 

While PCA doesnt care about labels on its mission to reduce dimensions, LDA on the other hand does the same thing but instead on an objective basis it looks for the best seperator axis. So that on that axis the classification is evident.