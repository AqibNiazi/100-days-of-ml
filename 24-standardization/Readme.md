# Lecture 24: Feature Scaling - Standardization

# 📘 Feature Scaling Notes

## 🔹 What is Feature Scaling?

- **Definition:** Resizing different data values so the computer can compare them fairly.
- **Intuition:**
  - Age ranges: 18 → 60
  - Salary ranges: 20,000 → 500,000
  - Without scaling, the model thinks _salary_ is more important because the numbers are larger.
- **Goal:** Put features on a similar scale so models don’t get biased by magnitude.

## 🔹 Why do we need Feature Scaling?

- Prevents large-valued features from dominating small-valued ones.
- Helps algorithms that rely on **distance** (e.g., KNN, SVM) or **gradient descent** (e.g., Linear Regression, Neural Networks).
- Ensures faster convergence and better performance.
- **Pipeline Note:** Feature scaling is usually the **last step** in feature engineering before training the model.

## 🔹 Types of Feature Scaling

### 1. Normalization (Min-Max Scaling)

- Formula:

\[
x' = \frac{x - x*{min}}{x*{max} - x\_{min}}
\]

- Scales values to range [0, 1].
- Example: Age 18–60 → scaled to 0–1.
- Sensitive to **outliers**.

### 2. Standardization (Z-score Normalization)

- Formula:

\[
x' = \frac{x - \mu}{\sigma}
\]

where \(\mu\) = mean, \(\sigma\) = standard deviation.

- Centers data around 0 with unit variance.
- Example: Test scores → transformed to show how far each student is from average.
- More robust to outliers compared to min-max scaling.

## 🔹 Standardization

- **Concept:** Transform data so mean = 0 and standard deviation = 1.
- **Intuition:**
  - Class average = 50 marks
  - Student A = 70 → +2 SD above average
  - Student B = 30 → -2 SD below average
- **Effect:**
  - Average becomes 0
  - Most values lie between -3 and +3
  - Features are balanced → fair comparison

## 🔹 Example of Standardization

- Suppose we have ages: [27, 15, 33, …]
- Mean = 32, Std Dev = 10
- Transformation:

\[
x' = \frac{x - 32}{10}
\]

- Age 27 → \((27 - 32)/10 = -0.5\)
- Age 33 → \((33 - 32)/10 = 0.1\)
- After transformation, the new column has mean = 0 and std dev = 1.

## 🔹 Impact of Outliers

- **Normalization:** Strongly affected by outliers (e.g., one huge salary can skew scaling).
- **Standardization:** Less sensitive, but extreme outliers still distort mean and standard deviation.
- **Tip:** Consider **Robust Scaling** (using median and IQR) when dataset has heavy outliers.

## 🔹 When to use Standardization?

✅ Use when:

- Algorithms rely on distance or gradient descent:
  - Linear Regression
  - Logistic Regression
  - SVM
  - KNN
  - Neural Networks

🚫 Avoid when:

- Data is already in the same range
- Using tree-based models (Decision Tree, Random Forest, XGBoost) → they don’t care about scale.

## 🔹 Geometric Intuition

- Imagine plotting Age vs Salary for 500 people.
- Without scaling: Salary dominates because of larger magnitude.
- With standardization: Both features are centered at 0, scaled by their own variance.
- Result: Fairer distance calculations and balanced learning.

# ✅ Summary

- **Feature Scaling:** Resizes values for fair comparison.
- **Normalization:** Compresses values into [0,1], sensitive to outliers.
- **Standardization:** Centers data around mean 0, std dev 1, widely used in ML.
- **Outliers:** Can distort scaling → use robust methods if needed.
- **Best Practice:** Always scale before training distance-based or gradient-based models.
