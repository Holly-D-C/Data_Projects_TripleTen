# Project 1: Data Analysis with Pandas — IMDb Movie Trends Analysis

## Overview

This project focuses on exploratory data analysis (EDA) and data cleaning using **pandas**. The goal was to transform a messy movie and TV show dataset into a clean, usable format and extract meaningful insights about IMDb ratings, actors, and release trends.

The project emphasizes **real-world data issues** such as inconsistent column names, encoding problems, missing values, and duplicated records—all common challenges in data science workflows.

---

## Business / Analytical Problem

Raw entertainment datasets often contain formatting errors and inconsistencies that make reliable analysis difficult. This project addresses:

* How to clean and standardize poorly formatted data
* How to extract actor- and title-level insights
* How to identify and categorize top-rated movies and shows

---

## Dataset

**Source:** `movies_and_shows.csv`

**Size:** 85,579 rows × 9 columns

**Key Features:**

* `name`: Actor or actress name
* `character`: Character played
* `role`: Role type (ACTOR / DIRECTOR)
* `title`: Movie or show title
* `type`: MOVIE or SHOW
* `release_year`: Year of release
* `genres`: List of genres
* `imdb_score`: IMDb rating
* `imdb_votes`: Number of IMDb votes

---

## Key Tasks & Methods

### 1. Data Cleaning & Standardization

* Renamed inconsistent and misspelled column names (e.g., `r0le` → `role`, `imdb sc0re` → `imdb_score`)
* Removed leading/trailing whitespace from column names
* Ensured consistent data types for analysis

### 2. Encoding & Data Correction

* Identified encoding-related name errors (e.g., `In??s Prieto`)
* Corrected corrupted text values using indexed updates
* Verified corrections to ensure data integrity

### 3. Exploratory Analysis

* Identified movies and shows with IMDb scores ≥ 9.0
* Extracted unique top-rated titles to avoid duplication
* Analyzed highly rated shows such as *Breaking Bad*, *Avatar: The Last Airbender*, and *Reply 1988*

### 4. Reusable Functions

Built reusable functions to support dynamic analysis:

* `get_unique_top_movies(min_score)` — returns unique titles above a given IMDb threshold
* `get_top_movies_from_decade(decade_start, min_score)` — retrieves top-rated titles by decade
* `get_actors_for_title(title)` — lists all actors in a given movie or show
* `categorize_imdb_score(title)` — categorizes titles as *Excellent*, *Good*, *Average*, or *Low*

### 5. IMDb Score Categorization

Titles were categorized based on IMDb score:

* **Excellent:** ≥ 9.0
* **Good:** 7.0 – 8.9
* **Average:** 5.0 – 6.9
* **Low:** < 5.0

---

## Key Findings

* High IMDb ratings are concentrated in TV shows rather than movies
* Top-rated content spans multiple decades, with strong representation in drama and crime genres
* Encoding issues can significantly impact grouping and filtering if not corrected

---

## Tools & Technologies

* **Python**
* **pandas**
* **Jupyter Notebook**

---

## Project Link

📂 Notebook: [Project 1: IMDb Movie Trends Analysis /Project_1.ipynb](https://holly-d-c.github.io/my-portfolio/Project_1/Project_1.html)


