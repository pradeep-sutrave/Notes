
# 📘 NumPy – Topic 3: Array Attributes (Deep Internal Understanding)

This topic helps you understand:

* How NumPy stores data
* How much memory it uses
* How to debug shape errors
* How ML models interpret tensors

---

## 🔹 3.1 Why Array Attributes Matter?

When working in:

* Machine Learning
* Data Science
* Image Processing
* Matrix operations

You MUST know:

> What is the shape?
> What is the dimension?
> How much memory is used?

Without this, broadcasting and reshaping will confuse you.

---

# 🔹 3.2 `ndim` → Number of Dimensions

![Image](https://study.com/cimages/multimages/16/1223543576347.png)

![Image](https://journaldev.nyc3.cdn.digitaloceanspaces.com/2020/03/2D-array-representation.png)

![Image](https://i.sstatic.net/h30TU.png)

![Image](https://www.researchgate.net/publication/281642488/figure/fig1/AS%3A284585259749392%401444861821647/Examples-of-3D-tensor-fl-attening-in-the-forward-index-permutation-mode.png)

### Definition:

`ndim` returns the number of axes (dimensions).

---

### Example 1: 1D Array

```python
import numpy as np

a = np.array([1, 2, 3])
print(a.ndim)
```

Output:

```
1
```

---

### Example 2: 2D Array

```python
b = np.array([[1,2],
              [3,4]])
print(b.ndim)
```

Output:

```
2
```

---

### Example 3: 3D Array

```python
c = np.array([
    [[1,2],[3,4]],
    [[5,6],[7,8]]
])
print(c.ndim)
```

Output:

```
3
```

---

### 🔥 Interview Note:

* 1D → Vector
* 2D → Matrix
* 3D → Tensor
* nd → N-dimensional tensor

---

# 🔹 3.3 `shape` → Structure of Array

### Definition:

Returns tuple showing size along each dimension.

---

### Example

```python
a = np.array([[1,2,3],
              [4,5,6]])

print(a.shape)
```

Output:

```
(2, 3)
```

Meaning:

* 2 rows
* 3 columns

---

### 3D Example

```python
print(c.shape)
```

Output:

```
(2, 2, 2)
```

Meaning:

* 2 blocks
* 2 rows
* 2 columns

---

### 🔥 Important:

Shape = blueprint of the array.

Most ML errors occur because of shape mismatch.

---

# 🔹 3.4 `size` → Total Elements

### Definition:

Returns total number of elements.

---

Example:

```python
a = np.array([[1,2,3],
              [4,5,6]])

print(a.size)
```

Output:

```
6
```

Formula:

```
size = rows × columns × depth × ...
```

---

# 🔹 3.5 `dtype` → Data Type

```python
a = np.array([1,2,3])
print(a.dtype)
```

Output:

```
int64
```

Important because:

* Affects memory
* Affects speed
* Important in ML models

---

# 🔹 3.6 `itemsize` → Memory per Element (Bytes)

Example:

```python
a = np.array([1,2,3], dtype=np.int32)
print(a.itemsize)
```

Output:

```
4
```

Meaning:
Each element takes 4 bytes.

---

Common sizes:

| Type    | Bytes |
| ------- | ----- |
| int32   | 4     |
| int64   | 8     |
| float32 | 4     |
| float64 | 8     |

---

# 🔹 3.7 `nbytes` → Total Memory Used

Formula:

```
nbytes = size × itemsize
```

Example:

```python
a = np.array([1,2,3], dtype=np.int32)
print(a.nbytes)
```

Output:

```
12
```

Because:

```
3 elements × 4 bytes = 12 bytes
```

---

# 🔹 3.8 Complete Attribute Example

```python
a = np.array([[1,2,3],
              [4,5,6]])

print("Dimensions:", a.ndim)
print("Shape:", a.shape)
print("Size:", a.size)
print("Data Type:", a.dtype)
print("Item Size:", a.itemsize)
print("Total Bytes:", a.nbytes)
```

---

# 🔥 Deep Internal Understanding

When you create:

```python
a = np.array([[1,2,3],
              [4,5,6]])
```

Internally:

1. NumPy allocates contiguous memory.
2. Stores 6 integers.
3. Keeps metadata:

   * ndim = 2
   * shape = (2,3)
   * strides (advanced topic later)

NumPy array =

```
Data block + Metadata
```

---

# 🧠 Real World Example (Image Data)

Suppose grayscale image:

```
Shape → (28, 28)
```

Color image:

```
Shape → (28, 28, 3)
```

* 3 → RGB channels

Understanding shape is critical in ML.

---

# 🎯 Interview Questions from This Topic

1. Difference between size and shape?
2. What is itemsize?
3. How to calculate memory of array?
4. Why dtype matters?
5. What does ndim return?

---

# 📌 Summary

You now understand:

✔ Dimensions
✔ Shape
✔ Total elements
✔ Memory per element
✔ Total memory usage
✔ Internal structure of ndarray

---
