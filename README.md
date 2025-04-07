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


### 🔁 Kernel Comparison for SVR Model

We compared four different SVR kernels (`linear`, `poly`, `rbf`, and `sigmoid`) using `GridSearchCV` to tune the hyperparameters `C`, `epsilon`, and `gamma`. The evaluation metrics used were **Root Mean Squared Error (RMSE)** and **Adjusted R²**.

| Kernel   | Best Parameters                         | RMSE    | Adjusted R² |
|----------|------------------------------------------|---------|-------------|
| linear   | C=1, epsilon=0.1, gamma='scale'          | 851.77  | 0.8043      |
| poly     | C=1, epsilon=0.5, gamma='auto'           | 1124.00 | 0.6593      |
| rbf      | C=1, epsilon=0.1, gamma='auto'           | 643.66  | **0.8883**  |
| sigmoid  | C=1, epsilon=0.01, gamma='auto'          | 5605.57 | -7.4748     |

### ✅ Best Performing Kernel
- The **RBF (Radial Basis Function)** kernel achieved the **lowest RMSE** and **highest Adjusted R²**, making it the best-performing kernel for this regression task.
- The **linear kernel** also performed well but slightly underperformed compared to RBF.
- **Polynomial** and especially **sigmoid** kernels had significantly worse results, suggesting they are not a good fit for this dataset.

### 🎯 Conclusion
The RBF kernel is the most suitable for capturing the nonlinear relationships in the bike rental dataset. Future work could involve further hyperparameter tuning or comparing this with ensemble methods like **Random Forest** or **XGBoost** for potential improvements.
