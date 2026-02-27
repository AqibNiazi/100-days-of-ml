# Lecture 31: Power Transformations in Machine Learning

## Box-Cox and Yeo-Johnson Transform

This document explains power transformation techniques used in Machine Learning, specifically **Box-Cox** and **Yeo-Johnson** transformations, with formulas, examples, and comparisons.

# 1️⃣ What is Power Transformation?

A **Power Transformation** is a statistical technique used to:

* Make data more normally distributed
* Reduce skewness
* Stabilize variance
* Improve model performance (especially linear models)

📌 Commonly used in:

* Linear Regression
* Logistic Regression
* Naive Bayes
* Statistical modeling

# 2️⃣ Why Do We Need Power Transformation?

Many ML algorithms assume:

* Data is normally distributed
* Constant variance (homoscedasticity)

If data is highly skewed:

* Model performance decreases
* Coefficients become unreliable
* Predictions become biased

Power transformations help correct these issues.

# 3️⃣ Box-Cox Transformation

## 📌 What is Box-Cox?

The **Box-Cox transformation** converts data to make it closer to a normal distribution.

⚠ **Important Condition:**
Data must be strictly positive (no zero or negative values).


## 📐 Box-Cox Formula

For a given $\lambda$ (lambda):

If $\lambda \ne 0$:


$$
y(\lambda) = \frac{x^{\lambda} - 1}{\lambda}
$$

If $\lambda = 0$:


$$
y(\lambda) = \log(x)
$$


## 🔍 What is Lambda ($\lambda$)?

Lambda determines the type of transformation:

| λ Value | Transformation Type |
| ------- | ------------------- |
| λ = 1   | No transformation   |
| λ = 0   | Log transformation  |
| λ = 0.5 | Square root         |
| λ = -1  | Reciprocal          |

The algorithm automatically finds the best $\lambda$ value.


## 📊 Example of Box-Cox

Original data (positively skewed):

```
[1, 2, 3, 10, 50, 100]
```

After Box-Cox transformation (approximate values):

```
[0.00, 0.69, 1.10, 2.30, 3.91, 4.61]
```

✅ Result:

* Reduced skewness
* Distribution becomes more symmetric


## ✅ When to Use Box-Cox?

* Data is strictly positive
* Data is right-skewed
* Working with linear models


# 4️⃣ Yeo-Johnson Transformation

## 📌 What is Yeo-Johnson?

The **Yeo-Johnson transformation** is an extension of Box-Cox.

✔ Works with:

* Positive values
* Zero values
* Negative values

This makes it more flexible than Box-Cox.


## 📐 Yeo-Johnson Formula

For $x \ge 0$:

If $\lambda \ne 0$:


$$
y(\lambda) = \frac{(x + 1)^{\lambda} - 1}{\lambda}
$$

If $\lambda = 0$:


$$
y(\lambda) = \log(x + 1)
$$

For $x < 0$:

If $\lambda \ne 2$:


$$
y(\lambda) = - \frac{(-x + 1)^{2 - \lambda} - 1}{2 - \lambda}
$$

If $\lambda = 2$:

$$
y(\lambda) = -\log(-x + 1)
$$


# 5️⃣ Box-Cox vs Yeo-Johnson Comparison

| Feature                 | Box-Cox            | Yeo-Johnson      |
| ----------------------- | ------------------ | ---------------- |
| Handles Positive Values | ✅ Yes              | ✅ Yes            |
| Handles Zero Values     | ❌ No               | ✅ Yes            |
| Handles Negative Values | ❌ No               | ✅ Yes            |
| Flexibility             | Medium             | High             |
| Common Usage            | Statistical models | ML preprocessing |


# 6️⃣ Implementation in Scikit-Learn

```python
from sklearn.preprocessing import PowerTransformer

# Box-Cox Transformation
pt_boxcox = PowerTransformer(method='box-cox')

# Yeo-Johnson Transformation
pt_yeo = PowerTransformer(method='yeo-johnson')
```

# 7️⃣ When Should You Use Power Transform?

✅ Use when:

* Data is heavily skewed
* Residuals are not normal
* Variance is not constant
* Linear regression assumptions are violated

❌ Avoid when:

* Using tree-based models (Random Forest, XGBoost)
  (They do not require normal distribution)

# 📌 Key Takeaways

* Power transformations reduce skewness.
* Box-Cox works only on positive data.
* Yeo-Johnson works on all real numbers.
* Helps meet normality assumptions.
* Improves performance of linear/statistical models.

## 📚 Summary

Power transformations are important preprocessing techniques in Machine Learning.
Understanding when to use **Box-Cox** or **Yeo-Johnson** can significantly improve model performance and statistical reliability.

