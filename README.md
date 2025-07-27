# Customer Data Cleaning Project

A Python notebook for cleaning and preprocessing raw customer data from ABC Retail Corporation's 2023 sales channels.

---

## Table of Contents

- [Introduction](#introduction)
- [Scenario and Problem Statement](#scenario-and-problem-statement)
- [Dataset Description](#dataset-description)
- [Actions and Approach](#actions-and-approach)
- [Screenshots and Examples](#screenshots-and-examples)
- [Technologies Used](#technologies-used)
- [Project Structure](#project-structure)
- [Results and Insights](#results-and-insights)
- [Future Work](#future-work)
- [Contact Information](#contact-information)

---

## Introduction

This project demonstrates a practical approach to cleaning and standardizing real-world customer data using Python and pandas. The goal is to prepare a reliable dataset for downstream analytics and business intelligence.

---

## Scenario and Problem Statement

ABC Retail Corporation collected raw customer data from various sales channels in 2023. The dataset contains inconsistencies, missing values, and formatting issues, making it unreliable for analysis. The objective is to clean and standardize the data to enable accurate customer segmentation, sales trend analysis, and targeted marketing.

---

## Dataset Description

- **Source:** `data/Raw_Data_Customer_2023.xlsx`
- **Records:** 23 customer entries
- **Fields:**
  - `ID`
  - `First Name`
  - `Last Name`
  - `Gender`
  - `Age`
  - `Birthday`
  - `Items Sold`
  - `Email`
  - `Phone Number`
- **Issues:**
  - Unnormalized text (e.g., inconsistent casing)
  - Null values
  - Duplicates
  - Formatting errors (dates, phone numbers)
  - Outliers in numeric fields

---

## Actions and Approach

- **Load Data:** Read the Excel file into a pandas DataFrame.
- **Standardize Text:** Convert names and gender to uppercase, normalize gender values.
- **Date Formatting:** Convert `Birthday` to pandas datetime.
- **Email Imputation:** Fill missing emails using a placeholder pattern based on name fields.
- **Outlier Handling:** Use `RobustScaler` to detect and replace outliers in numeric columns with the mean.
- **Missing Value Imputation:** Fill missing numeric values with the mean.
- **Phone Normalization:** Remove country codes and formatting from phone numbers.
- **Remove Duplicates:** Ensure unique records.

---

## Screenshots and Examples

### Raw Data Preview (Before Cleaning)

| ID     | First Name | Last Name | Gender | Age  | Birthday   | Items Sold | Email                | Phone          |
| ------ | ---------- | --------- | ------ | ---- | ---------- | ---------- | -------------------- | -------------- |
| 573819 | LIAM       | Garcia    | Male   | 13.0 | 1990-05-10 | 18.0       | liam.g@example.com   | +63 9274836192 |
| ...    | ...        | ...       | ...    | ...  | ...        | ...        | ...                  | ...            |

### Cleaned Data Preview (After Cleaning)

| ID     | First Name | Last Name | Gender | Age  | Birthday   | Items Sold | Email                  | Phone      |
| ------ | ---------- | --------- | ------ | ---- | ---------- | ---------- | ---------------------- | ---------- |
| 573819 | LIAM       | GARCIA    | MALE   | 29.0 | 1990-05-10 | 18.0       | liam.g@example.com     | 9274836192 |
| ...    | ...        | ...       | ...    | ...  | ...        | ...        | ...                    | ...        |

---

## Technologies Used

- Python 3.x
- pandas
- numpy
- scikit-learn
- Jupyter Notebook

---

## Project Structure

**raw-customer-data**

- **data/**
  - Raw_Data_Customer_2023.xlsx
- **notebooks/**
- data_cleaning_customer_2023.ipynb

---

## Results and Insights

- Produced a clean, normalized dataset ready for analytics.
- Standardized text, dates, and phone numbers.
- Imputed missing values and handled outliers.
- Improved data quality for downstream business intelligence.

---

## Future Work

- Add automated unit tests for data validation.
- Integrate with data visualization tools for reporting.
- Explore advanced imputation and outlier detection techniques.
- Automate the pipeline for regular data updates.

---

## Contact Information

For questions or suggestions, please contact:

- **Email:** [reynaldoiii.castillo@gmail.com]
- **LinkedIn:** Reynaldo III Castillo - [LinkedIn](https://www.linkedin.com/in/reynaldo-iii-castillo-975120303)

---
