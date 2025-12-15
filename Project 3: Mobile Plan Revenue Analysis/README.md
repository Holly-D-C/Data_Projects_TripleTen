# 📱 Mobile Plan Revenue Analysis

## Project Overview
This project analyzes customer behavior and revenue generation for two prepaid mobile plans — **Surf** and **Ultimate** — to determine which plan produces higher revenue and how customer usage patterns differ.

The analysis evaluates calls, text messages, and mobile internet usage, aggregates monthly activity, calculates total revenue, and applies statistical hypothesis testing to support business decisions.

---

## Business Questions
1. Which prepaid plan generates more revenue — Surf or Ultimate?
2. How do customer usage patterns differ between plans?
3. Does customer location (NY–NJ vs. other regions) impact revenue?

---

## Data Description
The dataset includes:
- Call records (duration rounded up per call)
- Text message counts
- Internet usage sessions (MB converted to GB and rounded up)
- User demographics and geographic location
- Plan pricing, limits, and overage fees

All customer activity was aggregated at the **monthly level**.

---

## Methodology

### 1. Data Preparation
- Converted date columns to datetime format
- Aggregated monthly usage per user:
  - Call minutes
  - Text messages
  - Internet usage (GB)
- Rounded usage according to billing rules
- Merged usage data with plan and user information
- Replaced missing usage values with zeros

---

### 2. Revenue Calculation
For each user-month:
- Subtracted plan limits from actual usage
- Calculated overage charges for calls, texts, and internet
- Set negative overages to zero
- Added the base monthly plan fee

**Final metric:** `monthly_revenue`

---

### 3. Exploratory Data Analysis
- Compared usage distributions between Surf and Ultimate plans
- Visualized monthly trends using histograms, boxplots, and line charts
- Calculated descriptive statistics (mean, median, variance, standard deviation)
- Analyzed revenue contribution by service type

---

### 4. Statistical Hypothesis Testing

#### Hypothesis 1: Revenue by Plan
- **H₀:** Average monthly revenue is the same for Surf and Ultimate users  
- **H₁:** Average monthly revenue differs between plans  
- **Test:** Welch’s t-test  
- **α:** 0.01  

**Result:** p-value = 1.37e-21 → **Reject H₀**

There is a statistically significant difference in revenue between plans.

---

#### Hypothesis 2: Revenue by Region
- **H₀:** Average revenue is the same for NY–NJ users and other regions  
- **H₁:** Average revenue differs by region  
- **Test:** Welch’s t-test  
- **α:** 0.05  

**Result:** p-value = 0.038 → **Reject H₀**

Revenue differs significantly by region.

---

## Key Insights
- Internet usage is the primary driver of overage revenue (~41%)
- Surf users frequently exceed data limits, causing revenue volatility
- Ultimate users generate more predictable monthly revenue
- Calls and texts contribute minimally to total overage revenue

---

## Business Recommendations
- Encourage heavy Surf users to upgrade to the Ultimate plan
- Promote Ultimate’s higher data allowance to reduce bill shock
- Adjust Surf pricing or limits to improve revenue predictability
- Consider region-specific pricing or marketing strategies

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
