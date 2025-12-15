# 🎮 Video Game Sales Forecasting

## Overview
Analyzed **historical video game sales** to identify platform, genre, and regional trends for **Ice**, an online game retailer.  

**Goal:** Inform advertising, production, and platform strategies by uncovering patterns that drive commercial success.

---

## Key Results 🚀

✅ **Actionable Insights**

- **Top Platforms:** PS2, PS3, Xbox 360 generate highest global sales  
- **Consistent Lifecycle:** PC platform shows long-term stability  
- **Top Genres:** Action, Sports, Shooter  
- **Regional Preferences:** RPGs dominate in Japan; Action/Sports in NA & Europe  
- **Score Correlation:** Critic scores correlate moderately with sales (r ≈ 0.39), user scores weakly (r ≈ 0.11)  
- **Forecasted Platform Life:** Wii, PS3, X360 → 2017; 3DS → 2019; WiiU/PSV → 2023; PS4/Xbox One → 2025

---

## Why This Analysis?

| Domain | Metric / Approach | Business Impact |
|--------|-----------------|----------------|
| Platform | Total & average sales | Identify profitable platforms for investment |
| Genre | Sales by genre & region | Tailor development and marketing strategy |
| Region | Regional sales distributions | Optimize localization and releases |
| Ratings | Critic vs. user scores | Allocate marketing resources effectively |
| Lifecycle | Platform lifespan modeling | Plan future releases & inventory |

---

## Methodology (Brief)

1. **Data Cleaning & Preprocessing**
   - Standardized columns and types  
   - Imputed missing critic/user scores and ESRB ratings  
   - Removed incomplete records for statistical analysis  

2. **Exploratory Data Analysis**
   - Platform and genre sales trends  
   - Regional sales comparisons  
   - Visualizations: histograms, bar charts, line plots  

3. **Statistical Testing**
   - Hypothesis testing for platform and genre user score differences  
   - Example: Xbox One vs PC → significant difference (p < 0.01)  

4. **Platform Lifecycle Forecasting**
   - Modeled console lifecycles (5–10 years)  
   - Predicted out-of-market years for major platforms  
   - Identified PC as a stable outlier

---

## Business Impact
- **Advertising Focus:** Prioritize Action, Sports, Shooter games on top-performing platforms  
- **Regional Strategy:** Target RPGs for Japan; M-rated games for Europe  
- **Platform Planning:** PS4/PS5 and Xbox focus for global campaigns; maintain PC for long-term stable revenue  
- **Score-Driven Insights:** Leverage critic reviews for predictive marketing campaigns

---

## Tools & Technologies
- Python
- pandas
- NumPy
- matplotlib
- SciPy
- Jupyter Notebook

---

## Project Link

📂 Notebook: [Project 4: Video Game Sales Forecasting](https://holly-d-c.github.io/my-portfolio/Project_5_Video_Games/video_game_sales_project_5.html)
