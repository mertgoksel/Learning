# Logistic Regression

Logistic regression is a method that takes parameters and interprets them for a yes/no output. (for exp; in titanic dataset the survival of a person is a logistic regression model.)

This method is great ONLY if no exceptions on outcomes are or can be occurent. If exceptions are many, then this method is not usable (not totally unusable but would not be great to use).

The purpose of the method is to fit a sigmoid function to the data (an s shaped line) to predict yes/no. The data that falls below the threshold of the s are no, above are yes. 

## Method

The output of the regression will always be 0 or 1! 

What we do have at the start may or may not include;

- Continuous data
- Categorical data

First things first we need to turn all values to numerical. This is for being able to use the categorical data in our regression. 

Given n amount of parameters, our sigmoid function (aka logistic regression) will be;

1 / (1 + exp(-sum(xi * ai))) where i is the number of the coefficients (sum(xi * ai) = x1 * a + x2 * b .... + constant)

But as always we wont be knowing the coefficients thus we use gradient descent.

Our cost function will not be mean squared error as it wont hold in this case, thus we use an appropriate one namely cross-entropy.

cross-entropy = j(inputs) = -1/N * sum(yi * log(f(inputs)) + (1 - yi) * log(1 - f(inputs)))

where;

- N = number of observations
- y = train sets target values
- i = class to predict
- f = sigmoid function
- inputs = independent variables which to be passed to sigmoid

### Deployment for single variable

g(z) = 1 / 1 + e^(-z) (bare sigmoid function)

z = theta^T * x (the regression function)

h(x) = g(theta^T * x) (sigmoid function to be used)

loss function(h, y) = j(h, y) = -1/N * sum(log(h) + (1 - y) * log(1 - h))

derivative for ith coefficient = -1/m * x^T * (h + y)

new ith coefficient => learning_rate * derivative of ith coefficient

### Extras

odds = p(success)/p(failure) = p / 1 - p = e^(a0 + a1 * x1 + a2 * x2...)

logodds = log(p / 1 - p) = a0 + a1 * x1 + a2 * x2... 