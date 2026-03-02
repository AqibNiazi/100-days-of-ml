# 📘 Lecture 33 – Handling Mixed Data

## Feature Engineering Techniques for Mixed-Type Features

This document explains how to handle **mixed-type data** (features containing both letters and numbers) using feature engineering techniques, with examples from the Titanic dataset.

# 1️⃣ What is Mixed Data?

**Mixed data** refers to features that contain:

- Letters and numbers
- Multiple categories inside one value
- Structured but unclean information

### Example

```

Cabin: B23, B45, C21, E101, D56

```

This feature is neither purely categorical nor purely numerical.

# 2️⃣ Why Mixed Data Needs Special Handling?

If we directly apply:

- Label Encoding ❌
- One-Hot Encoding ❌

We lose meaningful information.

### Example

```

B23 → 0
C21 → 1

```

This ignores:

- Deck information (B, C, D)
- Cabin number (23, 21)
- Hidden structure inside the feature

👉 Therefore, we must split and extract meaningful parts.

# 3️⃣ Understanding the Cabin Feature (Titanic Example)

### Example Values

```

B23
C45
E101
D56

```

### Structure

```

[Deck Letter][Cabin Number]

```

- First character → Deck (categorical)
- Remaining numbers → Cabin number (numerical)

# 4️⃣ Techniques to Handle Mixed Data

## 🔹 Technique 1: Splitting the Feature

### Step 1: Extract Deck

From:

```

B23

```

Extract:

```

Deck = B

```

Treat it as a categorical feature.

Apply:

- One-Hot Encoding
- Target Encoding

### Step 2: Extract Cabin Number

From:

```

B23

```

Extract:

```

23

```

Treat it as numerical.

Apply:

- Scaling
- Binning (optional)

## 🔹 Technique 2: Extract First Character Only

Sometimes cabin numbers are too noisy.

Instead of full split:

```

B23 → B
C45 → C

```

Use only deck information.

📌 Reason:

- Deck may capture socio-economic status.
- Cabin number may not be very meaningful.

## 🔹 Technique 3: Handling Multiple Values in One Cell

Sometimes a cabin column contains:

```

B23 C25 C27

```

This means one passenger has multiple cabins.

### Option 1: Take First Cabin Only

```

B23 C25 → B23

```

### Option 2: Count Number of Cabins

```

B23 C25 C27 → 3

```

Create a new feature:

```

Cabin_Count

```

### Option 3: Extract All Deck Letters

```

B23 C25 C27 → B, C

```

Then encode them.

## 🔹 Technique 4: Handling Missing Values

Cabin often has many missing values.

Options:

1. Replace with "Unknown"
2. Create binary feature:

```

Has_Cabin = 1 if cabin exists else 0

```

This is very powerful in the Titanic dataset.

# 5️⃣ Complete Example (Titanic Cabin)

Original:

```

Cabin = "B23 C25"

```

### Step 1: Extract Deck

```

Deck = B

```

### Step 2: Count Cabins

```

Cabin_Count = 2

```

### Step 3: Create Binary Feature

```

Has_Cabin = 1

```

### Final Engineered Features

- Deck (Categorical)
- Cabin_Count (Numerical)
- Has_Cabin (Binary)

# 6️⃣ Why This Improves Model Performance

- Preserves hidden structure
- Extracts meaningful signals
- Reduces noise
- Improves interpretability
- Helps both tree-based and linear models

# 7️⃣ General Strategy for Mixed Data Handling

Whenever you encounter mixed data:

1. Understand the pattern
2. Split meaningful components
3. Encode each component separately
4. Remove the original messy column

# 8️⃣ Real-World Examples of Mixed Data

| Feature       | Example      | Suggested Handling            |
| ------------- | ------------ | ----------------------------- |
| Cabin         | B23          | Extract letter & number       |
| Product Code  | A123X        | Extract prefix & numeric part |
| ZIP Code      | 75001        | Treat as categorical          |
| Phone Number  | 0300-1234567 | Extract area code             |
| License Plate | ABC-123      | Extract region code           |

# 📌 Key Takeaways

- Mixed data contains both letters and numbers.
- Never encode mixed data directly.
- Always split into meaningful components.
- Create additional engineered features.
- Handle missing values carefully.
- Drop the original raw feature after transformation.

## 📚 Summary

Handling mixed-type features is an essential feature engineering skill.  
By extracting meaningful components and encoding them properly, we can significantly improve model performance and interpretability.
