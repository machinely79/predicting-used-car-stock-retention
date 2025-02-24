# Predicting Used Car Stock Retention: A Time-To-Event Approach

This repository contains the implementation of Time-To-Event (TTE) machine learning models for predicting used car stock retention. The project compares different survival analysis techniques, including Cox Proportional Hazards, Random Survival Forest, and Gradient-Boosted Cox, to estimate the probability of a vehicle remaining in stock over time.
This approach provides a novel perspective on inventory optimization for used vehicles by leveraging TTE methods instead of traditional time-series forecasting.

# Benefits of Using Time-To-Event Modeling for Demand Prediction

Maintaining inventory at an optimal level continuously depends largely on demand forecasting accuracy. While Time Series Forecasting methods offer certain advantages, they also have limitations compared to Time-To-Event (TTE) methods:

1. One key limitation of Time Series Forecasting is that it only trains on products with recorded sales during a given period, meaning it considers only uncensored products (those sold within a specific timeframe) while completely ignoring censored products (those that remain unsold). 
2. Time Series Forecasting predicts product demand at an aggregate level. In contrast, Time-To-Event (TTE) models can track the sales probability of a single unique product and estimate its survival (retention) in stock over time. Unlike aggregate-level forecasting, TTE methods allow for daily-level sales predictions, even when only a few such products—e.g., two units—were sold in the previous month. This provides a different perspective on result interpretation, which can be highly beneficial.
3. TTE models have a distinct advantage over Time Series Forecasting when predicting sales for products that are not sold frequently daily. These include high-value items such as cars, real estate, and industrial machinery. For example, a specific car model is not sold every day, making it difficult to reliably predict sales volumes for a given date using Time Series Forecasting due to time series discontinuity.

# Trained Models Performance Summary

The training and validation process was conducted on 80% (n = 2245) of the dataset (n = 2807). The applied models produced the following key performance metrics, evaluated using the Concordance Index (C-Index):

•	Gradient-Boosted Cox achieved the highest mean test score (0.846).

•	Cox Proportional Hazards and Random Survival Forest performed similarly, with mean test scores of 0.838 and 0.837, respectively.

•	Random Survival Forest exhibited the lowest standard deviation (0.011), indicating the most stable performance.

#### **Table 1. Cross-Validation Results**
![Model Performance](https://github.com/machinely79/predicting-used-car-stock-retention/blob/main/images/cv_best_model_results.png)


#### **Figure 1. Concordance Index Across Models** 
![Concordance Index](https://github.com/machinely79/predicting-used-car-stock-retention/blob/main/images/concordance_index_across_models.png)

## Model Evaluation on Test Data
The best-performing model, Gradient-Boosted Cox, which achieved the highest mean test score (0.846), was deployed on the test dataset to evaluate its generalization performance.
The evaluation on the test dataset resulted in a Concordance Index of 0.8382, indicating a strong predictive performance.

## Dataset Overview

This dataset contains approximately 2,800 used vehicles with 74 detailed attributes:

- **Id**: Unique identifier
- **IsSold**: Indicates whether the car has been sold (True/False)
- **WeeksOnStockBeforeSale**: Number of weeks the car was on stock before being sold
- **onAction**: Indicates whether the car is on a promotional sale (True/False)
- **SalesSeason**: The season when the car was sold (e.g., Winter, Summer)
- **Total_Price**: Total price of the car in the dataset
- **Car_Age_Years**: Age of the car in years
- **Kilometers**: Total kilometers driven
- **Kilowatts**: Engine power in kilowatts
- **Horsepower**: Engine power in horsepower
- **Cars**: Car model name
- **Engine_Type**: Type of engine (e.g., diesel, petrol, hybrid)
- **Body_Type**: Car body type (e.g., sedan, SUV, hatchback)
- **Transmission_Type**: Type of transmission (manual or automatic)
- **Color**: Exterior color of the car
- **Number_of_Doors**: Total number of doors
- **Alarm**: Indicates if the car has an alarm system
- **Alloy_Wheels_16**: Indicates if the car has 16-inch alloy wheels
- **ASR**: Anti-Slip Regulation system (traction control)
- **Automatic_Climate_Control**: Indicates if the car has automatic climate control,+
- **Bi_Xenon**: Indicates if the car has Bi-Xenon headlights,
- **Bluetooth_Connection**: Indicates if the car has Bluetooth connectivity,
- **Remote_Locking**: Indicates if the car has remote key locking,
- **Electric_Windows**: Indicates if the car has electric window control,
- **Electric_Folding_Mirrors**: Indicates if the car has electrically foldable mirrors,
- **Electric_Mirror_Adjustment**: Indicates if the side mirrors can be adjusted electronically,
- **ESP**: Electronic Stability Program for improved handling,
- **Keyless_Go**: Indicates if the car has keyless entry and start,
- **LED_Lights**: Indicates if the car has LED headlights,
- **Steering_Wheel_Buttons**: Indicates if the steering wheel has control buttons,
- **Rear_Headrest**: Indicates if the rear seats have adjustable headrests,
- **Armrest**: Indicates if the car has a center armrest,
- **Navigation**: Indicates if the car has a built-in navigation system,
- **Mobile_Device_Preparation**: Indicates if the car has mobile device integration,
- **Trip_Computer**: Displays real-time driving information,
- **Rear_Parking_Sensor**: Indicates if the car has rear parking sensors,
- **Cruise_Control**: Indicates if the car has cruise control,
- **Xenon**: Indicates if the car has Xenon headlights,
- **Chrome_Package**: Indicates if the car has a chrome styling package,
- **Fog_Lights**: Indicates if the car has fog lights,
- **Heated_Front_Seats**: Indicates if the front seats are heated,
- **Front_Parking_Sensor**: Indicates if the car has front parking sensors,
- **Alloy_Wheels_17**: Indicates if the car has 17-inch alloy wheels,
- **Alloy_Wheels_19**: Indicates if the car has 19-inch alloy wheels,
- **Parking_Camera**: Indicates if the car has a rear parking camera,
- **Panoramic_Roof**: Indicates if the car has a panoramic glass roof,
- **Sliding_Panoramic_Roof**: Indicates if the panoramic roof is sliding,
- **All_Wheel_Drive**: Indicates if the car has all-wheel drive (AWD/4x4),
- **Manual_Air_Conditioning**: Indicates if the car has manual air conditioning,
- **Side_Roller_Blinds**: Indicates if the car has side window roller blinds,
- **Heated_Rear_Seats**: Indicates if the rear seats are heated,
- **Alloy_Wheels_18**: Indicates if the car has 18-inch alloy wheels,
- **Electric_Seat_Adjustment**: Indicates if the seats can be adjusted electronically,
- **Electric_Sunroof**: Indicates if the car has an electrically operated sunroof,
- **Seat_Memory_Package**: Indicates if the driver's seat has a memory function,
- **Rear_Roller_Blind**: Indicates if the car has a rear window roller blind,
- **Cooled_Front_Seats**: Indicates if the front seats are ventilated/cooled,
- **Head_Up_Display**: Projects driving information onto the windshield,
- *Park_Assist**: Indicates if the car has an automated parking system,
- **360_Parking_Camera**: Indicates if the car has a 360-degree parking camera,
- **Alloy_Wheels_20**: Indicates if the car has 20-inch alloy wheels,
- **Passenger_Seat_Memory_Package**: Indicates if the front passenger seat has memory settings,
- **Air_Suspension**: Indicates if the car has air suspension for adjustable ride height,
- **Alloy_Wheels_22**: Indicates if the car has 22-inch alloy wheels,
- **Alloy_Wheels_21**: Indicates if the car has 21-inch alloy wheels,
- **Cooled_Rear_Seats**: Indicates if the rear seats are ventilated/cooled,
- **Front_Electric_Windows**: Indicates if the front windows are electrically operated,
- **Alloy_Wheels_15**: Indicates if the car has 15-inch alloy wheels,
- **Virtual_Cockpit**: Indicates if the car has a fully digital instrument cluster,
- **Alcantara**: Indicates if the interior includes Alcantara material,
- **Leather_Alcantara**: Indicates if the seats are a mix of leather and Alcantara,
- **Leather**: Indicates if the seats are upholstered in leather,
- **Fabric**: Indicates if the seats are upholstered in fabric,
- **Leather_Fabric**: Indicates if the seats are a mix of leather and fabric,

