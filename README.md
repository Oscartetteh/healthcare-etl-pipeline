# Healthcare ETL Pipeline
---

## Your Brief

**Company:** MedCore Analytics
**Client:** St. Aurelius General Hospital
**Your role:** Data Engineer

You have `raw-data.csv` from Module 03 — a messy extract of patient,
appointment, and billing data. The data has null values, duplicates,
impossible values, and wrong data types. Before any analysis or modelling
can happen, this data must be cleaned.

Your job is to build an ETL pipeline that reads the raw data, validates it,
transforms it, and saves a clean `processed-data.csv`.

**Input:** `data/raw/raw-data.csv` (from Module 03)
**Output:** `data/processed/processed-data.csv`

The pipeline must:
- **Extract:** load the raw CSV
- **Validate:** check for nulls, duplicates, invalid ranges, wrong types
- **Transform:** fill nulls with appropriate strategies, remove duplicates,
  fix data types, add derived columns (e.g. `age_from_dob`, `bill_collection_rate`)
- **Load:** save the clean data to `data/processed/processed-data.csv`

---
## Success Criteria

- [ ] `DataValidator` catches all data quality issues from the raw file
- [ ] `DataTransformer` fixes all issues using appropriate strategies
- [ ] `ETLPipeline` orchestrates extract → validate → transform → load
- [ ] `python run.py` produces `processed-data.csv` without crashing
- [ ] Unit tests cover at least 8 scenarios
- [ ] No hardcoded values — all settings come from `config.py`
- [ ] Project pushed to GitHub using the Module 04 branching workflow

---

# Healthcare ETL Pipeline

## Project Architecture

This project is designed as a modular ETL pipeline for cleaning messy healthcare data from St. Aurelius General Hospital. The pipeline reads raw patient, appointment, and billing data, validates data quality issues, transforms the data, and saves a clean processed dataset for future analysis or modelling.

The architecture follows this flow:

```text
Raw CSV File
data/raw/raw-data.csv
        |
        v
Extract Layer
ETLPipeline.extract()
        |
        v
Validation Layer
DataValidator
- Checks null values
- Checks duplicates
- Checks invalid ranges
- Checks wrong data types
- Checks unexpected negative values
        |
        v
Transformation Layer
DataTransformer
- Fills missing values
- Removes duplicate rows
- Fixes data types
- Corrects invalid values where appropriate
- Adds derived columns
  - age_from_dob
  - bill_collection_rate
        |
        v
Load Layer
ETLPipeline.load()
        |
        v
Processed CSV File
data/processed/processed-data.csv
        |
        v
Reporting Layer
ReportWriter
- Excel report
- Word report
- Transformation summary
- Data quality summary

# Project Structure

Healthcare_ETL_Pipeline/
│
├── data/
│   ├── raw/
│   │   ├── raw-data.csv
│   │   └── .gitkeep
│   │
│   └── processed/
│       ├── processed-data.csv
│       └── .gitkeep
│
├── reports/
│   ├── etl-report.xlsx
│   ├── etl-report.docx
│   └── .gitkeep
│
├── src/
│   ├── __init__.py
│   ├── etl_pipeline.py
│   ├── validator.py
│   ├── transformer.py
│   └── report_writer.py
│
├── tests/
│   ├── __init__.py
│   └── test_pipeline.py
│
├── config.py
├── run.py
├── requirements.txt
├── README.md
├── .gitignore
└── .env
