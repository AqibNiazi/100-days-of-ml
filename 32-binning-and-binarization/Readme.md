# 📘 Lecture 32 – Feature Engineering

## Binning and Binarization

This document explains important Feature Engineering techniques related to **Binning (Discretization)** and **Binarization**, including types, examples, and use cases.

# 1️⃣ Why Do We Encode Numerical Features?

Although numerical features are already numeric, sometimes we encode or transform them to:

- Reduce noise
- Handle skewed distributions
- Capture non-linear relationships
- Improve interpretability
- Make models more robust
- Improve performance of linear models

### Example

Instead of using exact values:

```

Age = 23, 45, 67

```

We can convert them into categories:

```

Young, Adult, Senior

```

This can help models learn better patterns.

# 2️⃣ Types of Numerical Encoding

1. Discretization (Binning)
2. Binarization
3. Scaling (Standardization / Normalization)
4. Log / Power Transform
5. Polynomial Encoding

This lecture focuses on:

- Discretization (Binning)
- Binarization

# 3️⃣ What is Discretization?

## 📌 Definition

**Discretization** is the process of converting continuous numerical data into discrete categories (bins).

> Continuous → Categorical

## 🎯 Why Do We Use Discretization?

- Reduce effect of outliers
- Handle skewed data
- Capture non-linear patterns
- Improve interpretability
- Improve performance in some ML models

### Example

Original Income Data:

```

20000, 25000, 30000, 100000

```

After Discretization:

```

Low, Medium, High

```

# 4️⃣ Types of Discretization

1. Equal Width (Uniform Binning)
2. Equal Frequency (Quantile Binning)
3. K-Means Binning
4. Custom Domain-Based Binning

# 5️⃣ Equal Width (Uniform Binning)

## 📌 What is Equal Width Binning?

The entire range of values is divided into equal-sized intervals.

### Formula

```
Bin Width = (Max - Min) / Number_of_Bins

```

## 📊 Example

Data:

```

[10, 20, 30, 40, 50, 60]

```

Min = 10
Max = 60
Bins = 5

Bin Width:

```

(60 - 10) / 5 = 10

```

Bins:

```

10–20
20–30
30–40
40–50
50–60

```

## ✅ When to Use?

- When data is uniformly distributed
- When interpretability is important

⚠ Limitation:

- Not suitable for skewed data

# 6️⃣ Equal Frequency (Quantile Binning)

## 📌 What is Equal Frequency Binning?

Each bin contains approximately the same number of data points.

Instead of equal width, we ensure equal count.

## 📊 Example

Data:

```

[5, 10, 15, 20, 100]

```

If we create 2 bins:

Bin 1:

```

[5, 10]

```

Bin 2:

```

[15, 20, 100]

```

Each bin has roughly equal number of values.

## 🎯 Why Use It?

- Works well with skewed data
- Ensures balanced bins
- Reduces impact of extreme values

# 7️⃣ K-Means Binning

## 📌 What is K-Means Binning?

Uses the **K-Means clustering algorithm** to group numerical values into clusters.

Each cluster becomes a bin.

## 🎯 Why Use It?

- Data-driven approach
- Captures natural groupings
- Better for complex distributions

## 📊 Example

Data:

```

[10, 12, 14, 50, 55, 60]

```

If K = 2:

Cluster 1:

```

10, 12, 14

```

Cluster 2:

```

50, 55, 60

```

# 8️⃣ Encoding the Discretized Variable

After binning, the variable becomes categorical.

Now we encode it using:

- Label Encoding
- One-Hot Encoding
- Ordinal Encoding

## 📊 Example

Age Bins:

```

Young, Adult, Senior

```

### Label Encoding

```

Young → 0
Adult → 1
Senior → 2

```

### One-Hot Encoding

```

Young → [1,0,0]
Adult → [0,1,0]
Senior → [0,0,1]

```

# 9️⃣ Custom Domain-Based Binning

## 📌 What is Custom Binning?

Bins are created based on domain knowledge instead of mathematical formulas.

## 📊 Example (Education System)

Marks:

```

0–40 → Fail
41–60 → Average
61–80 → Good
81–100 → Excellent

```

## ✅ When to Use?

- When business rules exist
- When expert knowledge is available
- When interpretation is important

# 🔟 Binarization

## 📌 What is Binarization?

Converting numerical values into 0 and 1 based on a threshold.

## 📊 Example

Data:

```

[5, 10, 15, 20]

```

Threshold = 12

After Binarization:

```

[0, 0, 1, 1]

```

Rule:

```

x > threshold → 1
else → 0

```

## 🎯 Why Use Binarization?

- Simplifies data
- Creates indicator variables
- Useful in logistic regression
- Useful in text processing (presence/absence)

# 📌 Complete Example

Original Age Data:

```

[18, 22, 35, 45, 60]

```

### Step 1: Equal Width Binning (3 bins)

```

18–30 → Young
31–50 → Adult
51–70 → Senior

```

Result:

```

Young, Young, Adult, Adult, Senior

```

### Step 2: One-Hot Encoding

```

Young → [1,0,0]
Adult → [0,1,0]
Senior → [0,0,1]

```

# 📌 Key Takeaways

- Discretization converts continuous data into categorical bins.
- Equal Width → Same interval size.
- Equal Frequency → Same number of samples per bin.
- K-Means → Clustering-based binning.
- Custom Binning → Based on domain knowledge.
- Binarization → Threshold-based 0/1 encoding.

## 📚 Summary

Binning and Binarization are important Feature Engineering techniques that:

- Improve interpretability
- Handle skewed data
- Capture non-linear patterns
- Help linear models perform better
- Simplify numerical representations

Understanding when and how to use these techniques is essential for building effective ML models.
