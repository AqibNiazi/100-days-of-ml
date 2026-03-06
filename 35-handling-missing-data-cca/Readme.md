# Lecture 35 – Handling Missing Values using Complete Case Analysis

## Introduction

Handling missing data is an important step in data preprocessing and feature engineering. Real-world datasets often contain missing values due to data collection errors, system failures, incomplete surveys, or data integration problems.

Most machine learning models cannot work with missing values directly. Therefore, appropriate techniques must be applied before training models.

## Techniques for Handling Missing Data

Several common techniques are used to handle missing values in datasets.

**Complete Case Analysis (CCA)**
Remove rows that contain missing values.

**Mean / Median / Mode Imputation**
Replace missing values with statistical measures such as mean, median, or mode depending on the variable type.

**Arbitrary Value Imputation**
Replace missing values with a constant value such as `-999`, `0`, or `"Unknown"`.

**End of Distribution Imputation**
Replace missing values using extreme values from the distribution.

**Random Sample Imputation**
Replace missing values with randomly selected values from the existing data.

**Missing Indicator Method**
Create a binary variable indicating whether the original value was missing.

Example:

```
Age_missing = 1 if Age is missing else 0
```

**Predictive Model Imputation**
Use machine learning models to estimate missing values. Examples include KNN imputation and regression-based imputation.

## Complete Case Analysis (CCA)

Complete Case Analysis is one of the simplest methods for handling missing data.

In this method, rows containing any missing values are removed from the dataset. Only observations with complete information across all variables are kept for analysis.

Example dataset:

| Age | Salary | City      |
| --- | ------ | --------- |
| 25  | 50000  | Lahore    |
| NaN | 60000  | Karachi   |
| 30  | NaN    | Islamabad |
| 28  | 55000  | Lahore    |

After applying Complete Case Analysis:

| Age | Salary | City   |
| --- | ------ | ------ |
| 25  | 50000  | Lahore |
| 28  | 55000  | Lahore |

Rows with missing values are removed.

## Assumptions of Complete Case Analysis

Complete Case Analysis works properly when missing data follows the **Missing Completely at Random (MCAR)** assumption.

This means the probability of missing data is independent of any other variable.

Example: A survey participant accidentally skips a question.

If missing values depend on other variables, removing rows may introduce bias into the dataset.

## Advantages of Complete Case Analysis

**Simple Implementation**
Very easy to apply using data manipulation libraries.

**No Imputation Required**
Does not require estimating or guessing missing values.

**Preserves Original Data**
No changes are made to the remaining observations.

**Computationally Efficient**
Requires minimal processing.

## Disadvantages of Complete Case Analysis

**Data Loss**
Large portions of the dataset may be removed.

**Reduced Sample Size**
Smaller datasets may weaken model performance.

**Potential Bias**
If missing values are not random, removing rows may distort the data distribution.

**Not Suitable for High Missing Rates**
If many values are missing, too much data may be lost.

## When to Use Complete Case Analysis

Complete Case Analysis works best when:

- Missing values are very small (less than 5%)
- Missing values occur completely at random
- Dataset size is large
- Removing rows does not significantly reduce data

It should be avoided when:

- Dataset size is small
- Missing values are large
- Missing data depends on other variables

## Complete Case Analysis using Python

### Example Dataset

```python
import pandas as pd
import numpy as np

data = {
    'Age': [25, np.nan, 30, 28],
    'Salary': [50000, 60000, np.nan, 55000],
    'City': ['Lahore', 'Karachi', 'Islamabad', 'Lahore']
}

df = pd.DataFrame(data)
df
```

---

### Applying Complete Case Analysis

```python
df_complete = df.dropna()
```

Rows containing missing values are removed.

---

### Removing Missing Values from Specific Columns

```python
df.dropna(subset=['Age'])
```

This removes rows where **Age** is missing.

---

### Checking Missing Values

```python
df.isnull().sum()
```

This shows the number of missing values in each column.

---

## Example with Titanic Dataset

```python
import seaborn as sns

df = sns.load_dataset('titanic')

df.shape
```

Apply Complete Case Analysis:

```python
df_cca = df.dropna()

df_cca.shape
```

This allows comparison of dataset size **before and after applying CCA**.

## Key Takeaways

- Missing values are common in real-world datasets.
- Complete Case Analysis removes rows containing missing values.
- CCA assumes missing values are completely random.
- It is simple but may cause data loss.
- Best used when missing data is very small.

## Summary

Complete Case Analysis is a simple method for handling missing data when the proportion of missing values is small. It is easy to implement and computationally efficient but should only be used when missing values occur randomly to avoid bias and unnecessary data loss.
