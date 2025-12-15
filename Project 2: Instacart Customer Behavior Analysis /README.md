# Instacart Customer Behavior Analysis (EDA)

## Overview
This project explores customer purchasing behavior using Instacart’s open-source grocery ordering dataset. Through extensive exploratory data analysis (EDA), the goal was to uncover patterns in order timing, basket size, product popularity, and customer reordering behavior to better understand how customers interact with the Instacart platform.

## Objective
Analyze customer orders to identify:
- When customers place orders
- How many items they buy per order
- Which products are most popular and most frequently reordered
- Customer loyalty patterns through reorder rates

## Dataset
- ~480,000 orders
- ~50,000 products
- Multiple relational tables (orders, products, order_products)

## Key Questions Explored
- What times of day and days of the week are busiest for orders?
- How many orders does a typical customer place?
- What are the most popular and most reordered products?
- How large are typical shopping baskets?
- Which products are added to carts first?
- What proportion of products are reorders (by product and by customer)?

## Methodology
- Cleaned and validated datasets (handled missing values, verified joins, checked distributions)
- Merged relational tables using appropriate keys
- Grouped and aggregated data to compute customer- and product-level metrics
- Visualized distributions using histograms and bar charts to identify trends
- Interpreted behavioral patterns rather than reporting raw counts

## Key Insights
- **Peak order times** occur around **10 AM and 3 PM**, with weekend patterns differing from weekdays.
- Most customers place **1–10 total orders**, with sharp drop-off after the first order.
- Typical orders contain **5–6 items**, with most orders falling between **1 and 20 items**.
- **Produce and dairy** dominate:
  - Most popular products
  - Most frequently reordered items
  - Items most often added to the cart first
- Many products show **high reorder rates**, indicating staple purchasing behavior.
- Some customers reorder **nearly 100%** of their items, suggesting automated or habitual ordering patterns.

## Tools & Technologies
- Python
- pandas
- matplotlib
- Jupyter Notebook

## Skills Demonstrated
- Exploratory Data Analysis (EDA)
- Data cleaning and validation
- Relational data joins
- Aggregation and grouping logic
- Visualization and insight communication
- Translating data patterns into business-relevant observations

## Conclusion
This analysis highlights strong habitual purchasing behavior among Instacart customers, with produce and dairy acting as core staples. Order timing and basket size patterns provide insights that could support inventory planning, personalized recommendations, and user experience optimization.

---

