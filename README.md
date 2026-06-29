# Hospital Patient Analysis — SQL Portfolio Project

SQL analysis of 55,500 patient admissions from the Kaggle Healthcare Dataset. Raw CSV data is normalised into 5 relational tables and loaded into SQLite, then queried using joins, aggregations, window functions, and CTEs to answer real operational questions.

## Database Schema

```
patients    (patient_id PK, name, age, gender, blood_type)
doctors     (doctor_id PK, doctor_name)
hospitals   (hospital_id PK, hospital_name)
admissions  (admission_id PK, patient_id FK, doctor_id FK, hospital_id FK,
             date_of_admission, discharge_date, admission_type,
             room_number, medical_condition, test_results)
billing     (billing_id PK, admission_id FK,
             insurance_provider, billing_amount, medication)
```

## Business Questions Answered

| # | Question | SQL Techniques |
|---|---|---|
| Q1 | Which medical conditions drive the longest stays and highest costs? | JOIN · AVG · JULIANDAY · GROUP BY |
| Q2 | How does billing vary by insurance provider? | JOIN · SUM · AVG · MIN · MAX · GROUP BY |
| Q3 | Which patients were readmitted — and what keeps bringing them back? | CTE · COUNT() OVER PARTITION BY · GROUP_CONCAT |
| Q4 | How have monthly admissions trended, and what is the MoM change? | CTE · STRFTIME · LAG() OVER ORDER BY |
| Q5 | Which doctors handle the most patients, ranked within each condition? | CTE · RANK() OVER PARTITION BY |

## Key Skills Demonstrated
- Relational schema design — normalising a flat CSV into 5 linked tables with primary and foreign keys
- SQL window functions: `LAG()`, `RANK()`, `COUNT() OVER PARTITION BY`
- Common Table Expressions (CTEs) for readable multi-step queries
- Date arithmetic with `JULIANDAY` for length-of-stay calculations
- Connecting SQLite to Python with pandas `read_sql()`

## Tools Used
Python · SQLite · Pandas · Matplotlib · Jupyter Notebook

## Dataset
[Kaggle Healthcare Dataset](https://www.kaggle.com/datasets/prasad22/healthcare-dataset) — prasad22 · 55,500 rows · synthetic but realistic patient records (2019–2024)

## Setup
```bash
pip install -r requirements.txt
jupyter notebook hospital_patient_analysis.ipynb
```

Run all cells in order (Kernel → Restart & Run All). The notebook creates the database automatically from the CSV — no separate setup needed.
