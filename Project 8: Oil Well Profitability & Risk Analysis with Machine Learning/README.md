# 🛢️ Oil Well Profitability & Risk Analysis

## Overview
Selected the most profitable and lowest-risk oil region for OilyGiant by forecasting oil reserves, simulating profits under strict budget constraints, and evaluating investment risk using bootstrapping.

**Goal:** Develop 200 oil wells with <$100M budget and <2.5% risk of loss.

---

## Key Results 🚀

✅ **Region 2 selected as optimal**

- **Average Profit:** $4.08M (highest among compliant regions)
- **Risk of Loss:** **1.8%** (below 2.5% threshold)
- **Forecast Accuracy:** RMSE = **0.887** (vs. 37–40 in other regions)
- **Guaranteed Profitability:** Positive lower confidence bound ($203K)

---

## Why Region 2?

| Metric | Region 1 | **Region 2** | Region 3 |
|------|---------|-------------|---------|
| Avg Profit | $3.95M | **$4.08M** | $3.14M |
| Loss Probability | 6.6% ❌ | **1.8% ✅** | 13.0% ❌ |
| RMSE | 37.7 | **0.887** | 40.1 |
| Risk Status | Fail | **Pass** | Fail |

Only Region 2 met **all business constraints**.

---

## Methodology (Brief)
- Linear Regression (per business requirement)
- Top-200 well selection from 500 candidates
- 1,000-iteration bootstrapping simulation
- Profit & risk evaluated under fixed budget constraints

---

## Business Impact
- Predictable, low-volatility returns
- 98.2% profitable scenarios
- Enables confident capital deployment
- Protects stakeholder investment

---

## Tech Stack
- Python
- pandas
- NumPy
- scikit-learn
- matplotlib

---

## Project Link

📂 **Notebook:** [Project 8: Oil Well Profitability & Risk Analysis Project](https://holly-d-c.github.io/my-portfolio/Project_9/Sprint_9_ML_Business.html)
