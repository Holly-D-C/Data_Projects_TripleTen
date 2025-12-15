# 🥇 Gold Recovery Prediction (Industrial Machine Learning)

## Overview
Built a machine learning system to **predict gold recovery rates** during the flotation and purification process using industrial sensor data. Accurate predictions enable mining operators to optimize chemical dosing, detect low-yield conditions early, and improve production efficiency before full batch processing.

**Goal:** Predict rougher and final gold recovery using only deployment-safe features.

---

## Key Results 🚀

✅ **Production-ready recovery prediction**

- **Best Model:** Random Forest Regressor
- **Final sMAPE:** **11.48%**
- **Baseline Improvement:** ~20% error reduction
- **Leakage-safe pipeline** validated on unseen test data
- **Recovery formula validated** (MAE ≈ 0)

---

## Why This Model?

| Model | sMAPE (%) |
|-----|-----------|
| **Random Forest** | **11.48** |
| Linear Regression | 14.64 |
| Decision Tree | 22.48 |

**Key Insight:**  
Tree-based ensembles capture non-linear chemical and physical interactions significantly better than linear or shallow models while remaining robust to noisy sensor data.

---

## Methodology (Brief)
- Removed **34 leakage-prone features** unavailable at prediction time
- Applied **process-aware conditional imputation**
- Validated metallurgical recovery formulas
- Tuned model via cross-validated grid search
- Evaluated using sMAPE (industry-appropriate metric)

---

## Business Impact
- Enables **early intervention** for low-recovery conditions
- Reduces chemical waste and operational costs
- Improves batch-level decision making
- Supports scalable deployment in production pipelines

---

## Tech Stack
- Python
- pandas
- NumPy
- matplotlib
- scikit-learn

---

## Project Link

📂 **Notebook:** [Project 9: Gold Recovery Prediction with Machine Learning](https://holly-d-c.github.io/my-portfolio/Project_10_Integrated%20Project/Project_10_Gold.html)
