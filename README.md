# Task 1 - Data Cleaning and Preprocessing

## Internship
Elevate Labs | Data Analyst Internship | Ministry of MSME, Govt. of India

---

## Objective
Clean and prepare a raw dataset by handling missing values, fixing incorrect
data types, removing duplicates, and standardising column formats using Python (Pandas).

---

## Dataset
- **Name:** Amazon Product Reviews
- **Source:** Kaggle
- **Original size:** 1,465 rows × 16 columns
- **Cleaned size:** 1,465 rows × 17 columns (1 new column added)

---

## Tools Used
- Python 3.12
- Pandas library
- Jupyter Notebook / VS Code

---

## Files in This Repository

| File | Description |
|------|-------------|
| `amazon.csv` | Original raw dataset (uncleaned) |
| `data_cleaning.py` | Python script with all cleaning code |
| `amazon_cleaned.csv` | Final cleaned dataset |
| `Task1_DataCleaning_Report.docx` | Full summary report of changes made |

---

## Problems Found in Raw Data

| # | Column | Problem |
|---|--------|---------|
| 1 | discounted_price | Had ₹ symbol and commas — stored as text |
| 2 | actual_price | Had ₹ symbol and commas — stored as text |
| 3 | discount_percentage | Had % symbol — stored as text |
| 4 | rating_count | Had comma formatting — stored as text |
| 5 | rating_count | 2 missing (null) values |
| 6 | rating | 1 missing (null) value |
| 7 | category | Deeply nested values, no top-level category |

---

## Cleaning Steps Performed

1. Loaded dataset and explored using `df.shape`, `df.dtypes`, `df.isnull().sum()`
2. Standardised all column names to lowercase with underscores
3. Filled 2 missing values in `rating_count` with `0`
4. Filled 1 missing value in `rating` with the column median
5. Removed `₹` and commas from price columns → converted to `float`
6. Removed `%` from `discount_percentage` → converted to `int`
7. Removed commas from `rating_count` → converted to `int`
8. Checked for duplicates using `drop_duplicates()` — 0 found
9. Extracted top-level category into new column `main_category`
10. Saved final output as `amazon_cleaned.csv`

---

## Result

- ✅ 0 missing values remaining
- ✅ All numeric columns have correct data types
- ✅ 0 duplicate rows
- ✅ New column added for easier analysis
- ✅ Original file preserved, cleaned file saved separately
