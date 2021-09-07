# DBScan

This clustering method can work with any shaped clusters so it is widely used.

# Method

Given epsilon (the max radius of any cluster), k (minimum number of clusters):

- An initial point is selected
- Via given epsilon the point, the points in the circle of that point are labeled normal
- Via given epsilon the normal points circles are looked at, if anymore points are within these circles they are labeled border points and are added to the same cluster
- Until no more points are found repeat 3rd and finalize the cluster
- Now select another point which is not classified yet
- Apply 3,4 for that point too
- Apply 3,4,5,6 till no more unclassified points left.