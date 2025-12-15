# 🏥 Insurance Benefit Prediction & Data Obfuscation

## Overview
Evaluated the feasibility of applying machine learning at *Sure Tomorrow Insurance* to improve customer targeting, predict benefit usage, and protect sensitive personal data — **without sacrificing model performance**.

**Goal:** Improve predictive accuracy while ensuring customer data privacy and regulatory safety.

---

## Key Results 🚀

✅ **Accurate predictions with guaranteed privacy preservation**

- **kNN Classification:** **4.7× F1-score improvement** over dummy baseline after feature scaling
- **Linear Regression:** RMSE = **0.34**, R² = **0.66**
- **Data Obfuscation:** Identical model performance before and after anonymization
- **Privacy-Safe Modeling:** Personal data rendered unrecoverable without transformation key

---

## Why This Approach Works

| Task | Method | Outcome |
|----|----|----|
| Customer targeting | kNN (scaled) | F1 = **0.94** |
| Benefit count prediction | Linear Regression | RMSE = **0.34** |
| Privacy protection | Matrix obfuscation | **No performance loss** |

**Key Insight:**  
Distance-based models require feature scaling for fairness and accuracy, while linear regression is inherently scale-invariant. Matrix-based obfuscation preserves linear relationships, allowing full privacy protection without degrading predictions.

---

## Methodology (Brief)
- Feature scaling applied to distance-based models (kNN)
- Linear Regression used for benefit count prediction
- Data obfuscation via invertible matrix transformation (`X' = X × P`)
- Mathematical and empirical validation of prediction invariance

---

## Business Impact
- Enables **privacy-compliant ML deployment**
- Improves customer targeting accuracy
- Protects sensitive demographic and financial data
- Demonstrates how regulation and performance can coexist

---

## Tech Stack
- Python
- pandas
- NumPy
- scikit-learn

---

## Project Link

📂 **Notebook:** [Project 10: Insurance Benefit Prediction & Data Obfuscation](https://holly-d-c.github.io/my-portfolio/Project_11/Project_11_Linear%20Algebra.html)
