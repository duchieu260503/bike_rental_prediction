# 🚲 Bike Rental Prediction – Check-Up Notes

## ✅ 1. Dataset Description

- **Source**: "Bike Sharing Dataset"
- **Goal**: Predict the total number of bike rentals (`cnt`) per day using features like weather, holiday, and season.
- **Features**:
  - `season`: 1 = spring, 2 = summer, 3 = fall, 4 = winter  
  - `yr`: 0 = 2011, 1 = 2012  
  - `mnth`: Month (1 to 12)  
  - `holiday`: 1 = holiday, 0 = not a holiday  
  - `weekday`: 0 = Sunday, 6 = Saturday  
  - `workingday`: 1 = working day, 0 = weekend/holiday  
  - `weathersit`: 1 = Clear, 2 = Mist, 3 = Light Snow/Rain, 4 = Heavy Rain + Ice Pallets + Thunderstorm
  - `temp`: Normalized temperature in Celsius (0 to 1)  
  - `atemp`: Normalized “feels like” temperature  
  - `hum`: Normalized humidity  
  - `windspeed`: Normalized wind speed  
  - `cnt`: Total rentals (casual + registered)

---

## ✅ 2. Problem Definition

We aim to build a machine learning model to **predict daily bike rental counts** (`cnt`) based on various environmental and calendar features.

> This helps with operational planning, resource allocation, and customer behavior analysis.

---

## ✅ 3. Machine Learning Plan

We will test multiple regression models and compare their performance:

- **Multi Regression**: Establishes a baseline.
- **Random Forest Regressor**: Reduces overfitting, improves accuracy.
- **SVR**: Captures complex, non-linear patterns.

**Evaluation Metric**:  
- RMSE (Root Mean Squared Error)
- Adjusted R2
---
