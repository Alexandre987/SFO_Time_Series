# SFO_Time_Series

#### -- Project Status: [Completed]

## Project Intro/Objective
The goal of this project is to capacity plan as accurately as possible for SFO (San Francisco's airport) through 2023 - 48 months away at the time of analysis. The purpose of the project was to use multiple time series methods to compare which would be the most effective, from traditional methods like SARIMA to newer methods like neural nets.

### Methods Used
* SARIMA
* Facebook Prophet
* Neural Nets (LSTM, CNN-LSTM, GRU)

### Technologies & Libraries
* Python
* Pandas / Numpy
* Matplotlib / Seaborn
* Sklearn
* Statsmodels (SARIMA)
* Fbprophet (Facebook Prophet)
* Keras (Neural Nets)

## Project Description
Monthly departure and arrival data was taken from [SFGov's website](https://data.sfgov.org/Transportation/Air-Traffic-Passenger-Statistics/rkru-6vcg). Data was aggregated to analyze the seasonality and trend growth of departures. Different time series tools were compared.

2015-19 was withheld as a test set, and data from 2005-2015 was used as training and validation. Mean absolute error on the test set was used as a measure of the most predictive model.

Mean Absolute Error Results:
* SARIMA - 5.5%
* Facebook Prophet - 5.4%
* GRU Neural Net - 4.6%

After mean absolute error was obtained, the model was retrained on all available data ('05-'19) to get the most accurate 4 year estimate. Because the time series pattern is regular, we can expect the future prediction to have around the same mean absolute error.

## Future Work

In future work, I'd like to take the difference between each airline's departures and arrivals every month. Time series analysis would then to be used to see if there is a seasonal pattern in this difference. If there is a predictable pattern, recommendations could be given for next year for two purposes:

1. Commercial: Airlines could know what level of inefficiency to expect from their flights in and out of SFO next year
2. Consumer: Passengers could know what airline to book in order to find the most empty plane in any given month (more leg room and baggage space!). For instance, perhaps one airline would be the best to fly during the winter holiday months, while another would be the best during the summer months.
