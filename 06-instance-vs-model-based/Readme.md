# Lecture 6: Instance-Based vs Model-Based Learning

This repository provides clear and concise notes on **Instance-Based Learning** and **Model-Based Learning**, two fundamental learning paradigms in Machine Learning. The content is adapted from structured Notion notes and is suitable for **students, interviews, and quick revision**.

## Instance-Based Learning (Memory-Based Learning)

### What is Instance-Based Learning?

Instance-Based Learning is a learning approach where the model **stores training instances** and makes predictions by **comparing new inputs with stored examples**. There is no explicit model built during training.

Learning happens at **prediction time**, which is why it is also called **Lazy Learning**.

### Key Characteristics

- Stores most or all training data
- No explicit training phase
- Lazy learning approach
- High computation during prediction
- Sensitive to noise and irrelevant features

### Example: k-Nearest Neighbors (k-NN)

**How it works:**

1. Store all labeled training instances
2. Compute distance between new input and stored instances
3. Select the _k_ nearest neighbors
4. Predict using majority vote (classification) or average (regression)

**Real-World Applications:**

- Recommendation systems
- Handwritten digit recognition

### Advantages

- Simple and intuitive
- No training time required
- Easily adapts to new data

### Disadvantages

- High memory consumption
- Slow prediction on large datasets
- Sensitive to noisy data

## 🔹 Model-Based Learning

### What is Model-Based Learning?

Model-Based Learning builds an **explicit mathematical or statistical model** from training data. The learned model is then used to make predictions on unseen data.

Learning happens during the **training phase**, and prediction is fast.

### Key Characteristics

- Builds a generalized model
- Computationally intensive training phase
- Fast inference
- Low memory usage after training
- Better generalization capability

### Example: Linear Regression

**How it works:**

1. Learn model parameters from training data
2. Build a mathematical function
3. Use the function to predict unseen values

**Real-World Applications:**

- House price prediction
- Sales forecasting

### Advantages

- Fast predictions
- Requires less memory
- More robust to noise

### Disadvantages

- Requires retraining to incorporate new data
- Model assumptions may reduce flexibility


## Instance-Based vs Model-Based Learning

| Aspect            | Instance-Based Learning    | Model-Based Learning                    |
| ----------------- | -------------------------- | --------------------------------------- |
| Learning Style    | Lazy Learning              | Eager Learning                          |
| Training Cost     | Very Low                   | High                                    |
| Prediction Speed  | Slow                       | Fast                                    |
| Memory Usage      | High                       | Low                                     |
| Generalization    | Low                        | High                                    |
| Noise Sensitivity | High                       | Lower                                   |
| Examples          | k-NN, Case-Based Reasoning | Linear Regression, SVM, Neural Networks |

## Summary

- **Instance-Based Learning** relies on memorization and similarity measures
- **Model-Based Learning** relies on abstraction and generalization
- The choice depends on **dataset size, memory constraints, and inference speed requirements**

