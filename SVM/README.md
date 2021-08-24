# Support Vector Machine

Basically this method tries to put thresholds for each category, training this model will alter the position of the thresholds to be more precise. 

## Maximal Margin Classifier 

Tries to make the margins between the max of the lower sides category and min of the upper sides category the biggest. Thus making it very weak against outliers. So, not a great method if outliers are a thing in the population.




But if not taking the extremes of the both ends as the deciding factor for the threshold, what do we do?

We allow misclassifications. Thus we wont be a victim of Bias/Variance Tradeoff! By doing so we now do not have normal margins but __soft margins__ 

soft margin is a distance from randomly selected points one from each category, we select a random pair and look at the mean of the distance as the threshold.

Now that we are going to use soft margins, the thing comes down to *How do we select which soft margin is the best?*

Short answer? We cant.

Long answer? __WE USE CROSS VALIDATION TO ITERATE THROUGH ALL MARGINS MUHAHAHAHAHAHAHAHAH__ to finally find the best one.


## Method

Now its not always butterflies and sunsets on the data science world. Often we will have data that the threshold line will not be linear. So what do we do? we __BEND__ the space for our needs to __MAKE IT__ linear. The function that does this bending process of the space is a kernel.

Now first things first. 

Our Formula for this topic is

min 1/2 * slopes^T * slopes + C * sum(max(0,1 - yi(slopes^T * xi + intercept)))

Lets understand which portion does what;

- min 1/2 * slopes^T * slopes: Regularization term, Maximize the margin,
													Imposes a preference over the 
													hypothesis space and pushes for 
													better generalization,
													Can be replaced with other 
													regularization terms which impose 
													other preferences

- C: A hyper-parameter that 
     controls the tradeoff 
     between a large margin and 
     a small hinge-loss

- sum(max(0,1 - yi(slopes^T * xi + intercept))): Empirical Loss;
												            Hinge loss,
															Penalizes weight vectors that make 
															mistakes,
															Can be replaced with other loss 
															functions which impose other 
															preferences

Now for gradient descent part;

As you migth guess, the general formula is not differentiable... So what do we do?

We solve the max part first and compute the gradient for each case.

Steps:

- Initialize intercept, slopes = 0
- For epoch 1..N:
- For each xi,yi:
- If yi * slopes^T * xi <= 1, slope <- (1-learning_rate) * 0 + learning_rate * C * N * yi * xi
- Else slope <- (1-learning_rate) * old slope 
- Return slope

# Extras

- Cross Validation
- Bias/Variance Tradeoff

So we will first start with the easier one, Bias/Variance Tradeoff.

## Bias/Variance Tradeoff

This here is a consept, result of a term called overfitting. Basically it means that harder you train your model on your training data, your model will be dependent on that training data more. Thus not being able to predict for new or varying data. In a sense plagueing it.

## Cross Validation

Cross validation is a method that enables you to find the best machine learning algorithm that suits your needs best. Basically it tries all methods with variation on test/training data set that it implements on its own to get a general idea on how each ml algorithm does thus deciding on the best one.