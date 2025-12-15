# 🏦 Customer Churn Prediction (Supervised Learning)

## Overview
Built a supervised machine learning system to **predict customer churn** for *Beta Bank*, enabling proactive retention strategies and reducing customer acquisition costs.

**Goal:** Achieve **F1 ≥ 0.59** while maintaining strong generalization to unseen customers.

---

## Key Results 🚀

✅ **Production-ready churn prediction model selected**

- **Best Model:** Random Forest (downsampling strategy)
- **F1 Score:** **0.601** (exceeds requirement)
- **AUC-ROC:** **0.844**
- **Best generalization** across multiple validation strategies
- Robust performance on imbalanced data (~20% churn rate)

---

## Why This Model?

| Model Strategy | Test F1 | Generalization |
|--------------|--------|----------------|
| **Downsampling RF** | **0.601** | **Best ✅** |
| Upsampled RF | 0.589–0.596 | Moderate |
| Simple Upsampled RF | 0.600 | Moderate |
| Alternate Upsampled RF | 0.593 | Overfit ❌ |

**Key Insight:**  
Downsampling avoids artificial data duplication, allowing the model to learn **authentic customer behavior patterns**, resulting in more stable performance on unseen data.

---

## Methodology (Brief)
- Cleaned and encoded customer demographic and behavioral data
- Addressed missing values and class imbalance
- Evaluated multiple Random Forest variants using:
  - 60:20:20 (train/validation/test)
  - 80:20 (train/test) splits
- Optimized decision threshold for maximum F1
- Selected model based on **generalization, not peak score**

---

## Business Impact
- Identifies **at-risk customers before churn**
- Supports **targeted retention campaigns**
- Reduces acquisition costs by improving retention
- Provides reliable predictions suitable for production use

---

## Tech Stack
- Python
- pandas
- NumPy
- scikit-learn
- matplotlib

---

## Project Link

📂 **Notebook:** [Project 7: Retention Analytics with Machine Learning Project](https://holly-d-c.github.io/my-portfolio/Project_8_ML_Revised/Project_8_ML_Supervised_Learning_VS_new.html)
