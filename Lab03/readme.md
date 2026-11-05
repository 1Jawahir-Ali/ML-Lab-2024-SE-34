<div align="center">

# 🚗 Pakistan Used Cars: Data Cleaning & Analysis

**CS-3105 Machine Learning Lab · Lab 03 · Pandas for Data Manipulation and Cleaning**

![Python](https://img.shields.io/badge/Python-3.10+-3776AB?logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-Numerical-013243?logo=numpy&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter&logoColor=white)
![Status](https://img.shields.io/badge/Status-Completed-success)

</div>

---

## 📌 Overview

This lab cleans and analyses **24,973 real used-car ads** from OLX Pakistan (Open Data Pakistan, *Pakistan Used Cars*, 2021) using **Pandas**, with no Python loops over rows. The raw data contains missing values, inconsistent text, duplicates and impossible values, so it has to be cleaned before any analysis.

| | |
|---|---|
| **Name** | `Jawahir Ali` |
| **Roll No** | `2024-SE-34` |
| **Instructor** | Engr. Muhammad Awais |
| **Course** | CS-3105 Machine Learning Lab |

---

## 🗂️ Repository Structure

```
ML-Lab-2024-SE-34/
└── Lab03/
    ├── Lab03.ipynb                    # Main notebook (tasks 1–6)
    ├── pakistan_used_cars.csv         # Raw dataset
    ├── pakistan_used_cars_clean.csv   # Cleaned dataset (used in Lab 04)
    └── README.md
```

---

## 🧹 Data Cleaning Pipeline

Every one of the six common data problems was handled, in the correct order (text first, then duplicates):

| Problem | What was done |
|---|---|
| **Missing values** | Dropped ads without `Brand`/`Model`; filled `Registered City`, `Fuel` and `Transaction Type` with `"Unknown"` |
| **Formatting** | Stripped spaces, fixed city-name case, removed `Rs` and commas from `Price` |
| **Data types** | `Price` → `int64`, `Year` → `Int64` |
| **Inconsistent categories** | `Sukkar` → `Sukkur`, `Corrolla Altis` → `Corolla Altis` |
| **Duplicates** | Removed 2,028 exact duplicate ads |
| **Invalid values** | Set impossible `KMs Driven` to NaN; removed fake prices and unrealistic Suzuki/Daihatsu ads |

**Result:** `24,973 rows → 20,484 rows × 9 columns` ✅

---

## 📊 Key Findings

- 🏆 **Suzuki is the most advertised brand** (8,621 ads), ahead of Toyota and Honda.
- ⛽ **Hybrid cars have the highest median price** (≈ 16.3 lakh), while LPG and CNG cars are the cheapest.
- 📉 **A Corolla GLI loses about 1.4 lakh in value per year of age**, from ≈ 23.2 lakh (2018) to ≈ 12.3 lakh (2010).
- 💳 **Cash deals dominate** (19,634 ads, median 6.9 lakh) compared with installment/leasing (850 ads, median 3.0 lakh).

---

## ⚙️ Skills Demonstrated

`read_csv` · `loc` / `iloc` · Boolean filtering · `sort_values` · `groupby` · `value_counts` · `str` methods · `fillna` / `dropna` · `drop_duplicates` · type conversion · feature creation (`Price_lakh`, `Age`)

---

## 🚀 How to Run
# 2. Install dependencies
pip install pandas, numpy, jupyter

# 3. Open the notebook
jupyter notebook Lab03.ipynb

```
```
Or open it directly in **Google Colab** and upload `pakistan_used_cars.csv`. Then use **Runtime → Restart and run all**.

---

## 📚 Data Source

Open Data Pakistan, *Pakistan Used Cars* (OLX Pakistan ads, 2021).

---
<div align="center">

Made with ❤️ using Python & Pandas

</div>
