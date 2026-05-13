# Lecture 7: Challenges in Machine Learning

This repository documents the **key challenges faced in Machine Learning systems**, covering issues from **data collection to deployment and cost considerations**. The content is adapted from structured Notion notes and is suitable for **students, interviews, and quick revision**.

## 1️⃣ Data Collection

### Description

Data collection is the foundation of any Machine Learning system. If the collected data is incomplete, outdated, or irrelevant, even the best algorithms will fail.

### Challenges

- Data spread across multiple sources
- Privacy, legal, and ethical constraints
- High cost of acquiring quality data
- Rapidly changing data over time


## 2️⃣ Insufficient Data / Insufficient Labeled Data

### Description

Most ML algorithms, especially supervised learning models, require **large amounts of labeled data** to perform well.

### Challenges

- Manual labeling is expensive and time-consuming
- Small datasets lead to poor generalization
- Models become unstable and unreliable

### Impact

- Overfitting
- Low performance on unseen data


## 3️⃣ Non-Representative Data

### Description

Training data must accurately represent real-world data. If the dataset is biased or incomplete, the model will learn incorrect patterns.

### 🔸 Sampling Noise

- Random fluctuations due to small sample sizes
- Causes deviation from the true population distribution

### 🔸 Sampling Bias

- Systematic error during data collection
- Certain groups are overrepresented or underrepresented

### 📉 Impact

- Biased predictions
- Poor real-world performance


## 4️⃣ Poor Quality Data

### Description

Poor-quality data introduces noise and errors into the learning process.

### Examples

- Missing values
- Noisy or incorrect labels
- Outliers
- Duplicate or inconsistent records

### Impact

- Misleading patterns
- Reduced model accuracy
- Increased preprocessing effort


## 5️⃣ Irrelevant Features

### Description

Not all features contribute useful information. Irrelevant or redundant features can confuse the model.

### Challenges

- Curse of dimensionality
- Increased training time
- Reduced interpretability

### Common Solutions

- Feature selection
- Feature engineering
- Dimensionality reduction


## 6️⃣ Overfitting

### Description

Overfitting occurs when a model learns noise and details in the training data rather than general patterns.

### Symptoms

- Very high training accuracy
- Poor validation or test accuracy

### Causes

- Complex models
- Small datasets
- Too many features

## 7️⃣ Underfitting

### Description

Underfitting occurs when a model is too simple to capture underlying data patterns.

### Symptoms

- Poor performance on both training and test data

### Causes

- Oversimplified models
- Insufficient training time
- Poor feature selection


## 8️⃣ Software Integration

### Description

Integrating ML models into real-world software systems is often challenging.

### Challenges

- Compatibility with existing systems
- Model versioning and updates
- Monitoring and maintenance
- Latency and scalability issues

## 9️⃣ Offline Learning / Deployment Challenges

### Description

Models trained using offline (batch) learning may struggle in dynamic production environments.

### Challenges

- Model becomes outdated over time
- Retraining is costly and slow
- Difficulty handling real-time data

### Impact

- Performance degradation
- Delayed response to data changes

## 🔟 Cost Involved

### Description

Machine Learning systems involve significant costs beyond model training.

### Cost Factors

- Data collection and labeling
- Computational resources (GPUs, TPUs)
- Storage and cloud infrastructure
- Deployment and maintenance
- Skilled engineering and data science workforce

## Summary

Machine Learning challenges span the **entire lifecycle**—from data acquisition to deployment and maintenance. Successfully addressing these challenges requires a balance of **data quality, model selection, engineering practices, and cost management**.


