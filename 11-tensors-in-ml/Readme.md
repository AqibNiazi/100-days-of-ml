# 📘 Tensors in Machine Learning

This document explains the concept of tensors in Machine Learning, including different tensor dimensions, rank, axes, shape, and practical examples.

---

# 1️⃣ What are Tensors?

A **Tensor** is a mathematical structure used to represent numerical data in Machine Learning and Deep Learning.

> A tensor is a **multi-dimensional array of numbers**.

Tensors are the fundamental data structures used in:

- PyTorch
- TensorFlow
- NumPy

---

## 🔹 Why Tensors Are Important in ML?

- Store input data (images, text, audio)
- Store model weights
- Perform mathematical operations
- Represent outputs and predictions

---

# 2️⃣ 0D Tensor (Scalar)

A **0D tensor** contains a single number.

- No axes
- No dimensions
- Rank = 0

### Example

```

5

```

**Shape:** `()`  
**Rank:** `0`

---

# 3️⃣ 1D Tensor (Vector)

A **1D tensor** is a list of numbers arranged in one direction.

- One axis
- Rank = 1

### Example

```

[1, 2, 3, 4]

```

**Shape:** `(4,)`  
**Rank:** `1`

### Real-World Examples

- List of student marks
- Feature vector of one data sample

---

# 4️⃣ 2D Tensor (Matrix)

A **2D tensor** is arranged in rows and columns.

- Two axes (rows and columns)
- Rank = 2

### Example

```

[
[1, 2, 3],
[4, 5, 6]
]

```

**Shape:** `(2, 3)`  
**Rank:** `2`

### Real-World Examples

- Dataset table (rows = samples, columns = features)
- Grayscale image

---

# 5️⃣ 3D Tensor

A **3D tensor** is a collection of 2D matrices.

- Three axes
- Rank = 3

### Example

```

[
[
[1, 2],
[3, 4]
],
[
[5, 6],
[7, 8]
]
]

```

**Shape:** `(2, 2, 2)`  
**Rank:** `3`

### Real-World Examples

- Colored image (Height × Width × Channels)
- Multiple grayscale images stacked together

---

# 6️⃣ ND Tensor (Higher-Dimensional Tensor)

An **N-dimensional tensor** has more than three dimensions.

General format:

```

(shape1, shape2, shape3, ..., shapeN)

```

- **Rank** = Number of axes
- **Shape** = Size along each axis

---

# 7️⃣ Rank, Axes, and Shape

---

## 🔹 Rank

The **rank** of a tensor is the number of dimensions (axes) it has.

| Tensor Type | Rank |
| ----------- | ---- |
| Scalar      | 0    |
| Vector      | 1    |
| Matrix      | 2    |
| 3D Tensor   | 3    |
| ND Tensor   | N    |

---

## 🔹 Axes

Axes are the directions in which data extends.

Example:

For a tensor with shape `(3, 4, 5)`:

- Axis 0 → size 3
- Axis 1 → size 4
- Axis 2 → size 5

Total axes = 3 → Rank = 3

---

## 🔹 Shape

The **shape** describes the size of a tensor along each axis.

Example:

```

Tensor shape: (2, 3)

```

This means:

- 2 rows
- 3 columns

---

# 8️⃣ Examples of Different Tensors

---

## 🔹 1D Tensor Example

```

[10, 20, 30]

```

**Shape:** `(3,)`  
**Rank:** `1`

---

## 🔹 2D Tensor Example

```

[
[1, 2],
[3, 4],
[5, 6]
]

```

**Shape:** `(3, 2)`  
**Rank:** `2`

---

## 🔹 3D Tensor Example

```

[
[
[1, 2],
[3, 4]
],
[
[5, 6],
[7, 8]
]
]

```

**Shape:** `(2, 2, 2)`  
**Rank:** `3`

---

## 🔹 4D Tensor Example

Common in deep learning for image batches.

Format:

```

(batch_size, height, width, channels)

```

Example:

- 10 images
- 64 × 64 resolution
- 3 color channels

Shape:

```

(10, 64, 64, 3)

```

**Rank:** `4`

---

## 🔹 5D Tensor Example

Common in video processing.

Format:

```

(batch_size, frames, height, width, channels)

```

Example:

- 5 videos
- 20 frames per video
- 64 × 64 resolution
- 3 color channels

Shape:

```

(5, 20, 64, 64, 3)

```

**Rank:** `5`

---

# 📌 Key Takeaways

- A tensor is a multi-dimensional array.
- Rank = Number of dimensions.
- Shape = Size along each dimension.
- Axes = Directions in which data extends.
- Deep learning models commonly use 3D, 4D, and 5D tensors.

---

## 📚 Summary

Tensors are the foundation of Machine Learning and Deep Learning.  
Understanding dimensions, rank, and shape is essential for working with neural networks and real-world ML data.
