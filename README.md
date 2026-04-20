# time-series-demand-forecasting
Time series forecasting project predicting hourly taxi demand using historical airport data. Includes feature engineering (lags, rolling mean, calendar features), model comparison (Linear, Random Forest, LightGBM), and validation. Best model achieves RMSE &lt; 48.
# 🚕 Taxi Demand Forecasting (Time Series Project)

## 📌 Project Overview

Sweet Lift Taxi collected historical data on taxi orders at airports.
The goal of this project is to **predict the number of taxi requests for the next hour** in order to optimize driver allocation during peak demand periods.

This is a **time series forecasting problem** solved using machine learning models.

---

## 🎯 Objective

* Predict hourly taxi demand
* Achieve **RMSE ≤ 48** on the test dataset
* Compare multiple models and evaluate performance

---

## 📊 Dataset

* Source file: `/datasets/taxi.csv`
* Time range: March 2018 – August 2018
* Original frequency: **10 minutes**
* Resampled to: **1 hour**

Target variable:

* `num_orders` → number of taxi requests

---

## 🔧 Data Preprocessing

* Sorted by datetime index
* Resampled into hourly intervals using aggregation
* Handled missing values after feature engineering

---

## 🧠 Feature Engineering

The following features were created:

### ⏱ Time-based features

* Hour of day
* Day of week
* Day of month
* Month

### 🔁 Lag features

* Lag 1 to Lag 10 (previous hours)

### 📉 Rolling statistics

* Rolling mean (24-hour window)

These features help capture:

* Temporal dependencies
* Seasonality patterns
* Trends in demand

---

## 🤖 Models Used

* Linear Regression (baseline model)
* Random Forest Regressor
* LightGBM Regressor

Additionally:

* Median baseline model for comparison

---

## 📈 Model Evaluation

Evaluation metric:

* **RMSE (Root Mean Squared Error)**

Models were evaluated on:

* Training set
* Test set (10% split, no shuffling)

---

## 🧪 Validation Strategy

* Time-based split (no shuffling)
* Additional validation using **TimeSeriesSplit**
* Hyperparameter tuning using **GridSearchCV**

---

## 📊 Results

| Model             | RMSE (Train) | RMSE (Test) |
| ----------------- | ------------ | ----------- |
| Linear Regression | 30.13          | 51.14         |
| Random Forest     | 8.57          | 43.50         |
| LightGBM          | 13.75          | **41.84**      |
| Baseline (Median) | 38.85           | 87.21       |

✅ The best model achieved **RMSE < 48**, meeting the project requirement.

---

## 🔍 Key Insights

* Tree-based models outperform linear models due to non-linear relationships
* Lag features are the most important predictors
* Rolling mean improves stability and trend capture
* Calendar features (month, day) improve seasonality detection

---

## 🚀 Conclusion

The project successfully developed a machine learning model capable of predicting hourly taxi demand with high accuracy.

LightGBM provided the best performance and met the required RMSE threshold, making it a strong candidate for real-world deployment.

---

## 🛠 Tech Stack

* Python
* Pandas
* NumPy
* Scikit-learn
* LightGBM
* Matplotlib

---


---

## 👤 Author

Juan Manuel Puentes Sayo
Biomedical Engineer | Data Science Enthusiast
Based in Canada 🇨🇦

---

## 📬 Contact

Feel free to connect or reach out for collaboration opportunities!
