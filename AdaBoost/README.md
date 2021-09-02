# AdaBoost

This is a special method that uses normal ml methods and organizes them in a new way.

Basically its a combined force of weak learners. These weak learners are methods applied to train data for only 1 column. After you create these weak learners, you assign them new weigth coefficients.

After this is complete now it adjusts the learners by iterating.

And tada! You have your better made learner.

## Method

We will work with decision tree adaboost.

Stumps are single node decision trees made only for 1 column.

1. We will assign an equal sample weight to each observation. 1/N

2. We will create M decision stumps, for M number of features.

3. Out of all M decision stumps, I first have to select one best decision tree model. For selecting it, we will either calculate the Entropy or Gini coefficient. The model with lesser entropy will be selected (means model that is less disordered).

4. Now, after the first decision stump is built, an algorithm would evaluate this decision and check how many observations the model has misclassified.

5. Suppose out of N observations, The first decision stump has misclassified T number of observations.

6. For this, we will calculate the total error (TotalErr), which is equal to T/N.

7. Now we will calculate the performance of the first decision stump.

Performance of stump = 1/2*loge((1-TotalErr)/TotalErr)

8. Now we will update the weights assigned before. To do this, we will first update the weights of those observations, which we have misclassified. The weights of wrongly classified observations will be increased and the weights of correctly classified weights will be reduced.

9. By using this formula: old weight * exp(performance of stump)

10. Now respectively for each observation, we will add and subtract the updated weights to get the final weights. 

11. But these weights are not normalized so their sum is not equal to one. To do this, we will sum them and divide each final weight with that sum. 

12. After this, we have to make our second decision stump. For this, we will make a class intervals for the normalized weights.

13. After that, we want to make a second weak model. But to do that, we need a sample dataset on which the second weak model can be run. For making it, we will run N number of iterations. On each iteration, it will calculate a random number ranging between 0-1 and this random will be compared with class intervals we created and on which class interval it lies, that row will be selected for sample data set. So new sample data set would also be of N observation. 

14. This whole process will continue for M decision stumps. The final sequential tree would be considered as the final tree.