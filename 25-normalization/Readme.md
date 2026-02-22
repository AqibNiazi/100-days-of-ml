# Lecture 25: Normalization Notes

## 🔹 What is Normalization?

- **Definition:** Normalization is the process of adjusting values measured on different scales to a common scale — typically between 0 and 1.
- **Goal:** Ensure that all features contribute equally to model training and prevent large-scale features from dominating.
- **Used in:** Algorithms sensitive to magnitude and distance like KNN, SVM, Logistic Regression, and Neural Networks.


## 🔹 Why Normalize?

- Features like age (18–60) and salary (20,000–500,000) have vastly different ranges.
- Without normalization, models may assume salary is more important due to larger numbers.
- **Normalization ensures fair comparison and faster convergence.**

## 🔹 Types of Normalization

### 1. 📏 Min-Max Scaling

- **Formula:**

\[
x' = \frac{x - x*{min}}{x*{max} - x\_{min}}
\]

- **Range:** Scales data to [0, 1]
- **Example:** Age = 30, Min = 18, Max = 60

\[
x' = \frac{30 - 18}{60 - 18} = \frac{12}{42} \approx 0.29
\]

- **Pros:** Simple and effective when data is bounded.
- **Cons:** Sensitive to outliers.
- **Use When:** Data has known min/max and no extreme outliers.



### 2. 📊 Mean Normalization

- **Formula:**

\[
x' = \frac{x - \mu}{x*{max} - x*{min}}
\]

- **Range:** Centers data around mean, scales between -1 and 1.
- **Example:** Age = 30, Mean = 32, Min = 18, Max = 60

\[
x' = \frac{30 - 32}{60 - 18} = \frac{-2}{42} \approx -0.048
\]

- **Pros:** Centers data, useful for symmetric distributions.
- **Cons:** Still affected by outliers.
- **Use When:** You want centered data but still within a bounded range.

### 3. 📐 Max Absolute Scaling

- **Formula:**

\[
x' = \frac{x}{|x\_{max}|}
\]

- **Range:** [-1, 1] if data includes negatives.
- **Example:** Salary = 250,000, Max = 500,000

\[
x' = \frac{250000}{500000} = 0.5
\]

- **Pros:** Simple, preserves sparsity.
- **Cons:** Doesn’t center data.
- **Use When:** Data is already centered or sparse (e.g., text features).


### 4. 🛡️ Robust Scaling

- **Formula:**

\[
x' = \frac{x - \text{median}}{\text{IQR}}
\]

where IQR = Interquartile Range (Q3 - Q1).

- **Range:** Depends on distribution, but robust to outliers.
- **Example:** Age = 30, Median = 32, IQR = 20

\[
x' = \frac{30 - 32}{20} = -0.1
\]

- **Pros:** Resistant to outliers.
- **Cons:** Doesn’t guarantee fixed range.
- **Use When:** Dataset contains extreme values or skewed distributions.

## 🔹 Comparison Table

| Technique            | Formula                    | Range    | Sensitive to Outliers | Centered? | Best Use Case                |
| -------------------- | -------------------------- | -------- | --------------------- | --------- | ---------------------------- | ----- | ----------- |
| Min-Max Scaling      | \((x - min)/(max - min)\)  | [0, 1]   | ✅ Yes                | ❌ No     | Bounded data, no outliers    |
| Mean Normalization   | \((x - mean)/(max - min)\) | [-1, 1]  | ✅ Yes                | ✅ Yes    | Symmetric data               |
| Max Absolute Scaling | \(x /                      | max      | \)                    | [-1, 1]   | ✅ Yes                       | ❌ No | Sparse data |
| Robust Scaling       | \((x - median)/IQR\)       | Variable | ❌ No                 | ✅ Yes    | Skewed or outlier-heavy data |


# 🔄 Normalization vs Standardization

| Aspect                    | Normalization                                   | Standardization                               |
| ------------------------- | ----------------------------------------------- | --------------------------------------------- |
| **Definition**            | Rescales data to a fixed range (usually [0, 1]) | Centers data around mean 0 with unit variance |
| **Formula**               | \(\frac{x - x*{min}}{x*{max} - x\_{min}}\)      | \(\frac{x - \mu}{\sigma}\)                    |
| **Range**                 | [0, 1] or [-1, 1]                               | Typically [-3, 3] (not fixed)                 |
| **Sensitive to Outliers** | ✅ Yes                                          | ⚠️ Less sensitive (but still affected)        |
| **Use Case**              | When min and max are known and stable           | When data needs centering and fair comparison |
| **Best For**              | KNN, SVM, Neural Networks (bounded data)        | Linear/Logistic Regression, SVM, KNN, NN      |
| **Avoid When**            | Data has outliers or skewed distribution        | Using tree-based models (Decision Tree, RF)   |
| **Effect on Data**        | Compresses values into a narrow range           | Balances data around average                  |


### 🧠 Summary

- **Normalization** is ideal for bounded data without outliers.
- **Standardization** is better when data needs centering and fair distance comparison.
- Both are crucial for algorithms that rely on **distance**, **gradient descent**, or **feature magnitude**.
