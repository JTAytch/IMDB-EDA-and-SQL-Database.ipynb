# 🎬 Movie Data ETL & SQL Analysis

> **Blurb:** End‑to‑end data pipeline turning raw IMDb datasets into a clean, enriched PostgreSQL database with an embedded SQL showcase. Designed for full reproducibility, portability, and clear portfolio presentation.

---

## 📌 Project Overview

This project demonstrates a complete ETL pipeline — from extracting and cleaning IMDb data to enriching it with external API data, and finally loading it into PostgreSQL for analysis.  

The emphasis throughout is on **clarity, reproducibility, and professional polish** so another analyst (or recruiter) can clone the repo, run the notebooks, and explore the database without friction.

---

## 🛠 Tech Stack

- **Python**: pandas, SQLAlchemy, psycopg2-binary  
- **PostgreSQL**  
- **Jupyter Notebooks**  
- **TMDb API** for budget/revenue/certification enrichment

---

## 📂 Repository Structure

```text
📁 data/                # Intermediate and cleaned CSVs (compressed where possible)
📁 notebooks/           
    ├── Part0_Extract_Clean.ipynb
    ├── Part1_EDA_IMDb.ipynb
    ├── Part2_TMDb_API_Enrichment.ipynb
    ├── Part3_ETL_PostgreSQL_SQL_Showcase.ipynb
📁 docs/                # (Optional) ERDs, visuals, or charts
README.md
```


## 🧩 Workflow Summary

### **Part 0 – Extract & Clean**
- Pulled `title.basics` and `title.ratings` TSV files from IMDb.
- Filtered to valid movie records with runtime, release year, and genre data.
- Normalized genres into lookup/join tables for relational structure.
- Compressed cleaned outputs to keep the repo lightweight.

### **Part 1 – Exploratory Data Analysis**
- Initial profiling of the IMDb dataset.
- Checked distributions, missing values, and baseline trends to guide enrichment.

### **Part 2 – TMDb API Enrichment**
- Connected to TMDb with a locally stored API key (`~/.secret/TMDB_api.json`, ignored by Git).
- Added budget, revenue, and MPAA certification for proof‑of‑concept years (2000–2001).
- Merged results into combined CSV for downstream use.
- Graceful‑fail handling so the notebook runs even without API access.

### **Part 3 – PostgreSQL ETL + SQL Showcase**
- Auto‑created `movies` database and tables if missing.
- Loaded all cleaned and enriched datasets into a normalized schema.
- Built a unified `movies` table via joins.
- Wrote a SQL showcase covering:
  - Aggregations by genre
  - Top‑N filtering
  - Multi‑table joins
  - Window functions (Top 3 titles per genre)

---

## 📊 SQL Showcase Highlights
- **Top 10** highest‑rated movies
- **Average ratings** by genre
- **Best movie** in each genre (by rating)
- Join of IMDb ratings with TMDb popularity
- Genre title counts
- **ROW_NUMBER()** usage for Top 3 per genre
