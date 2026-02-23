# Lecture 27 # One-Hot Encoding in Machine Learning

This repository contains structured notes on **One-Hot Encoding**, a fundamental technique used to convert **categorical variables into numerical form** for Machine Learning models. The content is adapted from Notion notes and is suitable for **students, interviews, and quick revision**.

## 🔹 What is One-Hot Encoding?

One-Hot Encoding transforms each category of a categorical feature into a **separate binary column**.

- Value `1` → category is present
- Value `0` → category is absent

Each observation has exactly **one active (hot) column**.

## ❓ Why Do We Use One-Hot Encoding?

Most ML algorithms:

- Cannot process string-based categorical data
- May misinterpret label-encoded values as ordered

### ✅ Benefits

- Removes false ordinal relationships
- Preserves independence between categories
- Works well with linear and distance-based models

## 🗂️ When to Use One-Hot Encoding

- Nominal categorical variables (no order)
- Small to medium number of categories

Commonly used with:

- Linear Regression
- Logistic Regression
- K-Nearest Neighbors (KNN)
- Neural Networks

## 📍 Example

### Original Data

| Color |
| ----- |
| Red   |
| Blue  |
| Green |

### After One-Hot Encoding

| Color_Red | Color_Blue | Color_Green |
| --------- | ---------- | ----------- |
| 1         | 0          | 0           |
| 0         | 1          | 0           |
| 0         | 0          | 1           |

## ⚠️ Dummy Variable Trap

### What is Dummy Variable Trap?

The Dummy Variable Trap occurs when **all dummy variables are included**, causing **perfect multicollinearity**.

```
Color_Red + Color_Blue + Color_Green = 1
```

One variable can be predicted from others, making it redundant.

### ❌ Why is it a Problem?

- Multicollinearity in linear models
- Unstable coefficient estimates
- Reduced interpretability

---

## ✅ How to Avoid Dummy Variable Trap

### Drop One Dummy Column

Remove one category (reference category).

### Example (Drop Color_Green)

| Color_Red | Color_Blue |
| --------- | ---------- |
| 1         | 0          |
| 0         | 1          |
| 0         | 0          |

This avoids multicollinearity while preserving information.

## ⚖️ Advantages

- Simple and intuitive
- No assumption of order
- Widely supported in ML libraries

## ❌ Disadvantages

- Increases dimensionality
- Not suitable for high-cardinality features
- Can lead to sparse data

## 📝 Summary

- One-Hot Encoding converts categorical data into binary features
- Best suited for nominal variables
- Dummy Variable Trap arises due to multicollinearity
- Dropping one dummy variable solves the issue

⭐ If you find this repository helpful, consider starring it!
