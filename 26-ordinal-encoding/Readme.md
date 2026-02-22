# Encoding Categorical Variables in Machine Learning

This repository contains structured notes on **Encoding Categorical Variables**, an essential **data preprocessing step** in Machine Learning. These notes explain data types, categorical subtypes, and common encoding techniques with clear examples. Content is adapted from Notion notes and is suitable for **students, interviews, and quick revision**.

## 🔹 Types of Data in Machine Learning

### 1️⃣ Numerical Data

Numerical data represents **quantitative values** and supports mathematical operations.

**Types:**

- **Discrete**: Countable values (e.g., number of items, number of users)
- **Continuous**: Measurable values (e.g., height, weight, temperature)

**Examples:**

- Age: 25
- Salary: 75,000
- Temperature: 36.6

### 2️⃣ Categorical Data

Categorical data represents **qualitative labels** describing categories or groups.

**Examples:**

- Gender: Male, Female
- City: Lahore, Karachi, Islamabad
- Color: Red, Blue, Green

Most ML algorithms **cannot directly process categorical data**, so encoding is required.

## 🔹 Types of Categorical Data

### 1️⃣ Nominal Data

- Categories with **no intrinsic order**
- Numerical comparison is meaningless

**Examples:**

- Gender: Male, Female
- Color: Red, Blue, Green
- Country: Pakistan, USA, UK

### 2️⃣ Ordinal Data

- Categories with a **meaningful order**
- Spacing between categories is not uniform

**Examples:**

- Education: High School < Bachelor < Master < PhD
- Ratings: Poor < Average < Good < Excellent
- Size: Small < Medium < Large

## 🔢 Why Encoding is Required

- ML models require **numerical input**
- Categorical values lack numeric meaning
- Proper encoding preserves **relationships and order**

## 🔁 Label Encoding

### 📌 What is Label Encoding?

Label Encoding converts each category into a **unique integer value**.

### 📍 Example

| Color | Encoded Value |
| ----- | ------------- |
| Red   | 0             |
| Blue  | 1             |
| Green | 2             |

### ✅ When to Use

- Ordinal categorical features
- Tree-based models (with caution)

### ❌ Limitations

- Introduces false ordering for nominal data
- Some models may assume numeric relationships

## 🔢 Ordinal Encoding

### 📌 What is Ordinal Encoding?

Ordinal Encoding assigns numerical values **based on the true order** of categories.

### 📍 Example

| Education Level | Encoded Value |
| --------------- | ------------- |
| High School     | 1             |
| Bachelor        | 2             |
| Master          | 3             |
| PhD             | 4             |

### ✅ Advantages

- Preserves category order
- Simple and interpretable

### ❌ Limitations

- Assumes equal distance between categories

## 🆚 Label Encoding vs Ordinal Encoding

| Aspect                    | Label Encoding    | Ordinal Encoding |
| ------------------------- | ----------------- | ---------------- |
| Order Preserved           | ❌ Not guaranteed | ✅ Yes           |
| Suitable For              | Nominal / Ordinal | Ordinal only     |
| Risk of Misinterpretation | High (nominal)    | Lower            |
| Interpretability          | Medium            | High             |

## 📝 Summary

- Numerical data can be directly used in ML models
- Categorical data must be encoded
- Nominal data has no order, ordinal data has order
- Label Encoding is simple but risky for nominal features
- Ordinal Encoding is preferred when order matters

---

⭐ If you find this repository helpful, consider starring it!
