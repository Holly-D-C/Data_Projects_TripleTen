# 🚗 Used Car Price Prediction with Gradient Boosting

## Overview
Built and evaluated a production-ready machine learning system for *Rusty Bargain* to predict used car prices, balancing **prediction accuracy**, **training efficiency**, and **inference speed** for a customer-facing mobile application.

**Goal:** Deliver accurate, fast price estimates at scale.

---

## Key Results 🚀

✅ **Gradient boosting models significantly outperformed baselines**

- **Best Model:** **LightGBM**
- **RMSE:** **1,627 €** (≈ 40% improvement vs. Linear Regression)
- **Training Time:** ~58 seconds
- **Prediction Time:** ~4 seconds
- **CatBoost Alternative:** Nearly identical accuracy with **sub-second inference**

---

## Why LightGBM?

| Model | RMSE (€) | Training Time | Prediction Speed |
|-----|---------|---------------|------------------|
| **LightGBM** | **1,627** | Fast | Fast |
| CatBoost | 1,637 | Moderate | **Very Fast** |
| XGBoost | ~1,650 | Moderate | Moderate |
| Random Forest | 1,686 | **Very Slow** | Moderate |
| Linear Regression | 2,865 | Very Fast | Very Fast |

**Key Insight:**  
LightGBM offers the best **accuracy–performance trade-off**, while CatBoost is ideal when **real-time inference speed** is the primary constraint.

---

## Methodology (Brief)
- Cleaned and preprocessed **330,000+ vehicle records**
- Applied hierarchical imputation for missing technical specifications
- Evaluated tree-based and linear models under identical conditions
- Compared models using RMSE, training time, and inference speed

---

## Business Impact
- Enables **real-time car price estimates** in a mobile app
- Improves customer trust through accurate valuations
- Supports scalable deployment with fast inference
- Justifies computational cost with significant accuracy gains

---

## Tech Stack
- Python
- pandas
- NumPy
- scikit-learn
- LightGBM
- XGBoost
- CatBoost

---

## Project Link

📂 **Notebook:** [Project 11: Used Car Price Prediction with Gradient Boosting](https://holly-d-c.github.io/my-portfolio/Project_12/Project_12_Car_App.html)
