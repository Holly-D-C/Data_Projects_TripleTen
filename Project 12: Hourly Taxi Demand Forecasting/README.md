# 🚕 Project 12 — Time Series Forecasting for Hourly Taxi Demand

---

## 🔍 Objective

Predict **hourly taxi demand** at airports for *Sweet Lift Taxi* to improve driver allocation.

**Success Criteria:** RMSE < 48

---

### 📊 Dataset

* March–August 2018 taxi order history
* Resampled to **hourly intervals**
* ~4,400 observations
* No missing data

---

### 🧠 Models Evaluated

**Statistical Models**

* AR, ARMA, ARIMA, **SARIMA**

**Machine Learning Models**

* Linear Regression
* Random Forest
* **CatBoost**
* **LightGBM**
* **XGBoost**

---

### 🏆 Best Model

**CatBoost (Advanced Features)**

* **RMSE:** **39.38** ✅
* Exceeded requirement by **18%**
* 33% improvement over persistence baseline

---

### 📈 Model Comparison (Selected)

| Model                | RMSE      | Meets Goal |
| -------------------- | --------- | ---------- |
| CatBoost             | **39.38** | ✅          |
| LightGBM             | 39.43     | ✅          |
| SARIMA               | 39.66     | ✅          |
| XGBoost              | 40.13     | ✅          |
| Random Forest        | 43.32     | ✅          |
| Linear Regression    | 45.83     | ✅          |
| Persistence Baseline | 58.86     | ❌          |

---

### 🧠 Key Insights

* **Feature engineering (lags + rolling means)** reduced RMSE by up to **28%**
* Gradient boosting models were the most reliable
* SARIMA remains competitive when seasonality is well captured

---

### 📌 Business Impact

With RMSE ≈ 39:

* Enables proactive driver recruitment 1–2 hours ahead
* Reduces passenger wait times
* Improves driver utilization and earnings

---

### 🛠 Tech Stack

* Python, pandas, NumPy
* matplotlib, scikit‑learn
* statsmodels, CatBoost, LightGBM, XGBoost

---

## ✅ Final Takeaways

* **Scaling matters** for distance‑based models
* **Gradient boosting dominates** structured tabular data
* **Feature engineering** is often more impactful than model choice
* **Privacy‑preserving ML** can be achieved without sacrificing accuracy

---

## Project Link

📂 **Notebook:** [Project 12: Hourly Taxi Demand Forecasting](https://holly-d-c.github.io/my-portfolio/Project_13_Time_Series/Project_13_Taxi_Order_Prediction.html)


