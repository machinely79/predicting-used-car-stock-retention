# Predicting Used Car Stock Retention: A Time-To-Event Approach

This repository contains the implementation of Time-To-Event (TTE) machine learning models for predicting used car stock retention. The project compares different survival analysis techniques, including Cox Proportional Hazards, Random Survival Forest, and Gradient-Boosted Cox, to estimate the probability of a vehicle remaining in stock over time.
This approach provides a novel perspective on inventory optimization for used vehicles by leveraging TTE methods instead of traditional time-series forecasting.

# Benefits of Using Time-To-Event Modeling for Demand Prediction

Maintaining inventory at an optimal level continuously depends largely on demand forecasting accuracy. While Time Series Forecasting methods offer certain advantages, they also have limitations compared to Time-To-Event (TTE) methods:

1. One key limitation of Time Series Forecasting is that it only trains on products with recorded sales during a given period, meaning it considers only uncensored products (those sold within a specific timeframe) while completely ignoring censored products (those that remain unsold). 
2. Time Series Forecasting predicts product demand at an aggregate level. In contrast, Time-To-Event (TTE) models can track the sales probability of a single unique product and estimate its survival (retention) in stock over time. Unlike aggregate-level forecasting, TTE methods allow for daily-level sales predictions, even when only a few such products—e.g., two units—were sold in the previous month. This provides a different perspective on result interpretation, which can be highly beneficial.
3. TTE models have a distinct advantage over Time Series Forecasting when predicting sales for products that are not sold frequently daily. These include high-value items such as cars, real estate, and industrial machinery. For example, a specific car model is not sold every day, making it difficult to reliably predict sales volumes for a given date using Time Series Forecasting due to time series discontinuity.

# Model Performance Summary

The applied models produced the following key performance metrics, evaluated using the Concordance Index (C-Index):

•	Gradient-Boosted Cox achieved the highest mean test score (0.846).

•	Cox Proportional Hazards and Random Survival Forest performed similarly, with mean test scores of 0.838 and 0.837, respectively.

•	Random Survival Forest exhibited the lowest standard deviation (0.011), indicating the most stable performance.

#### **Cross-Validation Results**
![Model Performance](https://github.com/machinely79/predicting-used-car-stock-retention/blob/main/images/cv_best_model_results.png)
#### **Concordance Index Across Models** 
![Concordance Index](https://github.com/machinely79/predicting-used-car-stock-retention/blob/main/images/concordance_index_across_models.png)


## Dataset Overview

This dataset contains approximately 2,800 used vehicles with detailed attributes categorized as follows:
