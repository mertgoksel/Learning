# Arima aka Autoregressive integrated moving average

For this youll need a time series data, meaning a dataset with observations and the time of those observations.

This technique ables you to predict the trends that will happen to the topic you are working on.
For this tho, we will need some prep work beforehand.

To understand this topic a person should know;
- What are time series
- trend, seasonality, cyclical and random
- White noise
- Autoregressive Model
- Moving average model
- ARMA model
- Stationary time series

## What are time series

Time series is a set of observations with different time of occuring. (15 day stock price data, day by day is a time series for exp.)

## trend, seasonality, cyclical and random

trend:
- A direction that a part of the data follows.

seasonality:
- Certain templates that the data obeys depending on the time.

cyclical:
- Data that almost like sin function, repeats itself over time.

random:
- Data that does not follow any trend, seasonality, cyclical template.

### White noise

Data that is purely random by nature is called as this. Because it doesnt contain any information.

Average is the only way for this type of data.

## Autoregressive model

This model is a basic looking back model. 

todays = constant + a * yesterday + b * thedaybeforeyesterday + ........ + error

constant,a,b.. being the coefficients

the prediction is only dependant on n amount of days before. 

Not great. big error range.

## Moving average model

This model utilizes the fact that errors of multiple parts of a time series are not correlated so they are white noise error terms. Meaning they come from normal distribution.

What we are trying to accomplish here is a linear regression created by error terms from the time series and their coefficients.

todays = mean + error(today) + a * error(yesterday) .......

This method is pretty popular in the smoothening process for time series data.

# ARMA model

ARMA model combines both Autoregression and Moving Average techniques. 

This model works only for stationary (meaning no trends are occurant) time series data.

todays = todays = constant + a * yesterday + b * thedaybeforeyesterday + ........ + 
         error(today) + aa * error(yesterday) .......

# ARIMA model

Arima model ables us to apply ARMA model to non stationary data by converting it to one.