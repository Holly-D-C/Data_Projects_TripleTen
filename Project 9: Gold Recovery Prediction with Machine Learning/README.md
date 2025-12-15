# 🥇 Gold Recovery Prediction using Machine Learning

## 📌 Overview
This project builds a **machine learning model to predict gold recovery rates** during the industrial flotation and purification process. Accurate predictions allow mining operations to **optimize chemical dosing**, **identify unprofitable operating conditions**, and **improve production efficiency** before processing full ore batches.

The solution focuses on **process-aware data preprocessing**, **leakage-safe modeling**, and **robust evaluation** using real-world industrial sensor data.

---

## 🎯 Objective
Predict:
- **Rougher gold recovery**
- **Final gold recovery**

using only features available **prior to and during flotation**, ensuring realistic deployment in production systems.

---

## ⭐ Key Results
- **Best Model:** Random Forest Regressor
- **Final sMAPE:** **11.48%**
- **Relative Error Reduction:** ~20% from baseline
- **Validated Recovery Formula MAE:** 9.3e-15 (near-perfect)

---

## 🧠 Key Features
- Conditional imputation preserving chemical and physical relationships
- Removal of **34 leakage-prone features**
- Detailed metal flow analysis (Au, Ag, Pb)
- Cross-validated model selection and tuning
- Production-ready preprocessing pipeline

---

## 📊 Dataset
- **Source:** Industrial flotation sensor data
- **Training Set:** 16,860 rows × 87 features
- **Test Set:** 5,856 rows × 53 features
- **Features include:**
  - Reagent levels (xanthate, sulfate, depressants)
  - Air flow and flotation bank states
  - Feed size and metal concentrations

---

## 🔍 Exploratory Analysis Highlights
| Metal | Key Finding |
|-----|------------|
| Gold (Au) | Proper enrichment (~5.7× increase) |
| Silver (Ag) | Rejected, not recovered (unsuitable target) |
| Lead (Pb) | Moderate enrichment (~2.9×) |

Zero values were identified as **measurement errors** and removed via imputation.

---

## 🧹 Data Preprocessing
### Leakage Prevention
- Removed output/calculation features unavailable at prediction time
- Dropped 9.06% of rows with missing target values

### Conditional Imputation Strategy
| Feature Group | Method | Outcome |
|--------------|--------|--------|
| Sulfates | Concentration-based fill | 99.2% pattern match |
| Xanthate | Direct copy (near-perfect correlation) | ~0 error |
| Air Flow | Range-restricted copying | 99.5% variance reduction |
| Feed Solids | Range-specific medians | Preserved distributions |
| Remaining (<1%) | Median fill | Negligible impact |

Train-test distributions remained aligned after preprocessing.

---

## 📐 Recovery Formula Validation
Gold recovery was validated using metallurgical formulas:

\[
Recovery = \frac{C \times (F - T)}{F \times (C - T)}
\]

Result: **Formula reconstruction MAE = 9.3e-15**

---

## 🤖 Model Training
### Models Evaluated
- Linear Regression
- Decision Tree Regressor
- Random Forest Regressor

### Model Comparison
| Model | sMAPE (%) |
|-----|-----------|
| Random Forest | **14.30** |
| Linear Regression | 14.64 |
| Decision Tree | 22.48 |

---

## ⚙️ Hyperparameter Tuning
Optimized via `GridSearchCV`:
- `max_depth = 5`
- `n_estimators = 100`

### Final Performance
| Metric | Value |
|------|------|
| **Final sMAPE** | **11.48%** |
| MAE | 5.51 |
| Relative Improvement | −2.82 pp |

---

## 💼 Business Impact
This model enables:
- **Process optimization** before batch execution
- **Chemical cost reduction**
- **Quality control alerts** for low-recovery conditions
- **Decision support** for production planning

The pipeline is **deployment-ready** and validated on unseen test data.

---

## 🚀 Installation & Usage
### Requirements
- Python 3.9+
- pandas
- NumPy
- matplotlib
- scikit-learn
