# 📘 NumPy – Topic 1: Introduction to NumPy (Complete Detailed Notes)

---

## 🔹 1.1 What is NumPy?

![Image](https://scipy-lectures.org/_images/numpy_fancy_indexing.png)

![Image](https://miro.medium.com/v2/resize%3Afit%3A998/1%2A7O7miFMxn_D-lUOEDY3URg.png)

![Image](https://iq.opengenus.org/content/images/2020/04/index.png)

![Image](https://iq.opengenus.org/content/images/2020/04/Create-1.png)

### Definition

**NumPy (Numerical Python)** is a powerful Python library used for:

* Numerical computations
* Matrix operations
* Scientific computing
* Data processing
* Machine Learning foundations

It provides a special object called:

> **ndarray (N-dimensional array)**

This is the heart of NumPy.

---

## 🔹 1.2 Why NumPy is Needed?

You may ask:

> ❓ Python already has lists. Why NumPy?

Let’s understand deeply.

---

### 🔸 Problem with Python Lists

Python lists:

* Store heterogeneous data
* Store references to objects (not actual values)
* Slower for mathematical operations
* No built-in vectorized operations

Example:

```python
a = [1, 2, 3]
b = [4, 5, 6]

# Cannot directly do:
a + b   # This concatenates, not adds
```

---

### 🔸 NumPy Advantage

NumPy arrays:

* Store homogeneous data
* Stored in contiguous memory
* Faster computation (written in C)
* Supports vectorized operations

Example:

```python
import numpy as np

a = np.array([1, 2, 3])
b = np.array([4, 5, 6])

a + b   # Output: [5 7 9]
```

✔ Element-wise addition
✔ Faster
✔ Less memory

---

## 🔹 1.3 Internal Working (Important for Interviews)

### 🧠 How NumPy is Fast?

NumPy is faster because:

1. Written in C
2. Uses contiguous memory blocks
3. Avoids Python loop overhead
4. Uses vectorization

---

### 🔸 Memory Comparison

Python list:

```
[1] -> reference
[2] -> reference
[3] -> reference
```

Each element stored separately in memory.

NumPy array:

```
| 1 | 2 | 3 |
```

Stored in a continuous memory block.

This improves:

* Cache performance
* CPU optimization
* Memory usage

---

## 🔹 1.4 Installing NumPy

```bash
pip install numpy
```

Or in Jupyter:

```python
!pip install numpy
```

---

## 🔹 1.5 Importing NumPy

Standard practice:

```python
import numpy as np
```

Why `np`?

✔ Short alias
✔ Industry standard
✔ Cleaner code

---

## 🔹 1.6 What is ndarray?

### Definition:

`ndarray` = N-dimensional array

It can be:

* 1D array (vector)
* 2D array (matrix)
* 3D array (tensor)
* n-dimensional structure

---

### Example:

```python
a = np.array([1, 2, 3])
print(type(a))
```

Output:

```
<class 'numpy.ndarray'>
```

---

## 🔹 1.7 Dimensions in NumPy

| Type | Example       |
| ---- | ------------- |
| 0D   | Single number |
| 1D   | Vector        |
| 2D   | Matrix        |
| 3D   | Tensor        |

---

### 1D Example

```python
a = np.array([1, 2, 3])
```

---

### 2D Example

```python
b = np.array([[1, 2],
              [3, 4]])
```

---

### 3D Example

```python
c = np.array([
    [[1,2],[3,4]],
    [[5,6],[7,8]]
])
```

---

## 🔹 1.8 Homogeneous Data Rule

NumPy arrays must contain:

> Same data type elements

Example:

```python
a = np.array([1, 2, 3])      # int
b = np.array([1.5, 2.3, 3])  # becomes float
```

If mixed:

```python
np.array([1, 2.5, 3])
```

It converts all to float.

---

## 🔹 1.9 Vectorization (Very Important)

Vectorization means:

> Performing operations on entire arrays without writing loops.

Instead of:

```python
result = []
for i in range(len(a)):
    result.append(a[i] * 2)
```

We write:

```python
a * 2
```

✔ Cleaner
✔ Faster
✔ Efficient

---

## 🔹 1.10 Applications of NumPy

NumPy is used in:

* Machine Learning
* Artificial Intelligence
* Data Science
* Image Processing
* Deep Learning
* Scientific simulations

Libraries built on NumPy:

* Pandas
* Scikit-learn
* TensorFlow (internally)
* PyTorch (conceptually similar)

---

# 🔥 Interview Important Points

1. Difference between list and ndarray
2. Why NumPy is faster?
3. What is vectorization?
4. What is contiguous memory?
5. What is homogeneous data?

---

# 📌 Summary of Topic 1

You learned:

✔ What NumPy is
✔ Why it is needed
✔ ndarray concept
✔ Memory structure
✔ Vectorization
✔ Dimensions
✔ Installation

---
