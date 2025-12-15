# 🚗 Project 11 — Used Car Price Prediction (Gradient Boosting)

## 🔍 Objective

Build a production‑ready ML system for *Rusty Bargain* to predict used car prices, optimizing for:

* Prediction accuracy
* Training time
* Inference speed

**Target:** Car price (€)

---

### 📊 Dataset

* **330,000+ vehicles**
* 16 features (technical specs, brand, mileage, condition)
* Extensive missing values handled via **hierarchical imputation**

---

### 🧠 Models Evaluated

* Linear Regression (baseline)
* Decision Tree
* Random Forest
* **XGBoost**
* **CatBoost**
* **LightGBM**

---

### 🏆 Best Model

**LightGBM (Set 2)**

* **RMSE:** **1,627 €**
* Training time: ~58 seconds
* Prediction time: ~4 seconds

---

### 📈 Performance Comparison

| Model             | RMSE (€)  | Training Time | Prediction Speed |
| ----------------- | --------- | ------------- | ---------------- |
| LightGBM          | **1,627** | Fast          | Fast             |
| CatBoost          | 1,637     | Moderate      | **Very Fast**    |
| XGBoost           | ~1,650    | Moderate      | Moderate         |
| Random Forest     | 1,686     | **Very Slow** | Moderate         |
| Linear Regression | 2,865     | Very Fast     | Very Fast        |

---

### 🧠 Key Insights

* Gradient boosting reduced RMSE by **40%+** vs. Linear Regression
* CatBoost is ideal when **inference speed** is critical
* LightGBM provides the **best overall balance** for production

---

### 🛠 Tech Stack

* Python, pandas, NumPy
* scikit‑learn
* LightGBM, XGBoost, CatBoost

---

https://holly-d-c.github.io/my-portfolio/Project_12/Project_12_Car_App.html
