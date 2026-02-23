
# 📘 NumPy – Topic 2: Creating NumPy Arrays (Complete Detailed Guide)

This is one of the most important foundational topics.
If array creation is not clear, everything else becomes confusing.

---

## 🔹 2.1 Creating Arrays Using `np.array()`

![Image](https://i.sstatic.net/NWTQH.png)

![Image](https://iq.opengenus.org/content/images/2020/04/Create-1.png)

![Image](https://miro.medium.com/0%2Ap5YOY0e2EXIYHGma.png)

![Image](https://jalammar.github.io/images/numpy/numpy-3d-array-creation.png)

### 🔸 Syntax

```python
np.array(object, dtype=None)
```

### 🔸 Creating 1D Array

```python
import numpy as np

a = np.array([1, 2, 3, 4])
print(a)
```

Output:

```
[1 2 3 4]
```

---

### 🔸 Creating 2D Array

```python
b = np.array([[1, 2],
              [3, 4]])
```

This creates a matrix.

Shape:

```
(2, 2)
```

---

### 🔸 Creating 3D Array

```python
c = np.array([
    [[1,2],[3,4]],
    [[5,6],[7,8]]
])
```

Shape:

```
(2, 2, 2)
```

---

## 🔹 2.2 Understanding `dtype`

By default, NumPy automatically decides datatype.

```python
a = np.array([1,2,3])
print(a.dtype)
```

Output:

```
int64
```

You can manually define:

```python
a = np.array([1,2,3], dtype=float)
```

Now:

```
[1. 2. 3.]
```

---

### 🔸 Important Data Types

| Type    | Description     |
| ------- | --------------- |
| int32   | 32-bit integer  |
| int64   | 64-bit integer  |
| float32 | 32-bit decimal  |
| float64 | 64-bit decimal  |
| bool    | Boolean         |
| complex | Complex numbers |

---

## 🔹 2.3 Creating Special Arrays

---

### 🔸 `np.zeros()`

Creates array filled with 0.

```python
np.zeros((3,3))
```

Output:

```
[[0. 0. 0.]
 [0. 0. 0.]
 [0. 0. 0.]]
```

---

### 🔸 `np.ones()`

```python
np.ones((2,4))
```

---

### 🔸 `np.empty()`

Creates array with random garbage values (uninitialized memory).

```python
np.empty((2,2))
```

⚠ Used when performance matters.

---

## 🔹 2.4 Creating Sequences

---

### 🔸 `np.arange()`

Like Python `range()` but returns array.

```python
np.arange(0, 10, 2)
```

Output:

```
[0 2 4 6 8]
```

Parameters:

```
(start, stop, step)
```

---

### 🔸 `np.linspace()`

Creates evenly spaced numbers.

```python
np.linspace(0, 1, 5)
```

Output:

```
[0.   0.25 0.5  0.75 1.  ]
```

Here:

```
(start, stop, number_of_values)
```

Difference:

| arange                  | linspace              |
| ----------------------- | --------------------- |
| Uses step               | Uses number of points |
| May miss float accuracy | Better for ML         |

---

## 🔹 2.5 Identity Matrix

![Image](https://d138zd1ktt9iqe.cloudfront.net/media/seo_landing_files/definition-of-identity-matrix-formula-and-examples-1628605305.png)

![Image](https://www.kodeclik.com/assets/numpy-eye-example.webp)

![Image](https://d138zd1ktt9iqe.cloudfront.net/media/seo_landing_files/definition-and-formula-of-a-diagonal-matrix-1628749102.png)

![Image](https://d138zd1ktt9iqe.cloudfront.net/media/seo_landing_files/diagonal-matrix-inverse-formula-1628749170.png)

### 🔸 `np.eye()`

Creates identity matrix.

```python
np.eye(3)
```

Output:

```
[[1. 0. 0.]
 [0. 1. 0.]
 [0. 0. 1.]]
```

---

## 🔹 2.6 Random Arrays

---

### 🔸 `np.random.rand()`

```python
np.random.rand(2,3)
```

Random numbers between 0 and 1.

---

### 🔸 `np.random.randint()`

```python
np.random.randint(1, 10, size=(3,3))
```

Random integers.

---

### 🔸 `np.random.randn()`

Normal distribution (mean=0, std=1)

```python
np.random.randn(2,2)
```

---

## 🔹 2.7 Copy vs View (Very Important)

This is a common interview question.

---

### 🔸 View (Shallow Copy)

```python
a = np.array([1,2,3])
b = a
b[0] = 100
```

Now:

```
a = [100 2 3]
```

Because both point to same memory.

---

### 🔸 Deep Copy

```python
b = a.copy()
```

Now changes in `b` will NOT affect `a`.

---

### 🔸 Checking Memory Address

```python
print(a.base)
```

If `None` → owns its data.

---

## 🔹 2.8 Reshaping During Creation

```python
np.arange(6).reshape(2,3)
```

Output:

```
[[0 1 2]
 [3 4 5]]
```

---

# 🧠 Internal Understanding

When you create:

```python
np.zeros((3,3))
```

Internally:

1. Memory block allocated
2. Continuous 9 elements stored
3. Type decided (default float64)

---

# 🎯 Interview Important Questions

1. Difference between arange and linspace?
2. What is identity matrix?
3. Difference between copy and view?
4. What does empty() do?
5. How memory is allocated?

---

# 📌 Summary of Topic 2

You learned:

✔ Creating arrays
✔ Special arrays
✔ Sequences
✔ Random arrays
✔ Identity matrix
✔ Copy vs View
✔ Dtype control

---