# 📱 Mobile Plan Revenue Analysis

## Overview
Analyzed **customer usage and revenue generation** for two prepaid mobile plans — **Surf** and **Ultimate** — to determine which plan drives higher revenue and understand usage patterns.  

**Goal:** Provide actionable insights to optimize plan offerings and pricing strategy.

---

## Key Results 🚀

✅ **Revenue Insights**
- **Ultimate plan:** Higher and more predictable monthly revenue  
- **Surf plan:** Generates revenue volatility due to frequent data overages (~41% of overage revenue comes from internet usage)  
- **Calls & texts:** Minimal contribution to overage revenue  
- **Regional differences:** NY–NJ users generate significantly different revenue than other regions  

---

## Why This Analysis?

| Business Question | Metric / Approach | Key Finding |
|------------------|-----------------|-------------|
| Revenue by Plan | Welch’s t-test | Ultimate > Surf (p = 1.37e-21) |
| Usage Patterns | Aggregated call, text, internet usage | Surf exceeds data limits more often |
| Revenue by Region | Welch’s t-test | NY–NJ differs significantly (p = 0.038) |

---

## Methodology (Brief)

1. **Data Preparation**
   - Converted dates to datetime  
   - Aggregated monthly usage per user (calls, texts, internet in GB)  
   - Rounded usage according to billing rules  
   - Merged with plan and user data  
   - Replaced missing usage with zeros  

2. **Revenue Calculation**
   - Calculated overage charges (calls, texts, internet)  
   - Added base plan fee  
   - Ensured negative overages were set to zero  

3. **Exploratory Data Analysis**
   - Usage distribution comparisons by plan  
   - Monthly trends visualization (histograms, boxplots, line charts)  
   - Service-specific revenue contributions  

4. **Statistical Testing**
   - Revenue differences by plan: Welch’s t-test, α = 0.01, p = 1.37e-21 → **significant**  
   - Revenue differences by region: Welch’s t-test, α = 0.05, p = 0.038 → **significant**

---

## Business Impact
- **Upsell Strategy:** Encourage heavy Surf users to switch to Ultimate for more predictable revenue  
- **Plan Optimization:** Adjust Surf pricing or data limits to reduce volatility  
- **Marketing Opportunities:** Tailor messaging to regions with higher overage revenue  
- **Revenue Forecasting:** Predictable revenue streams support operational planning

---

## Tools & Technologies
- Python
- pandas
- NumPy
- Matplotlib
- SciPy
- Jupyter Notebook

---

## Project Link

📂 Notebook: [Project 3: Mobile Plan Revenue Analysis](https://holly-d-c.github.io/my-portfolio/Project_3/Project_3_Phone_Plan.html)
