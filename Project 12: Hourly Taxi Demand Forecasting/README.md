# 🚕 Hourly Taxi Demand Forecasting (Time Series)

## Overview
Developed a time series forecasting system for *Sweet Lift Taxi* to predict **hourly airport taxi demand**, enabling proactive driver allocation and reduced passenger wait times.

**Goal:** Achieve RMSE < **48** while maintaining reliable short-term forecasts.

---

## Key Results 🚀

✅ **Forecasting accuracy exceeded business requirements**

- **Best Model:** **CatBoost with advanced time-series features**
- **RMSE:** **39.38** (≈ **18% better** than target threshold)
- **Baseline Improvement:** **33%** reduction vs. persistence model
- Multiple models met operational accuracy requirements

---

## Why CatBoost?

| Model | RMSE | Meets Goal |
|-----|-----|-----------|
| **CatBoost** | **39.38** | ✅ |
| LightGBM | 39.43 | ✅ |
| SARIMA | 39.66 | ✅ |
| XGBoost | 40.13 | ✅ |
| Random Forest | 43.32 | ✅ |
| Linear Regression | 45.83 | ✅ |
| Persistence Baseline | 58.86 | ❌ |

**Key Insight:**  
Gradient boosting models with engineered lag and rolling features consistently outperform purely statistical approaches, while SARIMA remains competitive when seasonality is well captured.

---

## Methodology (Brief)
- Resampled taxi order data to **hourly intervals** (~4,400 observations)
- Engineered lag features and rolling statistics
- Evaluated statistical and ML models under identical conditions
- Benchmarked performance using RMSE against a persistence baseline

---

## Business Impact
- Enables **1–2 hour ahead driver allocation**
- Reduces passenger wait times during peak demand
- Improves driver utilization and revenue stability
- Supports data-driven operational planning

---

## Tech Stack
- Python
- pandas
- NumPy
- matplotlib
- scikit-learn
- statsmodels
- CatBoost
- LightGBM
- XGBoost

---

## Project Link

📂 **Notebook:** [Project 12: Hourly Taxi Demand Forecasting](https://holly-d-c.github.io/my-portfolio/Project_13_Time_Series/Project_13_Taxi_Order_Prediction.html)
