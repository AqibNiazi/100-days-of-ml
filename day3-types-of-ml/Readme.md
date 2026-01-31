# Day 3: Types of Machine Learning

This lecture explores the different types of Machine Learning (ML), both in short notes and detailed explanations.

---

## 3. Types of Machine Learning (Short Notes)

### 3.1 Supervised Learning

Supervised learning involves training a model on labeled data, where the input-output pairs are known. The model learns to predict the output from the input.

- **Regression:** Predicts continuous values.  
  _Example:_ Predicting house prices based on features like size and location.
- **Classification:** Predicts discrete categories.  
  _Example:_ Email spam detection (spam or not spam), handwriting recognition.

---

### 3.2 Unsupervised Learning

Unsupervised learning deals with unlabeled data, where the model tries to find hidden patterns or structures.

- **Clustering:** Groups similar data points together.  
  _Example:_ Customer segmentation in marketing.
- **Dimensionality Reduction:** Reduces the number of features while preserving important information.  
  _Example:_ PCA used for data visualization.
- **Anomaly Detection:** Identifies unusual data points.  
  _Example:_ Fraud detection in banking.
- **Association Rule Learning:** Finds relationships between variables.  
  _Example:_ Market basket analysis.

---

### 3.3 Semi-Supervised Learning

Semi-supervised learning uses a small amount of labeled data along with a large amount of unlabeled data to improve learning accuracy.

- _Example:_ Google Photos grouping faces with limited labeled images.

---

### 3.4 Reinforcement Learning

Reinforcement learning trains an agent to make a sequence of decisions by rewarding desired behaviors and punishing undesired ones.

- _Example:_ Training a robot to navigate a maze or teaching an AI to play chess/Go.

---

## 3. Types of Machine Learning (Detailed Notes)

### 3.1 Supervised Learning

Supervised learning is when a computer learns from training data that already contains correct answers.  
If both input and output are available, the task is to create a relationship between them to predict new inputs.

#### 3.1.1 Regression

Regression predicts numerical values based on input data.

- **Linear Regression:** Uses a straight line.
- **Multiple Regression:** Uses multiple inputs (e.g., house price depends on size, location, rooms).
- **Polynomial Regression:** Uses a curved line.

#### 3.1.2 Classification

Classification predicts categories (labels) instead of numbers.  
**Analogy:** Sorting fruits into baskets (apples, bananas, oranges).

**Summary:**

- Input + Output → Supervised Learning
- Output = Number → Regression
- Output = Category → Classification

---

### 3.2 Unsupervised Learning

Unsupervised learning finds patterns and groups in data without knowing the correct answers.  
Only input data is available, and the computer discovers structure on its own.

**Example:** Grouping mixed fruits by color, shape, and size without labels.

#### 3.2.1 Clustering

Groups similar items together.

- **K-Means:** Predefined number of clusters.
- **Hierarchical:** Builds a tree of clusters.
- **DBSCAN:** Detects clusters of varying shapes and noise.

#### 3.2.2 Dimensionality Reduction

Simplifies data by reducing features while keeping important information.

- **PCA:** Finds important directions in data.
- **t-SNE:** Visualizes high-dimensional data in 2D/3D.
- **Autoencoders:** Neural networks that compress data.

#### 3.2.3 Anomaly Detection

Identifies unusual or abnormal data points.

- **Point anomaly:** Single unusual data point.
- **Contextual anomaly:** Unusual in context (e.g., high heart rate while sleeping).
- **Collective anomaly:** Unusual group pattern.

#### 3.2.4 Association Rule Learning

Finds relationships between items.  
_Example:_ People who buy bread often also buy butter.

---

### 3.3 Semi-Supervised Learning

Uses a mix of labeled and unlabeled data.  
_Example:_ Google Photos face recognition with limited labeled images.

---

### 3.4 Reinforcement Learning

Learning by trial and error, with rewards and punishments guiding behavior.  
_Example:_ Learning to ride a bicycle or training AI to play games.

---

## Summary

This lecture covers:

- The four main types of ML: Supervised, Unsupervised, Semi-Supervised, and Reinforcement Learning.
- Detailed breakdowns of regression, classification, clustering, dimensionality reduction, anomaly detection, and association rule learning.
- Practical analogies and examples to illustrate each concept.
