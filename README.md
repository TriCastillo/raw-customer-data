# Scenario Problem

ABC Retail Corporation recently collected raw customer data from various sales channels for the year 2023. This dataset, stored in an Excel file, includes key customer information such as `ID`, `First Name`, `Last Name`, `Gender`, `Age`, `Birthday`, `Items Sold`, `Email`, and `Phone Number`. However, the data is unprocessed and contains inconsistencies, missing values, and formatting issues that make it unreliable for analysis and reporting.

As part of the company's data quality improvement initiative, you are tasked with cleaning this dataset using Python. The goal is to prepare a clean and accurate version of the customer data that can be used for further analysis, such as customer segmentation, sales trend evaluation, and targeted marketing strategies. This involves detecting and handling missing values, correcting data types and formats, removing duplicates, and standardizing entries across all columns.

The success of this data cleaning project will directly impact the accuracy of business decisions and customer insights derived from the dataset.

# Action

The dataset consists of 23 records about customers. It contains inconsistencies such as unnormalized text, null values, and human errors.

Using the **pandas** library, the Excel file containing the customer data is read into a **pandas DataFrame** to facilitate data manipulation.

The **`DataFrame.replace()`** function is used to standardize inconsistent entries. It accepts a dictionary-like syntax where each key-value pair maps a value to be replaced with its standardized form.

**Example:**

```python
dataframe = dataframe.replace({"AbcD": "abcd", "EFGH": "efdh"})
```

The `Birthday` column is converted to a pandas `datetime` object to ensure consistent formatting and enable time-based operations.

Rows with missing values in the `Email` column are filled using the `dataframe['email'].fillna()` function. If the first name and the initial of the last name are available, a placeholder email is generated and normalized to lowercase.

A separate DataFrame is created to calculate the mean while **excluding null values**, to avoid introducing bias into the statistics.

Another DataFrame is created to isolate numeric and float data types using:

```python
dataframe.select_dtypes(include=[type1, type2])
```

This enables numerical operations, such as scaling, without interference from non-numeric columns.

To handle outliers and missing values in numeric columns:

* **Outliers** are excluded.
* **Null values** are imputed using the **mean** of their respective fields.

# Screenshots & Examples

### 🔍 Raw Data Preview (Before Cleaning)

> *Insert a screenshot of the original Excel data or a pandas `.head()` output here*

```markdown
![Raw Data](images/raw_data_preview.png)
```

### 🛠️ Cleaned Data Preview (After Cleaning)

```markdown
![Cleaned Data](images/cleaned_data_preview.png)
```

# Results

The results produced a clean and complete Excel dataset, following a normalized format and free from inconsistencies.

# Lesson

This project demonstrated how prone real-world data is to anomalies. To prevent null values or improperly formatted entries, systems should implement input validation to enforce data entry rules at the source.

Regarding imputation and outlier handling, if the statistical approach I used (mean imputation) is not ideal in some cases, I'm open to feedback and eager to learn better techniques for future scenarios.

