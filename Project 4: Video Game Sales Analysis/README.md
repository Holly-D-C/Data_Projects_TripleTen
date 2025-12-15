# 🎮 Video Game Sales Forecasting

## Project Overview
This project analyzes historical video game sales data to identify patterns that determine a game’s commercial success.  
Acting as a data analyst for the online store **Ice**, the goal was to uncover platform, genre, regional, and rating trends to inform future advertising and production strategies.

The analysis combines exploratory data analysis, statistical testing, and predictive reasoning to support business-driven decision-making.

---

## Business Objectives
- Identify which platforms and genres consistently generate high sales
- Understand how regional preferences differ across markets
- Evaluate the impact of critic and user scores on total sales
- Predict platform life cycles and future market viability

---

## Data Description
The dataset includes:
- Game titles, release years, platforms, and genres
- Regional sales (North America, Europe, Japan, Other)
- Critic scores, user scores, and ESRB ratings

**Time range:** 1980–2016  
**Target metric:** Total global sales

---

## Methodology

### 1. Data Cleaning & Preprocessing
- Standardized column names and corrected data types
- Addressed missing values in:
  - `critic_score`
  - `user_score`
  - `rating`
- Imputed missing ESRB ratings and release years where possible
- Filtered out incomplete records when required for statistical testing

---

### 2. Exploratory Data Analysis
- Analyzed release trends by year and decade
- Compared platform sales distributions and life cycles
- Evaluated genre performance across time and regions
- Examined regional market shares and platform dominance
- Visualized trends using histograms, bar charts, and line plots

---

### 3. Statistical Analysis & Hypothesis Testing

#### Hypothesis 1: Platform User Scores
- **H₀:** Average user ratings for Xbox One and PC are equal  
- **H₁:** Average user ratings differ between platforms  
- **Result:** p-value < 0.01 → **Reject H₀**

There is a statistically significant difference in user ratings between Xbox One and PC.

---

#### Hypothesis 2: Genre User Scores
- **H₀:** Average user ratings for Action and Sports genres are equal  
- **H₁:** Average user ratings differ between genres  
- **Result:** p-value ≈ 0.12 → **Fail to reject H₀**

No statistically significant difference in average user scores between Action and Sports genres.

---

### 4. Platform Lifecycle & Forecasting
- Identified typical console lifecycles of **5–10 years**
- Modeled growth and decline patterns by release year
- Forecasted out-of-market years for major platforms:
  - Wii, PS3, X360 → 2017
  - 3DS → 2019
  - WiiU, PSV → 2023
  - PS4, Xbox One → 2025
- Highlighted **PC** as an outlier with lower sales but the longest lifecycle

---

## Key Insights

### Platform Performance
- **Highest total sales:** PS2, PS3, Xbox 360
- **Most consistent lifecycle:** PC
- North America dominates global sales (~50%)

---

### Genre Performance
- **Top-performing genres:** Action, Sports, Shooter
- Shooter games rebounded strongly after 2008
- Role-Playing games dominate the Japanese market
- Platform and Shooter games achieve the highest average sales

---

### Regional Trends
- **North America:** Action, Sports, Shooter (E & E10+ ratings perform best)
- **Europe:** Action, Sports, Shooter, Racing (M-rated games generate higher average revenue)
- **Japan:** Strong preference for Role-Playing games; M-rated games underperform
- **Other regions:** Trends closely align with Europe

---

### Scores & Sales Relationship
- **Critic scores:** Moderate positive correlation with sales  
  - Pearson r ≈ 0.39
- **User scores:** Weak positive correlation  
  - Pearson r ≈ 0.11
- Critics provide more consistent and predictive scoring than users

---

## Business Recommendations
- Focus advertising on **Action, Sports, and Shooter** games
- Prioritize **PlayStation and Xbox** platforms for global releases
- Tailor game genres to regional preferences (RPGs for Japan)
- Consider producing more **M-rated games** for Europe and Other regions
- Maintain PC releases for long-term, stable revenue despite lower sales

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



