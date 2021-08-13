# Gradient Descent (aka the optimizer)

This method is used to get optimized parameters for ANY kind of model. 

The loss functions aka the residuals are your enemy. You have to get to the point where you have LEAST amount of them. This is key for all machine learning problems.

## The Method

To do this we look at sum of squares residuals meaning sum(residuals^2). 
you give random values to variables and graph the result ssr at each instance. The point where the maxima/minima is your optimized parameter. 

The difference between doing this randomly and gradient descent is that, gradient descent does this much fewer times moving from big steps to miniscule as it nears to the most optimal point making it a much more efficient way.

### Gradient Descent one variable with SSR

In this instance we know the optimal slope so we are looking for the intercept

slope = .64

In the formula of ssr change the predicted variable with its formula. 

SSR = sum((data - predicted)^2) -> sum((data - (intercept + slope * x))^2)
								 = sum((data - (intercept + .64 * x))^2)

for every point of data change x with that points x value

now you have n amount of residual formula with only intercept being unknown. 

get the sum of all these formulas to find ssr formula

from here on out the algorithm will take steps to get the best parameter that results in the lowest ssr. In order to do this we will need to first put a random number to intercept. This will result in a value for the ssr and its slope. Then we will take this ssr slope and multiply it with the "Learning rate". 

old intercept - step size will give us the new parameter to input. 

Rince and repeat until the ssr slope is near 0 (normally if step size becomes lower than 0.001 then gradient descent stops the loop). Thus you will have the most optimal parameter.

### Gradient Descent multiple variables with SSR

Same with the one variable version until getting the SSR general function. Unlike before now we have 2 or more variables that we need to put in numbers to.

But then again we still get the derivative of it to get the slope of SSR but unlike before we will get the derivative for all unknown variables (intecept, x1, x2 ...) 

Now we have n amount of functions, now we will select a random intercept. But we also select random numbers for the slopes.

We put these random values to all derivatives.

Now that we have results for all derivatives, we now put the results to step size function to get the new values (old value - step size for that value where step size = old value * learning rate) to put into these derivatives.

# Extras

The method of least square loss function is not the only one. Each type of data has at least one method.

Notice: Loss function is the function where you apply gradient descent to. In this instance it was Sum of Squared Residuals.

But whatever loss function you may use gradient descent does not change. Get the loss function slope, then put a random number in, get the step size for that number, now use old - step size as the new number; repeat till step size is lower than 0.001 (or another number bigger/smaller, or epoch size.. It depends on the situation). 

# interpolation
# road from gradient to adam
