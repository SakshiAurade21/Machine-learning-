# 🧹 Data Cleaning in Python | Practice Notes

## 📌 Overview

While practicing Machine Learning projects, I encountered issues due to missing and inconsistent data. This motivated me to revisit and strengthen my understanding of **Data Cleaning in Python using Pandas**. This repository contains the key concepts, examples, doubts, and solutions I worked through using the dataset from Kaggle.

---

## 📊 Dataset Used

**Dataset Name**: Retail Store Sales (Dirty for Data Cleaning)
**Source**: [Kaggle](https://www.kaggle.com/datasets/rahulbhatia/retail-store-sales-dirty-for-data-cleaning)
**File Used**: `retail_store_sales.csv`

This dataset was intentionally created with "dirty" data, including:

* Missing values
* Duplicates
* Inconsistent formatting
* Misaligned columns


## ✅ Topics Practiced with Explanations & Doubts Solved

### 1. Detecting Missing Values

```python
data.isna()               # Shows True/False mask of missing values
data.isna().sum()         # Count of nulls per column
data['Item'].isnull().any()  # Checks if 'Item' column has any null
```

### 2. Filtering Rows with Nulls

```python
data[data['Item'].isna()]  # Rows where 'Item' is null
```

### 3. Handling Missing Values

#### Numerical Columns (e.g., Quantity, Total Sales, Price Per Unit)

* Use `mean()` if data is normally distributed (no major outliers)
* Use `median()` if outliers are present
* Use `mode()[0]` if values are repeated frequently

```python
data['Price Per Unit'].fillna(data['Price Per Unit'].mean(), inplace=True)
```

#### Boolean Columns (e.g., InStock)

* Use `mode()[0]` to fill with the most common value (True or False)

```python
data['InStock'].fillna(data['InStock'].mode()[0], inplace=True)
```

#### Categorical Columns (e.g., Item, Store Name)

* Use `mode()[0]` for most frequent value
* Or fill with a placeholder like `'Unknown'`

### 4. inplace=True

* When used in methods like `fillna()` or `drop_duplicates()`, it modifies the original DataFrame directly without needing assignment.

```python
data.fillna(value, inplace=True)
```

### 5. Common Error Faced and Solution

```text
TypeError: unsupported operand type(s) for +: 'float' and 'method'
```

* Cause: Forgot parentheses when calling `.mean`
* Fix: Always call functions like `.mean()` not `.mean`

### 6. Removing Duplicates

```python
data.duplicated().sum()              # Number of duplicates
data.drop_duplicates(inplace=True)  # Removes duplicates
```

To simulate duplicates:
(data does not have any duplicate value so write this line to copy first 5 lines)
```python
data = pd.concat([data, data.iloc[:5]])
```

### 7. Checking for Nulls After Fill

```python
data['Price Per Unit'].isnull().any()  # Should return False
```

---

# 🧹 Data Cleaning Practice: Retail Store Sales Dataset

**📁 Folder Name:** `Data_Cleaning_Retail_Store_Sales`

**📊 Dataset Used:**
Retail Store Sales (Dirty for Data Cleaning)
**Path:** `/kaggle/input/retail-store-sales-dirty-for-data-cleaning/retail_store_sales.csv`

---

## 📌 Background

While practicing machine learning, I encountered issues related to dirty data. So, I decided to revisit and practice core data cleaning concepts using a messy retail store dataset.

---

## ✅ Topics Covered (till now)


### 🟡 2. Data Type Conversions

* `astype()` usage:

  * Convert string to float: `data['Quantity'] = data['Quantity'].astype('float')`
  * Convert to datetime (if clean): `data['Date'] = data['Date'].astype('datetime64[ns]')`
  * Safer datetime conversion: `pd.to_datetime(data['Date'], errors='coerce')`
* Difference between `astype()` vs `pd.to_datetime()`
* `errors='coerce'` explanation: invalid values become `NaN`

### 🟡 3. Dropping Unnecessary Columns

* Dropping a column: `data.drop('Transaction Date', axis=1, inplace=True)`
* Confirming `axis=1` is for columns and `axis=0` for rows

### 🟡 4. Working with Date Columns

* Splitting date span into start and end:

  ```python
  data['First_date'] = data['Warranty_Period'].str.split('to').str[0]
  ```
* Treated as string for easy splitting
* Will work on creating synthetic date columns if not available

### 🟡 5. Duplicate Values

* Checking duplicates: `data.duplicated().sum()`
* Removing duplicates: `data.drop_duplicates(inplace=True)`

---

## 🔧 Coming Up Tomorrow

* More date column manipulations
* Feature engineering from date fields
* Detecting and handling outliers
* String normalization (case, spaces, typos)



## 📊 Summary

Today, I covered the essential concepts of data cleaning in Python using Pandas. This included:

* Checking and handling missing values
* Choosing the correct measure (mean/median/mode) based on data type and distribution
* Handling boolean and categorical nulls
* Using `inplace=True` to directly update DataFrame
* Identifying and removing duplicate rows
* Understanding common errors and fixing them

