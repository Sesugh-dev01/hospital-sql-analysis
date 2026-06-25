# Hospital Patient SQL Analysis

SQL-driven analysis of a hospital patient database to answer real business questions about patient demographics, conditions, and admission trends.

## Business Questions Answered

1. **What is the most common condition?** — Diabetes affects 2 out of 5 patients, making it the leading diagnosis.
2. **What is the average patient age?** — The average age across all patients is 44 years.
3. **Who are the oldest and youngest patients?** — James (61) is the oldest; Chidi (28) is the youngest — a 33-year age range.
4. **Which condition affects older patients?** — Heart Disease patients average 58 years old, vs 38 for Diabetes patients.
5. **What was the busiest admission month?** — January 2024 had the highest admissions with 2 patients.

## Tools Used
Python · SQLite · Pandas · Jupyter Notebook

## Setup
```bash
pip install pandas jupyter
jupyter notebook hospital_patient_analysis.ipynb
```

## Project Structure
```
hospital-sql-analysis/
├── hospital_patient_analysis.ipynb   # Full analysis notebook
├── requirements.txt                  # Dependencies
└── README.md                         # This file
```

## Key Skills Demonstrated
- Database creation and schema design with SQLite
- SQL queries: SELECT, WHERE, GROUP BY, ORDER BY, AVG, COUNT, SUBSTR
- Presenting SQL results as plain-English business insights
- Connecting SQL databases to Python with pandas
