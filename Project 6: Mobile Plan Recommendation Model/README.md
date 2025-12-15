# 📱 Mobile Plan Recommendation Model

## Project Overview
Developed a predictive model for Megaline to recommend the optimal mobile plan (Smart or Ultra) for legacy subscribers. Using behavior data from subscribers who have switched to new plans, the goal was to build a classification model that achieves at least **75% accuracy** to improve customer satisfaction and reduce churn.

This project demonstrates end-to-end machine learning workflow: data preparation, model training, hyperparameter tuning, validation, and final model selection.

---

## Business Objectives
- Analyze legacy subscriber behavior to predict optimal plan choice
- Achieve minimum 75% accuracy threshold for production deployment
- Compare multiple classification algorithms to find the best performer
- Ensure model generalization through proper train-test validation
- Provide actionable recommendations for customer retention strategy

---

## Data Description
The dataset includes subscriber behavior metrics:

| Feature | Description |
|---------|-------------|
| `calls` | Number of calls made |
| `minutes` | Total call duration in minutes |
| `messages` | Number of text messages sent |
| `mb_used` | Internet traffic used in MB |
| `is_ultra` | Plan type (0 = Smart, 1 = Ultra) - **Target Variable** |

**Dataset Size:** 3,214 subscribers  
**Target:** Binary classification (`is_ultra`)  
**Features:** All other columns (calls, minutes, messages, mb_used)

---

## Methodology

### Plan of Action
1. Load the dataset
2. Split source data into training, validation, and test sets
3. Investigate quality of different models
4. Optimize models through hyperparameter tuning
5. Validate final model for production readiness

### Data Splitting Strategy
- **Training Set:** 60% (used for model learning)
- **Validation Set:** 20% (used for hyperparameter tuning)
- **Test Set:** 20% (used for final evaluation)

Final evaluation used an **80:20 train-test split** to assess generalization.

---

## Model Development

### Models Evaluated
1. **Decision Tree Classifier**
2. **Random Forest Classifier**
3. **Logistic Regression**

### Hyperparameter Tuning

#### Decision Tree
**Tested Parameters:**
- `max_depth`: Range tested to find optimal tree complexity

**Best Configuration:**
- `random_state=12345`
- `max_depth=3`

**Performance:**
- Validation Accuracy: **78.5%**
- Test Accuracy: **77.9%**

---

#### Random Forest (SELECTED MODEL ✅)
**Tested Parameters:**
- `max_depth`: Tested multiple values (optimal = 6, Accuracy = 80.1%)
- `n_estimators`: Tested multiple values (optimal = 48, Accuracy = 79.2%)

**Best Configuration:**
- `random_state=12345`
- `max_depth=6`
- `n_estimators=48`

**Performance:**
- Training Accuracy: **82.8%**
- Test Accuracy: **79.8%**
- Train-Test Gap: **3.1%** (excellent generalization)

---

#### Logistic Regression
**Tested Parameters:**
- `solver`: Tested multiple solvers (optimal = 'lbfgs', Accuracy = 71.1%, Gap = 0.2%)
- `C`: Regularization strength (optimal = 0.01, Accuracy = 75.6%, Gap = 0.27%)

**Best Configuration:**
- `random_state=12345`
- `solver='lbfgs'`
- `C=0.01`
- `max_iter=1000`

**Performance:**
- Test Accuracy: **73.9%**

---

## Model Performance Comparison

| Model | Test Accuracy | Train-Test Gap | Meets Threshold (75%)? |
|-------|---------------|----------------|------------------------|
| **Random Forest** | **79.8%** | **3.1%** | ✅ **Yes** |
| Decision Tree | 77.9% | ~4.6% | ✅ Yes |
| Logistic Regression | 73.9% | ~1.0% | ❌ No |

---

## Key Findings

### Random Forest: Superior Performance
- **Highest accuracy** (79.8%) among all models tested
- **Excellent generalization** with only 3.1% gap between training and test
- **Stable predictions** across multiple validation splits
- **Exceeds business requirement** of 75% accuracy threshold

### Model Insights
- **Random Forest** balances complexity and generalization effectively
- **Decision Tree** performs well but slightly lower accuracy
- **Logistic Regression** falls short of the 75% threshold, indicating the relationship between features and plan choice is non-linear

### Feature Importance
The model successfully leverages subscriber behavior patterns:
- Call volume and duration
- Messaging frequency
- Data usage patterns

These features collectively predict whether a customer would benefit from the Smart or Ultra plan.

---

## Business Recommendations

### Deployment Strategy
**Recommended Model:** Random Forest (`max_depth=6`, `n_estimators=48`)

**Rationale:**
- Achieves **79.8% accuracy**, exceeding the 75% threshold
- Demonstrates **minimal overfitting** (3.1% gap)
- Provides **reliable predictions** on unseen customer data
- **Production-ready** with proven stability

### Implementation Impact
- **Improved customer satisfaction** through accurate plan recommendations
- **Reduced churn** by matching customers to appropriate plans
- **Increased revenue** from better plan-to-usage alignment
- **Automated decision-making** for legacy subscriber migration

### Next Steps
1. Deploy Random Forest model to production environment
2. Monitor model performance on live customer data
3. Implement A/B testing to measure business impact
4. Schedule periodic retraining as new behavior data accumulates
5. Consider feature engineering for potential accuracy improvements

---

## Tools & Technologies

- **Python**
- **scikit-learn**
- **pandas**
- **Jupyter Notebook**

---

## Conclusion

This project successfully developed a machine learning solution that **predicts customer plan preferences with 79.8% accuracy**, exceeding the business requirement of 75%. The Random Forest model demonstrates excellent generalization and is recommended for production deployment to optimize Megaline's customer plan recommendations and improve overall satisfaction.

---

## Project Link

📂 **Notebook:** [Mobile Plan Recommendation Model Project](https://holly-d-c.github.io/my-portfolio/Project_7_Intro_to_ML/Sprint_7_Intro_to_ML.html)
