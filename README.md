# 311-Request-Project-3

Dat512 

Canisius College

Kyle Eberle
# Project Description
In this project I was tasked with again looking into the public Buffalo 311 Request data. This time around
looking into a time series forecast using dates before 2023, trying to predict the requests 
that would occur throughout 2023.

In this analysis I focused on the following:
* General cleanup and manipulation of the data sets
  * To be able answer questions with the most compelling visuals
* Performing a time series analysis on the requests for 2023
* Using both the FB Prophet and ARIMA methods to check and compare results

# Data used for project
https://data.buffalony.gov/Quality-of-Life/311-Service-Requests/whkc-e5vr

# Project Overview
#### Data Pull/Cleaning
* Data was pulled from the Open Buffalo Data site using API request method
* Cleansing of data along with manipulation of datetime conversions 
* Creating subsets of only essential columns/grouping reasons
#### FB Prophet Analysis
* Had to manipulate the data to get it to a point were a forecast could be carried out
  * This included limiting ot just the open date column, while creating a count by day column
  * Lastly the dates were grouped by distinct date over the time period to consolidate
* From there the forecast was carried out, leading to an R-Squared score of 0.62 which 
  showed a fairly decent prediction
* Trying to build on that R-squared score I took into account holidays
  * Here I created a subset of known US holidays as well as creating custom "holidays"
    using the dates of teh covid lockdown
* I expected this to help the overall prediction scores however after taking holidays
  into account my R-squared score dropped to 0.47
#### ARIMA Forecast Analysis
* ARIMA Forecasting is a different time series forecasting method used to predict future values based on past observations. 
* It is a combination of three components: autoregression (AR), differencing (I), and moving average (MA).
* After running the ARIMA model we found a mean of 94.65 and a mean squared error of 105 in regards to the 311 requests
* The final plot in the jupyter notebook shows a 2023 prediction that flucuates a lot throughout.
  * In my opinion not proving to be all that accurate with this set of data at predicting future requests

