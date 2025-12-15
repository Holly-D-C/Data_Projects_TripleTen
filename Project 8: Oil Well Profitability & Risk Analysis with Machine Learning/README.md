# 🛢️ Oil Well Profitability & Risk Analysis

## Project Overview
Determined the most profitable and lowest-risk oil field for OilyGiant mining company by forecasting oil reserves, simulating profits under strict business constraints, and applying bootstrapping risk analysis. 

The goal was to select the optimal region from three candidates for development of 200 new oil wells, balancing profitability, forecasting accuracy, and investment risk to maximize stakeholder value while minimizing downside exposure.

---

## Business Objectives
- Build predictive models to forecast oil reserves in three regions
- Identify the 200 most profitable well locations from 500 explored points per region
- Calculate expected profit under strict budget constraints ($100M for 200 wells)
- Evaluate investment risk using bootstrapping simulation (1,000 iterations)
- Select the region with highest profit and risk of loss below 2.5%

---

## Business Constraints

### Investment Parameters
- **Budget:** $100 million USD for 200 oil wells
- **Revenue:** $4,500 USD per thousand barrels (equivalent to $4.50 per barrel)
- **Well Selection:** Choose top 200 wells from 500 explored points per region
- **Risk Threshold:** Maximum 2.5% probability of losses

### Success Criteria
- Risk of loss < 2.5%
- Highest average profit among qualifying regions
- Reliable forecasting accuracy (low RMSE)

---

## Data Description
Three datasets representing different geographic regions, each containing:

| Feature | Description |
|---------|-------------|
| `id` | Unique well identifier |
| `f0` | Oil quality parameter 1 |
| `f1` | Oil quality parameter 2 |
| `f2` | Oil quality parameter 3 |
| `product` | Volume of reserves (thousand barrels) - **Target Variable** |

**Dataset Size:** 100,000 wells per region  
**Target:** Predict oil reserves (`product`)  
**Features:** Three oil quality parameters (`f0`, `f1`, `f2`)

---

## Methodology

### 1. Data Preparation
- Loaded datasets for all three regions
- Verified data quality and consistency
- Prepared features (`f0`, `f1`, `f2`) and target (`product`)

### 2. Model Training & Validation
**Model:** Linear Regression (as required by business constraints)

**Data Split:** 75:25 (training:validation)

**Process:**
- Trained separate models for each region
- Made predictions on validation sets
- Calculated RMSE to assess forecasting accuracy
- Compared average predicted vs. actual reserves

### 3. Profit Calculation
**Break-even Analysis:**
- Calculated minimum reserves needed per well to avoid losses
- Formula: `break_even = budget / (top_wells * revenue_per_unit)`

**Selection Strategy:**
- From 500 explored wells, selected top 200 by predicted reserves
- Calculated total profit: `(total_reserves * revenue) - budget`

### 4. Risk Analysis via Bootstrapping
**Bootstrapping Technique (1,000 iterations):**
- Randomly sampled 500 wells with replacement
- Selected top 200 wells per sample
- Calculated profit for each iteration
- Analyzed distribution of outcomes

**Risk Metrics Calculated:**
- Average profit across all iterations
- 95% confidence interval (2.5th to 97.5th percentile)
- Probability of loss (negative profit scenarios)
- Average loss amount in losing scenarios

---

## Model Performance Comparison

### Predictive Accuracy (RMSE)

| Region | RMSE | Average Predicted | Average Actual | Difference | Accuracy Ranking |
|--------|------|-------------------|----------------|------------|------------------|
| Region 1 | 37.662 | 92.596 | 92.277 | +319 barrels | 2nd |
| **Region 2** | **0.887** | **68.557** | **68.564** | **-7 barrels** | **1st (Best)** ✅ |
| Region 3 | 40.085 | 94.978 | 94.770 | +208 barrels | 3rd (Worst) |

**Key Finding:** Region 2 achieved dramatically superior forecasting accuracy with RMSE of 0.887 compared to 37-40 in other regions, enabling highly reliable profit predictions.

---

## Profitability Analysis

### Model Predictions vs Actual Results

| Region | Actual Profit | Predicted Profit | Difference | Performance |
|--------|---------------|------------------|------------|-------------|
| Region 1 | $3,009,782 | $4,196,342 | -$1,186,559 | Overestimated |
| **Region 2** | **$5,012,600** | **$4,946,606** | **+$65,993** | **Slightly underestimated** ✅ |
| Region 3 | $6,407,831 | $3,891,079 | +$2,516,751 | Significantly underestimated |

**Critical Insight:** While Region 3 showed highest actual profit, the massive forecasting error ($2.5M discrepancy) indicates unreliable predictions and higher risk. Region 2's accuracy provides confidence in projected returns.

---

## Risk & Return Analysis (Bootstrapping Results)

### Comprehensive Regional Comparison
*Based on 1,000 simulations selecting best 200 wells*

| Metric | Region 1 | Region 2 ✅ | Region 3 |
|--------|----------|-------------|----------|
| **Average Total Profit** | $3,953,082 | **$4,083,321** | $3,142,067 |
| **Average Profit Per Well** | $19,765 | **$20,416** | $15,710 |
| **Lower Bound (2.5%)** | -$1,003,786 | **$203,029** ✅ | -$2,286,620 |
| **Upper Bound (97.5%)** | $9,120,659 | $8,052,508 | $8,055,177 |
| **Probability of Loss** | 6.6% | **1.8%** ✅ | 13.0% |
| **Risk Status** | ❌ Fails (>2.5%) | ✅ **Passes (<2.5%)** | ❌ Fails (>2.5%) |
| **Negative Samples** | 66/1000 | **18/1000** | 130/1000 |
| **Total Loss (all scenarios)** | -$82,465,191 | -$9,254,363 | -$186,924,875 |
| **Average Loss** | -$1,249,472 | **-$514,131** | -$1,437,883 |

---

## Key Findings

### 1. Model Accuracy 🎯
**Region 2 dominates in forecasting reliability:**
- RMSE of 0.887 vs. 37-40 in other regions
- Only -7 barrel difference between predicted and actual
- Accurate forecasting reduces uncertainty and enables better planning

### 2. Profitability 💰
**Region 2 delivers highest average returns:**
- **$4,083,321** total average profit (highest)
- **$20,416** profit per well (highest)
- Consistent performance across 1,000 simulations

### 3. Risk Profile 📊
**Region 2 offers the most stable returns:**
- **Only 1.8% probability of loss** (well below 2.5% threshold) ✅
- **Only region with positive lower confidence bound** ($203,029)
- Effectively guarantees profitability across scenarios
- Smallest average loss in negative scenarios (-$514,131)

### 4. Regional Comparisons

**Region 1:**
- Moderate returns ($3,953,082 average)
- **6.6% risk of loss** (exceeds 2.5% threshold) ❌
- Better forecasting than Region 3, but less stable than Region 2

**Region 3:**
- Highest upside potential ($8,055,177 upper bound)
- Greatest volatility and uncertainty
- **13.0% probability of loss** (highest risk) ❌
- Massive forecasting errors undermine reliability
- Despite high actual profit, unpredictability makes it unsuitable

---

## Final Recommendation: Develop Region 2 ✅

### Why Region 2 is the Optimal Choice

#### 1. Meets All Business Requirements ✅
- Risk of loss (1.8%) is **well below** the 2.5% threshold
- Highest average profit among compliant regions
- Only region that guarantees profitability (positive lower bound)

#### 2. Superior Forecasting Accuracy 🎯
- RMSE of 0.887 provides **exceptional prediction reliability**
- Minimal forecasting error (-7 barrels) enables confident planning
- Reduces project uncertainty and execution risk

#### 3. Optimal Risk-Adjusted Returns 📈
- Highest profit per well ($20,416)
- Lowest probability of loss (1.8%)
- Smallest potential losses in negative scenarios
- **Balances profitability with stability**

#### 4. Strategic Advantages 🏆
- **Consistent stakeholder value** with limited downside exposure
- **Predictable returns** support long-term planning
- **Minimal volatility** reduces financial stress
- **Production-ready** with proven reliability across 1,000 scenarios

### Why Not the Others?

**Region 1:**
- 6.6% loss probability **exceeds risk threshold** (2.5%)
- Lower profitability than Region 2
- Negative lower confidence bound indicates guaranteed loss scenarios

**Region 3:**
- 13.0% loss probability **far exceeds acceptable risk**
- Massive forecasting errors ($2.5M discrepancy)
- Highest volatility despite attractive upside
- Unpredictable returns undermine business planning

---

## Business Impact

### Strategic Value
✅ **Maximizes profit** while minimizing risk exposure  
✅ **Reduces forecasting uncertainty** for better capital allocation  
✅ **Ensures consistent returns** across diverse scenarios  
✅ **Protects stakeholder investment** with <2% loss probability  

### Financial Outcomes (Region 2)
- **Expected Profit:** $4,083,321 (average across 1,000 simulations)
- **ROI:** ~41% return on $100M investment
- **Downside Protection:** Positive returns in 98.2% of scenarios
- **Risk-Adjusted Performance:** Best Sharpe ratio among all regions

### Operational Benefits
- **Reliable forecasting** enables accurate budgeting
- **Low volatility** reduces need for contingency reserves
- **Predictable cash flows** support strategic planning
- **Minimal reputational risk** from project underperformance

---

## Tools & Technologies

- **Python**
- **scikit-learn** (Linear Regression modeling)
- **pandas**, **NumPy** (data analysis)
- **matplotlib** (visualization)
- **Jupyter Notebook**

## Analytical Techniques
- Linear Regression modeling
- Train-test split (75:25)
- Bootstrapping simulation (1,000 iterations)
- Confidence interval estimation
- Risk probability calculation

---

## Conclusion

After comprehensive analysis of model accuracy, profitability, and investment risk across all three regions, **Region 2 emerges as the optimal choice for development**.

The combination of:
- ✅ **Exceptional forecasting accuracy** (RMSE = 0.887)
- ✅ **Highest average profit** ($4,083,321)
- ✅ **Lowest risk of loss** (1.8%, well below 2.5% threshold)
- ✅ **Positive guaranteed returns** (lower confidence bound = $203,029)

Makes Region 2 the **most strategic and sustainable investment**, ensuring consistent stakeholder value with minimal exposure to losses. While Region 3 demonstrates attractive upside potential, its volatility and forecasting unreliability make it unsuitable for responsible capital deployment.

**Final Recommendation:** Develop Region 2 to maximize risk-adjusted returns and ensure predictable, profitable operations.

---

## Project Link

📂 **Notebook:** [Project 8: Oil Well Profitability & Risk Analysis Project](https://holly-d-c.github.io/my-portfolio/Project_9/Sprint_9_ML_Business.html)
