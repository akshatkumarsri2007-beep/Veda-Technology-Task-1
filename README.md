# Veda-Technology-Task-1: Data Cleaning and Preprocessing

## Objective
Clean a raw dataset (Titanic dataset) containing null values, duplicates, inconsistent formats, and incorrect data types, so it is ready for reliable analysis.

## Dataset
- **Source:** Titanic Dataset (`train.csv`)
- **Rows:** 891
- **Columns:** 12

## Tools Used
- Python
- Pandas
- Google Colab

## Data Quality Issues Found & How They Were Resolved

| Column     | Issue                          | Fix Applied                                                                 |
|------------|---------------------------------|------------------------------------------------------------------------------|
| `Age`      | 177 missing values (~20%)       | Imputed with the **median** age, since it's a numeric column and median is robust to outliers |
| `Cabin`    | 687 missing values (~77%)       | Filled with `"Unknown"` instead of dropping the column, to preserve the row count while flagging missing data |
| `Embarked` | 2 missing values                | Imputed with the **mode** (most frequent port), since only a very small number of rows were affected |
| Duplicates | Checked with `df.duplicated()`  | 0 duplicate rows found — no action needed |
| Data Types | Checked with `df.info()`        | All column data types (int64, float64, object) were already correct — no conversion needed |

## Process
1. Loaded the dataset into a Pandas DataFrame.
2. Ran `df.info()`, `df.isnull().sum()`, and `df.duplicated().sum()` to inventory all data quality issues before making any changes.
3. Handled missing values on a case-by-case basis (median for `Age`, flag value for `Cabin`, mode for `Embarked`) rather than applying one method to the whole dataset.
4. Re-ran the inventory checks (`df.isnull().sum()`) after cleaning to confirm all issues were resolved.
5. Exported the cleaned dataset as `cleaned_csv.csv`.

## Files in this Repository
- `train.csv` — original raw dataset
- `Veda_Technology_Task1.ipynb` — Colab notebook with all cleaning code
- `cleaned_csv.csv` — final cleaned dataset
- `README.md` — this write-up

## Outcome
After cleaning, the dataset has **zero missing values** across all columns and is ready for further analysis.
