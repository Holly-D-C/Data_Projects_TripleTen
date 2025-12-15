# 🎬 IMDb Movie & TV Show Trends Analysis

## Overview
Performed **exploratory data analysis (EDA)** and **data cleaning** on a messy IMDb dataset to extract insights on movie and TV show ratings, actors, and release trends.  
The project addresses **real-world data issues** such as inconsistent column names, encoding errors, missing values, and duplicates—common challenges in production-level data science.

---

## Objective 🎯
Transform raw IMDb data into a clean, analyzable format and answer key business questions:

- Which movies and shows are top-rated?
- Which actors appear in the highest-rated content?
- How do ratings and popularity vary over decades?
- How to standardize messy datasets for reliable analysis?

---

## Dataset 📊

**Source:** `movies_and_shows.csv`  
**Size:** 85,579 rows × 9 columns  

**Key Features:**

| Feature | Description |
|---------|-------------|
| `name` | Actor or actress name |
| `character` | Character played |
| `role` | Role type (ACTOR / DIRECTOR) |
| `title` | Movie or show title |
| `type` | MOVIE or SHOW |
| `release_year` | Year of release |
| `genres` | List of genres |
| `imdb_score` | IMDb rating |
| `imdb_votes` | Number of IMDb votes |

---

## Methodology 🛠

### 1. Data Cleaning & Standardization
- Renamed inconsistent columns (e.g., `r0le` → `role`, `imdb sc0re` → `imdb_score`)  
- Stripped whitespace from column names  
- Ensured consistent data types  

### 2. Encoding & Text Correction
- Corrected corrupted text entries (e.g., `In??s Prieto`)  
- Verified fixes to maintain data integrity  

### 3. Exploratory Data Analysis
- Identified titles with IMDb scores ≥ 9.0  
- Extracted unique top-rated titles to avoid duplication  
- Examined critically acclaimed shows (*Breaking Bad*, *Avatar: The Last Airbender*, *Reply 1988*)  

### 4. Reusable Analysis Functions
- `get_unique_top_movies(min_score)` — fetch unique titles above a score  
- `get_top_movies_from_decade(decade_start, min_score)` — top-rated titles by decade  
- `get_actors_for_title(title)` — list actors per title  
- `categorize_imdb_score(title)` — categorize as *Excellent*, *Good*, *Average*, or *Low*  

### 5. IMDb Score Categorization
| Category | IMDb Score |
|----------|------------|
| Excellent | ≥ 9.0 |
| Good | 7.0 – 8.9 |
| Average | 5.0 – 6.9 |
| Low | < 5.0 |

---

## Key Findings 📈
- **Top-rated content:** Higher concentration in TV shows than movies  
- **Decade trends:** Strong representation of drama and crime genres across decades  
- **Data quality impact:** Encoding issues can distort grouping and filtering if uncorrected  

---

## Business Impact 💡
- Enables identification of top-performing content for **recommendation systems**  
- Supports **actor and genre analytics** for content acquisition or licensing  
- Demonstrates methods to **clean and standardize messy datasets** for reliable analytics  

---

## Tools & Technologies
- Python  
- pandas  
- Jupyter Notebook  

---

## Project Link

📂 Notebook: [Project 1: IMDb Movie Trends Analysis /Project_1.ipynb](https://holly-d-c.github.io/my-portfolio/Project_1/Project_1.html)


