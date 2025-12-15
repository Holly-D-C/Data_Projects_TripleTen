# 💼 Startup & Investment SQL Analysis

## Project Overview
This project leverages SQL to analyze startup performance, funding activity, acquisitions, geographic trends, and influencer networks using a unified database schema. The goal is to uncover actionable insights that support investor decision-making, risk analysis, and marketing outreach.

Acting as a data analyst for a venture capital firm, I designed and executed complex SQL queries to solve 10 real-world business problems using startup funding and acquisition data.

---

## Business Objectives
- Quantify startup success and failure rates across the ecosystem
- Identify high-performing sectors and geographic investment opportunities
- Analyze acquisition strategies during economic recovery periods
- Support marketing outreach by identifying industry influencers
- Classify venture fund activity levels and investment strategies
- Explore correlations between employee education and startup outcomes

---

## Data Description
The dataset includes multiple interconnected tables:
- **Companies:** Startup profiles, status, and founding information
- **Funding Rounds:** Investment amounts, dates, and round types
- **Acquisitions:** Acquisition details, pricing, and terms
- **People:** Individual profiles, social media handles, and affiliations
- **Education:** Employee education levels and institutions
- **Funds:** Venture fund information and investment portfolios

**Schema:** Relational database with foreign key relationships  
**Analysis Period:** Multi-year startup ecosystem data

---

## Key Analyses Performed

### 1. Startup Landscape Analysis
**Objective:** Measure baseline success rates by counting failed versus surviving companies.

**Key Findings:**
- Quantified the number of startups that closed down
- Established ecosystem-wide failure rate benchmarks

---

### 2. Sector Analysis for US Investors
**Objective:** Identify funding trends in US-based news/media companies to benchmark investment potential.

**Approach:**
- Listed total funding raised by US news and media companies
- Sorted results from highest to lowest funding amounts

**Business Impact:** Provides investors with sector-specific funding benchmarks

---

### 3. Cash Acquisition Trends (2011–2013)
**Objective:** Calculate total value of cash-based acquisitions during the post-recession recovery period.

**Key Findings:**
- Measured acquisition activity during economic recovery
- Focused specifically on cash-only transactions
- Analyzed trends from 2011 to 2013

**Business Impact:** Reveals acquisition strategies during market stabilization

---

### 4. Industry Influencer Identification
**Objective:** Find individuals with strong social branding for marketing outreach.

**Approach:**
- Identified users with "Silver" in their Twitter handles
- Compiled names and usernames for partnership opportunities

**Business Impact:** Supports targeted influencer marketing campaigns

---

### 5. Finance Influencer Analysis
**Objective:** Target finance-focused influencers for FinTech campaigns.

**Criteria:**
- Twitter handles containing "money"
- Last names starting with "K"

**Business Impact:** Provides marketing team with relevant FinTech contacts

---

### 6. Geographic Investment Analysis
**Objective:** Rank countries by total venture funding raised to highlight top global markets.

**Key Findings:**
- Calculated total capital raised per country
- Identified highest-funded regions globally

**Business Impact:** Guides international investment strategy and market prioritization

---

### 7. Funding Round Volatility
**Objective:** Detect unusual market activity by analyzing gaps between smallest and largest funding rounds per date.

**Approach:**
- Identified dates with significant funding disparities
- Excluded zero or identical values
- Highlighted potential market anomalies

**Business Impact:** Supports risk analysis and market timing decisions

---

### 8. Fund Activity Classification
**Objective:** Categorize venture funds based on investment activity levels.

**Categories:**
- **High Activity:** Funds investing in many companies
- **Middle Activity:** Moderate investment portfolio size
- **Low Activity:** Focused or emerging funds

**Business Impact:** Helps identify co-investment partners aligned with strategic preferences

---

### 9. Investment Strategy by Fund Activity
**Objective:** Compare average funding rounds per company across activity categories.

**Key Findings:**
- Measured depth vs. breadth of fund engagement
- Analyzed whether active funds diversify or concentrate investments

**Business Impact:** Reveals fund investment philosophies and strategies

---

### 10. Employee Education & Startup Success
**Objective:** Explore whether employee education levels correlate with startup failure.

**Approach:**
- Identified startups that failed after one funding round
- Linked employees to education records
- Calculated average degrees per employee

**Business Impact:** Uncovers potential correlations between education and startup outcomes

---

## Technical Implementation

### SQL Techniques Used
- Complex `JOIN` operations across multiple tables
- Aggregate functions (`COUNT`, `SUM`, `AVG`)
- Subqueries and Common Table Expressions (CTEs)
- Window functions for ranking and partitioning
- `CASE` statements for classification logic
- Date filtering and range queries
- String pattern matching (`LIKE`, `ILIKE`)
- `GROUP BY` and `HAVING` clauses

### Database Schema
- Worked with a multi-table relational database
- Utilized foreign key relationships for data integration
- Referenced provided ER diagram for query design

---

## Key Insights

### Startup Ecosystem
- Established baseline failure rates for ecosystem benchmarking
- Identified sector-specific funding patterns in news/media

### Acquisition Trends
- Post-recession period (2011–2013) showed specific cash acquisition patterns
- Provides context for current acquisition strategy planning

### Geographic Markets
- Certain countries dominate global venture funding
- Regional analysis reveals emerging vs. established markets

### Influencer Networks
- Identified key individuals for marketing partnerships
- Targeted finance-specific influencers for FinTech outreach

### Fund Behavior
- Funds exhibit distinct investment strategies (depth vs. breadth)
- Activity level classification aids in partner selection

### Education & Success
- Analyzed correlation between employee education and startup outcomes
- Results inform talent acquisition strategies

---

## Business Recommendations
- Focus investments on sectors with proven funding traction
- Monitor funding round volatility for market timing insights
- Partner with funds whose activity levels align with portfolio strategy
- Leverage influencer networks for targeted marketing campaigns
- Consider employee education levels as one factor in due diligence
- Prioritize geographic markets with strong funding ecosystems

---

## Tools & Technologies
- **SQL** (PostgreSQL/MySQL compatible queries)
- **Database Design** (ER Diagram analysis)
- **Data Analysis** (Complex joins, aggregations, window functions)

---

## Project Link

📂 **Notebook:** [Project 5: Startup & Investment SQL Analysis Project](https://holly-d-c.github.io/my-portfolio/Project_6_SQL/Startup_and_Investment_SQL_Analysis_Project.pdf)


