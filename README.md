# US Household Income – SQL Data Cleaning & Exploratory Analysis

This project focuses on cleaning and analyzing **US household income** data using **MySQL**, from raw Excel files to an analysis-ready table and insight-driven SQL queries.

It was built as **Project 2 – US Household Income** from Alex The Analyst’s *MySQL for Data Analytics* course on Analyst Builder, and is part of my growing SQL & data analytics portfolio.

![Lake Tahoe](https://github.com/iyanusol/US-Household-Income/raw/main/images/lake-tahoe.jpg)


---

## 🎯 Project Overview

The goal of this project was to:

- Import raw US household income datasets into MySQL
- Clean and standardize the data using **SQL only**
- Create an analysis-ready table for downstream reporting
- Explore income patterns across states, counties, and regions using SQL queries

![Water Area](https://github.com/iyanusol/US-Household-Income/raw/main/images/Water%20Area.png)


This project is intentionally **SQL-only** – no BI front-end – to demonstrate strong skills in:

- Data cleaning and transformation
- Writing efficient SQL
- Structuring analytical queries
- Documenting logic clearly for reproducibility

![Average Income By State](https://github.com/iyanusol/US-Household-Income/raw/main/images/Average%20Income%20By%20State.png)

---

## 📂 Dataset


Typical structure:

- **USHouseholdIncome.csv**
  - County-level income and demographic information
- **USHouseholdIncome_Statistics.csv**
  - Additional statistics and metadata for each area

![Data Cleaning - Delete Duplicates](https://github.com/iyanusol/US-Household-Income/raw/main/images/Data%20Cleaning%20-Delete%20Duplicates.png)


Key fields include:

- `State_Name`, `State_Code`, `County`, `City`
- `Type`, `ALand`, `AWater`, `Location`
- `Mean`, `Median` household income
- Additional statistics used for filtering and validation

---

## 🛠 Tools & Technologies

- **MySQL / MySQL Workbench**
- **SQL** (data cleaning + analysis)
- **VS Code** (for editing and organizing scripts)
- **Excel / CSV files** (source data)

---

![Areas](https://github.com/iyanusol/US-Household-Income/raw/main/images/Areas.png)


## 🧹 Data Cleaning (SQL Only)

All cleaning was performed in SQL. The main steps included:

- **Loading raw CSVs** into MySQL tables
- **Standardizing text fields**
  - Trimming spaces
  - Converting state/county names to consistent casing
- **Handling missing values**
  - Checking for NULLs across key columns
  - Deciding when to filter vs. impute vs. leave as-is
- **Fixing inconsistent categories**
  - Aligning `Type` values (e.g., removing typos or stray labels)
- **Removing duplicates**
  - Identifying duplicate rows by state, county, and city combinations
- **Validating numeric fields**
  - Ensuring income fields are numeric
  - Checking for impossible or extreme outliers
- **Creating a cleaned table**
  - Writing a `CREATE TABLE AS SELECT` (or INSERT INTO) with the cleaned, standardized data

![Data Cleaning](https://github.com/iyanusol/US-Household-Income/raw/main/images/Data%20Cleaning.png)


The full cleaning logic is documented in:

- `sql/us_household_income_data_cleaning.sql`

---

## 🔍 Exploratory Data Analysis (EDA)

Once the data was clean, I used SQL to explore key questions such as:

- **Which states have the highest and lowest median household income?**
- **How does income vary by region or state?**
- **Which counties stand out as outliers (very high or very low income)?**
- **What is the distribution of income across the US?**
- **Are there patterns between income and area type (urban, rural, etc.)?**

Example types of queries included:

- Ranking states by **average or median household income**
- Calculating **aggregates** by state, county, and region
- Identifying **top 10 / bottom 10** locations
- Using **GROUP BY**, **ORDER BY**, **HAVING**, and **window functions** (where appropriate)

![Data Import](https://github.com/iyanusol/US-Household-Income/raw/main/images/Data%20Import.png)

These queries are stored in:

- `sql/us_household_income_eda.sql`

---

## 📁 Repository Structure

```text
US-Household-Income-SQL-Project/
│
├── sql/
│   ├── us_household_income_data_cleaning.sql   # all cleaning steps
│   └── us_household_income_eda.sql             # analysis queries
│
├── data/                                       # optional (if license allows)
│   ├── USHouseholdIncome.csv
│   ├── USHouseholdIncome_Statistics.csv
│   └── us_household_income_cleaned.csv
│
└── README.md

