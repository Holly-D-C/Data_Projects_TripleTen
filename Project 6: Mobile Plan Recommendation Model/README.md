# 📱 Mobile Plan Recommendation Model

## Overview
Developed a machine learning model for *Megaline* to recommend the optimal mobile plan (Smart or Ultra) for legacy subscribers, improving **customer satisfaction** and reducing churn.

**Goal:** Achieve **≥75% accuracy** on unseen subscriber data.

---

## Key Results 🚀

✅ **Random Forest selected as best model**

- **Test Accuracy:** 79.8% (exceeds 75% threshold)  
- **Train-Test Gap:** 3.1% (excellent generalization)  
- **Stable predictions** across validation splits  
- **Features leveraged:** call volume/duration, messaging frequency, data usage

---

## Why Random Forest?

| Model | Test Accuracy | Train-Test Gap | Meets Threshold? |
|-------|---------------|----------------|----------------|
| **Random Forest** | **79.8%** | 3.1% | ✅ |
| Decision Tree | 77.9% | 4.6% | ✅ |
| Logistic Regression | 73.9% | 1.0% | ❌ |

**Insight:** Random Forest balances accuracy and generalization, while simpler models either underperform or fail to capture non-linear patterns.

---

## Methodology (Brief)
- Preprocessed subscriber behavior data (calls, minutes, messages, data usage)  
- Handled train-validation-test splits (60:20:20 and 80:20 for generalization)  
- Tested multiple models: Decision Tree, Random Forest, Logistic Regression  
- Hyperparameter tuning for optimal performance  
- Selected Random Forest based on **accuracy, generalization, and stability**

---

## Business Impact
- Recommends the **best plan for each legacy subscriber**  
- Reduces churn by aligning plan to usage patterns  
- Improves customer satisfaction and retention  
- Automates plan recommendation process for scalable deployment

---

## Tech Stack
- Python
- pandas
- NumPy
- scikit-learn
- Jupyter Notebook

---

## Project Link

📂 **Notebook:** [Project 6: Mobile Plan Recommendation Model Project](https://holly-d-c.github.io/my-portfolio/Project_7_Intro_to_ML/Sprint_7_Intro_to_ML.html)
