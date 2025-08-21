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
