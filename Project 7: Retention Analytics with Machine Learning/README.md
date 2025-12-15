# 🏦 Customer Churn Prediction for Beta Bank

## Project Overview
Developed supervised learning models to predict whether customers from Beta Bank will leave the bank soon. Using historical data on client behavior and contract terminations, the goal was to build a model with **maximum F1 score (minimum 0.59)** to proactively identify at-risk customers and enable targeted retention campaigns.

This project addresses the critical business insight that **retaining existing customers is more cost-effective than acquiring new ones**. By accurately predicting churn, Beta Bank can implement strategic interventions to save customers before they leave.

---

## Business Objectives
- Predict customer churn with F1 score ≥ 0.59
- Understand why previous customers left the bank
- Enable proactive retention strategies
- Reduce customer acquisition costs through improved retention
- Measure model performance using F1, precision, recall, and AUC-ROC

---

## Data Description
The dataset includes customer information and banking behavior:

| Feature | Description |
|---------|-------------|
| `RowNumber` | Row index |
| `CustomerId` | Unique customer identifier |
| `Surname` | Customer last name |
| `CreditScore` | Credit score |
| `Geography` | Customer location (France, Spain, Germany) |
| `Gender` | Male/Female |
| `Age` | Customer age |
| `Tenure` | Years as bank customer |
| `Balance` | Account balance |
| `NumOfProducts` | Number of bank products used |
| `HasCrCard` | Has credit card (1 = Yes, 0 = No) |
| `IsActiveMember` | Active member status (1 = Yes, 0 = No) |
| `EstimatedSalary` | Estimated annual salary |
| `Exited` | Churned (1 = Yes, 0 = No) - **Target Variable** |

**Dataset Size:** 10,000 customers  
**Class Imbalance:** ~20% churn rate (significant imbalance requiring specialized techniques)  
**Missing Values:** 909 missing values in `Tenure` column

---

## Methodology

### Dual Data Splitting Strategy
To ensure robust model validation and generalization assessment:

**Strategy 1: 60:20:20 Split**
- **Training:** 60% (for model learning)
- **Validation:** 20% (for hyperparameter tuning)
- **Test:** 20% (for model selection)

**Strategy 2: 80:20 Split**
- **Training:** 80% (for final model training)
- **Test:** 20% (for generalization analysis and overfitting assessment)

### Data Preparation
- Handled missing values in `Tenure` column
- Encoded categorical features (`Geography`, `Gender`)
- Dropped irrelevant identifiers (`RowNumber`, `CustomerId`, `Surname`)
- Applied feature scaling using `StandardScaler`

### Addressing Class Imbalance
Given the ~20% churn rate, multiple sampling strategies were tested:
- **Upsampling:** Duplicate minority class samples
- **Downsampling:** Reduce majority class samples
- **Threshold Optimization:** Adjust classification threshold for optimal F1

### Hyperparameter Tuning
- Used `GridSearchCV` and `RandomizedSearchCV`
- Optimized RandomForest parameters:
  - `n_estimators`
  - `max_depth`
  - `max_features`
  - `min_samples_split`
  - `min_samples_leaf`

---

## Model Performance Comparison

### 1. Upsampled RF Model
**Configuration:**
- `RandomForestClassifier(max_depth=11, n_estimators=119, min_samples_split=8, random_state=12345)`
- Optimal Threshold: 0.46372

| Dataset | F1 | Precision | Recall | AUC-ROC |
|---------|----|-----------|---------|---------| 
| 60:20:20 Validation | 0.667 | 0.650 | 0.684 | 0.868 |
| 60:20:20 Test | 0.586 | 0.581 | 0.592 | 0.849 |
| 80:20 Train | 0.819 | 0.842 | 0.773 | 0.958 |
| 80:20 Test | 0.589 | 0.615 | 0.565 | 0.852 |

**Train-Test Gap:** 0.233 (80:20 split)

---

### 2. Alternate Upsampled RF Model
**Configuration:**
- `RandomForestClassifier(max_depth=12, n_estimators=37, min_samples_split=7, min_samples_leaf=3, random_state=12345)`
- Optimal Threshold: 0.41183

| Dataset | F1 | Precision | Recall | AUC-ROC |
|---------|----|-----------|---------|---------| 
| 60:20:20 Validation | 0.644 | 0.575 | 0.733 | 0.860 |
| 60:20:20 Test | 0.593 | 0.548 | 0.646 | 0.845 |
| 80:20 Train | 0.852 | 0.842 | 0.862 | 0.966 |
| 80:20 Test | 0.596 | 0.564 | 0.631 | 0.849 |

**Train-Test Gap:** 0.256 (80:20 split) - highest overfitting

---

### 3. Simple Upsampled and Tuned RF Model
**Configuration:**
- `RandomForestClassifier(max_depth=11, max_features='sqrt', min_samples_leaf=1, min_samples_split=11, n_estimators=93)`
- Optimal Threshold: 0.48336

| Dataset | F1 | Precision | Recall | AUC-ROC |
|---------|----|-----------|---------|---------| 
| 60:20:20 Validation | 0.665 | 0.666 | 0.664 | 0.868 |
| 60:20:20 Test | 0.573 | 0.622 | 0.531 | 0.839 |
| 80:20 Train | 0.805 | 0.878 | 0.742 | 0.952 |
| 80:20 Test | 0.600 | 0.653 | 0.555 | 0.850 |

**Train-Test Gap:** 0.205 (80:20 split)

---

### 4. Downsampling RF Model ✅ (RECOMMENDED)
**Configuration:**
- `RandomForestClassifier(n_estimators=54, max_depth=9, max_features=0.5, min_samples_leaf=1, min_samples_split=14, random_state=12345)`
- Optimal Threshold: 0.48954

| Dataset | F1 | Precision | Recall | AUC-ROC |
|---------|----|-----------|---------|---------| 
| 60:20:20 Validation | 0.664 | 0.632 | 0.699 | 0.866 |
| 60:20:20 Test | 0.588 | 0.607 | 0.570 | 0.845 |
| 80:20 Train | 0.736 | 0.836 | 0.658 | 0.919 |
| 80:20 Test | **0.601** | **0.636** | **0.570** | **0.844** |

**Train-Test Gap:** **0.135** (80:20 split) - **BEST generalization** ✅

---

## Performance Rankings

### 60:20:20 Test Set Performance (F1):
1. Alternate Upsampled RF: 0.593
2. **Downsampling RF: 0.588** ✅
3. Upsampled RF: 0.586
4. Simple Upsampled RF: 0.573

### 80:20 Test Set Performance (F1):
1. **Downsampling RF: 0.601** ✅ **(BEST)**
2. Simple Upsampled RF: 0.600
3. Alternate Upsampled RF: 0.596
4. Upsampled RF: 0.589

### Generalization Analysis (80:20 Train-Test Gap):
1. **Downsampling RF: 0.135** ✅ **(BEST generalization)**
2. Simple Upsampled RF: 0.205
3. Upsampled RF: 0.230
4. Alternate Upsampled RF: 0.256 (worst overfitting)

---

## Key Findings

### Performance Consistency
- **AUC-ROC scores:** Consistently strong (0.844-0.868) across all models, indicating reliable separation of positive and negative classes
- **Downsampling RF:** Most stable performance across different data split strategies
- **Data split impact:** 80:20 split showed different performance rankings than 60:20:20, with Downsampling and Simple Upsampled RF benefiting more from additional training data

### Critical Insight: Authentic Data Patterns
Unlike upsampled models that rely on artificially duplicated minority class samples, the **downsampling approach learns from genuine data patterns**, resulting in:
- Better generalization to unseen data
- Improved performance with more real training examples
- Lower risk of learning artificial patterns

---

## Final Recommendation: Downsampling RF Model

### Why Downsampling RF is the Optimal Choice

#### 1. Superior Generalization ⭐
- **Train-test gap of only 0.135** (dramatically better than alternatives: 0.205-0.256)
- Most consistent performance on truly unseen customer data
- Lowest risk of performance degradation in production

#### 2. Strong Performance Across Both Evaluation Methods
- **60:20:20 Split:** F1 = 0.588 (competitive)
- **80:20 Split:** F1 = 0.601 **(best performance)**
- **Validation Metrics:**
  - Precision = 0.632
  - Recall = 0.699 (catches **69% of churning customers**)
  - AUC-ROC = 0.866

#### 3. Learns from Authentic Data Patterns
- No artificial data duplication
- Learns genuine customer behavior patterns
- Demonstrates significant improvement with more real training data

#### 4. Production Advantages
- ✅ **Computational Efficiency:** Faster training and inference with smaller datasets
- ✅ **Stability:** Lowest risk of performance degradation
- ✅ **Reliability:** Most consistent predictions across different data conditions
- ✅ **Scalability:** Better performance with increased training data availability

---

## Model Specifications

### Final Production Model
```python
RandomForestClassifier(
    n_estimators=54,
    max_depth=9,
    max_features=0.5,
    min_samples_leaf=1,
    min_samples_split=14,
    random_state=12345
)
```

### Production Performance Metrics
- **Optimal Threshold:** 0.48954
- **F1 Score:** 0.601 (exceeds 0.59 requirement ✅)
- **Precision:** 0.636 (64% of predicted churners actually churn)
- **Recall:** 0.570 (57% of actual churners are caught)
- **AUC-ROC:** 0.844 (strong class separation)

### Confusion Matrix (80:20 Test Set)
```
                Predicted
                Not Churn  |  Churn
Actual -------------------------
Not Churn  |    1460     |   133
Churn      |     175     |   232
```

---

## Business Impact

### Strategic Advantages
✅ **Exceeds performance requirements:** F1 = 0.601 (target: 0.59)  
✅ **Proactive retention:** Identifies at-risk customers before they leave  
✅ **Cost optimization:** Retention campaigns are cheaper than new customer acquisition  
✅ **Reliable predictions:** Best generalization ensures sustainable performance  

### Operational Benefits
- **Consistent churn prediction accuracy** over time
- **Reduced model retraining frequency** due to stable performance
- **Reliable ROI** on customer retention campaigns
- **Minimized risk** of model performance degradation

### Customer Retention Strategy
The model enables Beta Bank to:
1. Identify the **top 20-30% highest-risk customers**
2. Deploy **targeted retention offers** (fee waivers, premium services, loyalty rewards)
3. **Monitor intervention effectiveness** through A/B testing
4. **Optimize retention budget allocation** by focusing on truly at-risk customers

---

## Tools & Technologies

- **Python**
- **scikit-learn**
- **pandas**, **NumPy**
- **matplotlib**
- **Jupyter Notebook**

---

## Conclusion

The comprehensive dual-split analysis demonstrates that the **Downsampling RandomForest** provides the optimal balance of performance and reliability for Beta Bank's customer churn prediction system. 

While other models may achieve marginally higher scores on specific test sets, the Downsampling RF's **exceptional generalization characteristics (0.135 train-test gap)** and **consistent performance across different evaluation strategies** make it the most trustworthy choice for sustainable business impact.

**Recommended Production Deployment:** Downsampling RandomForest with threshold optimization at 0.48954, delivering **robust and reliable customer churn predictions** for strategic business decision-making and cost-effective customer retention.

---

## Project Link

📂 **Notebook:** [Project 7: Retention Analytics with Machine Learning Project](https://holly-d-c.github.io/my-portfolio/Project_8_ML_Revised/Project_8_ML_Supervised_Learning_VS_new.html)
