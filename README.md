# Experiment-13
Experiment 13

**Student Name:** Naman Bothra
**PRN:** 25070123078
**Experiment No:** 13

### 1. Aim
To perform data cleaning and pre-processing tasks using Python’s `pandas` and `numpy` libraries, specifically focusing on handling missing values, data type conversion, normalization of strings, and date-time formatting.

### 2. Theory
Data Wrangling is the process of transforming and mapping data from one "raw" data form into another format with the intent of making it more appropriate and valuable for a variety of downstream purposes such as analytics.
* **Missing Data:** Represented as `NaN` (Not a Number). It can be handled by deletion (`dropna`) or imputation (`fillna`).
* **Imputation:** Filling missing values using statistical measures like the **mean** (average), **median** (middle value), or **mode** (most frequent).
* **Coercion:** Forcing data into a specific type (e.g., converting a string "-" to a numeric type) using `pd.to_numeric`.
* **Standardization:** Ensuring consistency in categorical data (e.g., converting "cse" and "CSE" to a single format).

### 3. Logic
The logic follows a systematic cleaning pipeline:
1.  **Identification:** Use `.isna()` to locate "holes" in the dataset.
2.  **Substitution:** Replace non-standard missing markers (like `-`) with standard `np.nan`.
3.  **Type Correction:** Ensure columns meant for math (`Age`, `Marks`) are numeric, and dates are in `datetime` format.
4.  **Imputation:** Use the Mean for `Age` (as it's continuous) and Median for `Marks` (to avoid the influence of outliers).
5.  **Normalization:** Use string methods to capitalize text for uniform grouping.

### 4. One-Liner Code Explanations
* `df1.isna().sum()`: Returns the count of missing values for each column.
* `df1.dropna()`: Removes all rows that contain at least one missing value.
* `df1.fillna(value=df1.mean())`: Replaces `NaN` values with the average value of that specific column.
* `df.replace("-", np.nan, inplace=True)`: Globally swaps a dash symbol with a recognized null value.
* `pd.to_numeric(..., errors='coerce')`: Converts data to numbers, turning unconvertible items into `NaN`.
* `df["Age"].fillna(df["Age"].mean())`: Specifically targets the Age column to fill gaps with the mean.
* `df["Department"].str.upper()`: Converts all text in the Department column to uppercase to ensure consistency.
* `pd.to_datetime(..., dayfirst=True)`: Standardizes various date formats into a single YYYY-MM-DD format.

### 5. Algorithm
1.  **Import** `pandas` and `numpy`.
2.  **Create/Load** the DataFrame containing inconsistent data (missing values, mixed types).
3.  **Detect Nulls** using `isna()` to assess the extent of data loss.
4.  **Clean Symbols:** Replace placeholder strings (like "-") with `np.nan`.
5.  **Convert Types:** Cast columns to `float` or `int` using `to_numeric` with coercion.
6.  **Handle Missingness:** * Calculate the mean/median of the column.
    * Use `fillna()` to plug the holes with these statistical values.
7.  **Format Strings:** Use `.str.upper()` to fix case-sensitivity issues in categorical columns.
8.  **Format Dates:** Convert strings to formal `datetime` objects for time-based analysis.
9.  **Output** the final cleaned DataFrame.

### 6. Conclusion
In this experiment, I successfully implemented data wrangling techniques to transform a "dirty" dataset into a structured format ready for analysis. I learned that handling missing data requires careful selection between dropping rows or imputing values to maintain data integrity. Furthermore, I observed how standardized strings and date formats are crucial for accurate grouping and time-series operations.

---
