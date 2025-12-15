# 🛒 Instacart Customer Behavior Analysis (EDA)

## Overview
Explored **customer purchasing behavior** on the Instacart platform using open-source grocery order data.  
**Goal:** Identify patterns in order timing, basket size, product popularity, and reorder behavior to inform business decisions and improve customer experience.

---

## Key Results 🚀

✅ **Order Timing**
- Peak order hours: **10 AM** and **3 PM**  
- Weekends show distinct ordering patterns compared to weekdays  

✅ **Customer Behavior**
- Most customers place **1–10 orders**, sharp drop after first order  
- Reorder rates reveal **habitual purchasing**, with some customers reordering nearly 100% of items  

✅ **Basket Size**
- Typical order contains **5–6 items**, most between 1–20 items  

✅ **Product Insights**
- **Produce and dairy** dominate popularity and reorder frequency  
- Items frequently added to carts first are often staples  
- High reorder rates indicate strong habitual buying patterns  

---

## Business Questions Addressed

| Question | Insight |
|----------|---------|
| When do customers place orders? | Peaks at 10 AM & 3 PM; weekends differ |
| How many orders per customer? | Most have 1–10 total orders |
| Basket composition | Typical baskets: 5–6 items |
| Most popular products | Produce & dairy dominate |
| Reordering patterns | High reorder rates indicate staple habits |
| First-added items | Staples are often added first |

---

## Methodology

1. **Data Cleaning & Validation**
   - Handled missing values  
   - Verified table joins and distributions  

2. **Data Integration**
   - Merged multiple relational tables (`orders`, `products`, `order_products`)  

3. **Aggregation & Metrics**
   - Computed customer- and product-level statistics  
   - Calculated reorder rates, basket sizes, and first-added products  

4. **Visualization**
   - Histograms, bar charts, and line plots to identify trends  

5. **Behavioral Interpretation**
   - Focused on translating patterns into actionable business insights  

---

## Business Impact

- **Inventory Planning:** Anticipate peak ordering times and popular products  
- **Personalized Recommendations:** Suggest frequently reordered items  
- **UX Optimization:** Improve checkout and cart placement based on habitual patterns  
- **Customer Retention:** Understand loyalty behaviors for targeted promotions  

---

## Tools & Technologies

- Python
- pandas
- matplotlib
- Jupyter Notebook

---

## Skills Demonstrated

- Exploratory Data Analysis (EDA)  
- Data cleaning and validation  
- Relational joins and aggregation  
- Data visualization  
- Translating data into actionable business insights  

---

## Project Link

📂 Notebook: [Project 2: Instacart Customer Behavior Analysis (EDA)](https://holly-d-c.github.io/my-portfolio/Project_2/Project_2_EDA_Instacart.html)
