
# 📘 NumPy – Topic 12: Advanced NumPy (Memory, Views, Strides, Vectorization)

---

# 🔹 12.1 Views vs Copies (Deep Understanding)

You already saw basic idea. Now let’s go deeper.

![Image](https://www.scaler.com/topics/images/copies-and-views-in-numpy_thumbnail.webp)

![Image](https://i.sstatic.net/EeBUb.png)

![Image](https://www.pythoninformer.com/img/numpy/3d-array-slice.png)

![Image](https://miro.medium.com/v2/resize%3Afit%3A1400/1%2AW9DYV8pLr8AKVXJefwJBng.png)

---

## 🔸 View (No New Memory)

```python
import numpy as np

a = np.array([1,2,3,4])
b = a[1:3]
```

Here:

* `b` is a view
* Both share same memory

If:

```python
b[0] = 100
```

Now:

```python
a → [1,100,3,4]
```

---

### How to Check?

```python
b.base
```

If not `None` → it is a view.

---

## 🔸 Copy (New Memory Allocated)

```python
c = a.copy()
```

Now changes in `c` won’t affect `a`.

---

### 🔥 Interview Question

Why slicing returns view?

Answer:

> To avoid unnecessary memory allocation and improve performance.

---

# 🔹 12.2 Memory Layout (C-order vs F-order)

![Image](https://upload.wikimedia.org/wikipedia/commons/thumb/4/4d/Row_and_column_major_order.svg/960px-Row_and_column_major_order.svg.png)

![Image](https://d8it4huxumps7.cloudfront.net/uploads/images/6851382354377_memory_layout_in_c_inside.jpg?d=2000x2000)

![Image](https://eli.thegreenplace.net/images/2015/row-major-2D.png)

![Image](https://wolf.hece.uliege.be/_images/tutorials_Fortran_C_order_30_1.png)

NumPy stores arrays in:

### 🔸 C-order (Row-major) – Default

Memory layout:

```
Row 1 → Row 2 → Row 3
```

Example:

```python
A = np.array([[1,2,3],
              [4,5,6]])
```

Stored in memory as:

```
1 2 3 4 5 6
```

---

### 🔸 Fortran-order (Column-major)

Stored as:

```
1 4 2 5 3 6
```

You can create:

```python
np.array(A, order='F')
```

---

# 🔹 12.3 Strides (Very Important)

Strides tell:

> How many bytes to jump in memory to move to next element.

---

Example:

```python
a = np.array([[1,2,3],
              [4,5,6]], dtype=np.int32)

a.strides
```

Output example:

```
(12, 4)
```

Meaning:

* To move to next row → jump 12 bytes
* To move to next column → jump 4 bytes

Why?

Each int32 = 4 bytes
Row has 3 elements → 3×4 = 12 bytes

---

### 🔥 Why Strides Matter?

Broadcasting works by manipulating strides — not copying data.

---

# 🔹 12.4 Vectorization (Performance Booster)

![Image](https://benediktehinger.de/blog/science/upload/sites/2/2017/11/matlab_comparison.png)

![Image](https://www.scaler.com/topics/images/np-vectorize-thumbnail.webp)

![Image](https://i.sstatic.net/LLd64.png)

![Image](https://i.sstatic.net/uKN3R.png)

---

### ❌ Slow Way (Python Loop)

```python
for i in range(len(a)):
    a[i] = a[i] * 2
```

---

### ✅ Fast Way (Vectorized)

```python
a = a * 2
```

Why faster?

* Runs in C
* No Python loop overhead
* Uses SIMD CPU instructions

---

# 🔹 12.5 Broadcasting Internals

When shapes differ:

NumPy:

1. Aligns dimensions from right
2. Expands dimensions of size 1
3. Adjusts strides
4. Does not copy data

This makes operations memory efficient.

---

# 🔹 12.6 Memory Efficiency Example

```python
a = np.ones((1000,1000))
b = a[:, :500]
```

`b` is just a view.

No new 500k elements copied.

Huge memory saving.

---

# 🔹 12.7 `np.where()` (Advanced Filtering)

```python
a = np.array([10,20,30,40])

np.where(a > 25)
```

Returns indices.

---

Conditional replacement:

```python
np.where(a > 25, 1, 0)
```

Output:

```
[0 0 1 1]
```

Very useful in ML preprocessing.

---

# 🔹 12.8 `np.clip()`

Limit values in range.

```python
np.clip(a, 15, 35)
```

Output:

```
[15 20 30 35]
```

Used in gradient clipping in ML.

---

# 🔹 12.9 `np.unique()`

```python
np.unique([1,2,2,3,3,3])
```

Output:

```
[1 2 3]
```

With counts:

```python
np.unique(a, return_counts=True)
```

---

# 🔹 12.10 Performance Comparison

NumPy is faster because:

* Contiguous memory
* C backend
* SIMD instructions
* Avoids Python overhead
* Efficient memory strides

---

# 🧠 Internal Architecture of ndarray

An ndarray consists of:

```
Data Buffer
Shape
Dtype
Strides
Flags
```

This is why reshaping is cheap — only metadata changes.

---

# 🎯 Interview Questions

1. Difference between view and copy?
2. What are strides?
3. What is C-order?
4. Why vectorization is faster?
5. How broadcasting avoids memory copy?
6. What is np.where?

---

# 📌 Summary

You now understand:

✔ View vs Copy (deep level)
✔ Memory layout
✔ Strides
✔ Vectorization
✔ Broadcasting internals
✔ where
✔ clip
✔ unique
✔ Performance concepts
