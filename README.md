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

> Build your project from scratch using the teaching project as your reference.
