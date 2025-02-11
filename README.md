# **ZOMATO-DELIVERY-DATA-ANALYSIS-PYCARET-PREDICTION-OPTIMIZATION**

## Please open '.ipynb' file to have a look at full python code with detailed insights and visualizations.

## Objective
Analyze Zomato delivery data to uncover key factors affecting delivery time, build a predictive model using PyCaret for accurate time estimation, and provide data-driven optimization strategies to enhance delivery efficiency.

## Dataset Description
The dataset contains multiple features related to deliveries, including delivery personnel information, order details, traffic conditions, and delivery time.

### Libraries used
- import **pandas** as pd
- import **numpy** as np
- import **matplotlib.pyplot** as plt
- import **seaborn** as sns
- from **pycaret.regression** import *
- from **geopy.distance** import geodesic
- import **folium**
- from **folium.plugins** import **HeatMap**
- from **sklearn.preprocessing** import **OrdinalEncoder**
- from **sklearn.preprocessing** import **StandardScaler**
- from **sklearn.model_selection** import **train_test_split**

### Features
- **ID**: Unique identifier for each delivery.
- **Delivery_person_ID**: Unique identifier for each delivery person.
- **Delivery_person_Age**: Age of the delivery person.
- **Delivery_person_Ratings**: Ratings assigned to the delivery person.
- **Restaurant_latitude & longitude**: Geographical coordinates of the restaurant.
- **Delivery_location_latitude & longitude**: Geographical coordinates of the delivery location.
- **Order_Date**: Date of the order.
- **Time_Ordered**: Time the order was placed.
- **Time_Order_picked**: Time the order was picked up for delivery.
- **Weather_conditions**: Weather conditions at the time of delivery.
- **Road_traffic_density**: Density of road traffic during delivery.
- **Vehicle_condition**: Condition of the delivery vehicle.
- **Type_of_order**: Type of order (e.g., dine-in, takeaway, delivery).
- **Type_of_vehicle**: Type of vehicle used for delivery.
- **Multiple_deliveries**: Indicator of whether multiple deliveries were made in the same trip.
- **Festival**: Indicator of whether the delivery coincided with a festival.
- **City**: City where the delivery took place.
- **Time_taken (min)**: Time taken for delivery in minutes.

## Exploratory Data Analysis (EDA)

### Univariate Analysis
- The age group of most delivery persons is between **25 and 35**.
- Most delivery persons have ratings between **4.5 and 5**.
- Most orders are delivered in **20 to 35 minutes**.
- The restaurant-to-delivery location distance is typically **5 to 14 km**.
- Delivery speeds generally range between **10 km/h to 30 km/h**.

### Categorical Insights
- **Motorcycles** are the most commonly used vehicles.
- Most food orders originate from **metropolitan cities**.
- **Wednesdays and Fridays** receive the highest number of orders.

### Bivariate Analysis Insights
- **Weather Conditions**: Delivery time is **fastest in sunny weather** (~22 mins) and **slowest in cloudy & foggy conditions** (~29 mins).
- **Road Traffic Density**: Delivery time is **quickest in low traffic** and **longest during traffic jams** (~31.7 mins).
- **Type of Vehicle**: **Electric scooters** are the **fastest**, while **motorcycles** take longer.
- **Festival Impact**: Delivery time almost **doubles during festivals** (~45.5 mins vs. 26.3 mins).
- **City Type**: Urban deliveries are **quicker (23.5 mins)** compared to semi-urban areas (**49.7 mins**).

### Geo-Spatial Analysis
A **heatmap** was created to visualize delivery locations using **folium**. The heatmap highlights areas with high delivery density, which can help optimize delivery routes.

### Correlation Analysis
- **Distance vs. Time Taken**: Moderate positive correlation (0.41).
- **Traffic Density vs. Time Taken**: Moderate positive correlation (0.42).
- **Delivery Speed vs. Distance**: Strong positive correlation (0.77).
- **Multiple Deliveries vs. Time Taken**: Positive correlation (0.38), indicating batch deliveries increase time.

## Model Selection Using PyCaret
Using **PyCaret**, a regression model was built to predict delivery time based on various features. Key insights from model training:

- **Most impactful features on delivery time**:
  1. **Delivery Speed**
  2. **Distance from Restaurant to Delivery Location**
  3. **Road Traffic Density**
  4. **Vehicle Condition**

- **Model Performance**: The predicted delivery time closely aligns with actual times, confirming high accuracy.

## Saving and Loading the Model
The trained model was saved for future predictions, saved as **"rf_reg_pipeline.pkl"**.

## Key Recommendations for Optimization

### 1. **Enhance Delivery Speed**
- Switch to **electric scooters** for faster delivery.
- Incentivize high-performance delivery personnel.
- Regular vehicle maintenance to optimize speed.

### 2. **Manage Road Traffic Better**
- Implement **real-time traffic monitoring** to adjust routes dynamically.
- Avoid peak hours for deliveries.

### 3. **Optimize Routes Based on Distance**
- Utilize **AI-powered route optimization** tools.
- Group deliveries in nearby locations.

### 4. **Plan for Festivals & Weather**
- Adjust schedules and allocate extra resources during festivals.
- Use alternative delivery methods in extreme weather.

### 5. **Monitor Delivery Ratings**
- Longer deliveries tend to lower ratings.
- Track delivery times and offer training or incentives.

### 6. **Optimize Multiple Deliveries**
- Use **smart routing** to minimize additional time taken.
- Optimize the number of deliveries per trip.

### 7. **City-Specific Optimization**
- **Urban Areas**: Use faster vehicles, advanced routing.
- **Semi-Urban Areas**: Consider alternative delivery methods like drones.

## Conclusion
By implementing these strategies, food delivery companies can improve **delivery speed, reduce costs, and enhance customer satisfaction**. Leveraging **technology, efficient traffic management, and quality control** will ensure better service efficiency and reduced delivery times.

