
# 📘 NumPy – Topic 5: Array Operations & Broadcasting (Complete Deep Guide)

---

# 🔹 5.1 Arithmetic Operations (Element-wise Operations)

![Image](https://www.w3resource.com/w3r_images/python-numpy-exercise-146.svg)

![Image](https://www.boardinfinity.com/blog/content/images/2022/11/Your-paragraph-text--48-.jpg)

![Image](https://pytorch.org/assets/images/inside-the-matrix/binary_part.jpg)

![Image](https://pytorch.org/assets/images/inside-the-matrix/matmul3.jpg)

NumPy performs operations **element-by-element**.

---

### Example

```python
import numpy as np

a = np.array([1,2,3])
b = np.array([4,5,6])
```

---

### 🔸 Addition

```python
a + b
```

Output:

```
[5 7 9]
```

---

### 🔸 Subtraction

```python
a - b
```

Output:

```
[-3 -3 -3]
```

---

### 🔸 Multiplication

```python
a * b
```

Output:

```
[4 10 18]
```

⚠ This is NOT matrix multiplication.
It is element-wise multiplication.

---

### 🔸 Division

```python
a / b
```

Output:

```
[0.25 0.4 0.5]
```

---

# 🔹 5.2 Scalar Operations

Operations with single value.

```python
a + 10
```

Output:

```
[11 12 13]
```

```python
a * 2
```

Output:

```
[2 4 6]
```

This works because of **broadcasting** (explained later).

---

# 🔹 5.3 Comparison Operations

```python
a = np.array([10,20,30,40])
```

---

### 🔸 Greater Than

```python
a > 20
```

Output:

```
[False False True True]
```

---

### 🔸 Equal

```python
a == 20
```

Output:

```
[False True False False]
```

These return **boolean arrays**.

Used heavily in filtering.

---

# 🔹 5.4 Logical Operations

Used with boolean arrays.

```python
np.logical_and(a > 10, a < 40)
```

Output:

```
[False True True False]
```

Other functions:

* `np.logical_or()`
* `np.logical_not()`

---

# 🔹 5.5 Matrix Multiplication (Important)

![Image](https://d138zd1ktt9iqe.cloudfront.net/media/seo_landing_files/multiplication-of-matrices-of-order-2-x-2-1627879189.png)

![Image](https://i.sstatic.net/HSp5c.png)

![Image](https://eli.thegreenplace.net/images/2015/matcomb.png)

![Image](https://kishorepv.github.io/images/51.png)

Matrix multiplication is different from `*`.

---

### Example

```python
A = np.array([[1,2],
              [3,4]])

B = np.array([[5,6],
              [7,8]])
```

---

### Using `dot()`

```python
np.dot(A, B)
```

---

### Using `@` Operator

```python
A @ B
```

Output:

```
[[19 22]
 [43 50]]
```

---

# 🔥 Difference Between `*` and `@`

| Operator | Meaning               |
| -------- | --------------------- |
| `*`      | Element-wise          |
| `@`      | Matrix multiplication |

Interview favorite question.

---

# 🔹 5.6 Broadcasting (The Real Power)

![Image](https://www.w3resource.com/w3r_images/python-numpy-image-exercise-60.png)

![Image](https://numpy.org/doc/stable/_images/broadcasting_5.png)

![Image](https://jakevdp.github.io/PythonDataScienceHandbook/figures/02.05-broadcasting.png)

![Image](https://scaler.com/topics/images/numpy-broadcasting-Image_1.webp)

Broadcasting allows operations between arrays of different shapes.

---

## 🔸 Example 1: Scalar Broadcasting

```python
a = np.array([1,2,3])
a + 10
```

Internally:

```
[1,2,3]
[10,10,10]
```

Result:

```
[11,12,13]
```

---

## 🔸 Example 2: 2D + 1D

```python
A = np.array([[1,2,3],
              [4,5,6]])

b = np.array([10,20,30])

A + b
```

Result:

```
[[11 22 33]
 [14 25 36]]
```

NumPy stretches `b` across rows.

---

# 🔥 Broadcasting Rules (Very Important)

Two arrays are compatible if:

1. Dimensions are equal OR
2. One of them is 1

Comparison happens from right to left.

---

### Example

Shape of A:

```
(2,3)
```

Shape of b:

```
(3,)
```

NumPy treats (3,) as:

```
(1,3)
```

Then stretches to:

```
(2,3)
```

---

## 🔴 Broadcasting Error Example

```python
A = np.array([[1,2,3],
              [4,5,6]])

b = np.array([1,2])
```

This gives error.

Because:

```
(2,3)
(2,)
```

Not compatible.

---

# 🔹 5.7 Power & Modulus

```python
a = np.array([2,3,4])

a ** 2
```

Output:

```
[4 9 16]
```

---

```python
a % 2
```

Output:

```
[0 1 0]
```

---

# 🔹 5.8 Universal Functions (ufuncs)

NumPy provides built-in vectorized functions:

```python
np.sqrt(a)
np.exp(a)
np.sin(a)
np.log(a)
```

These are faster than Python loops.

---

# 🧠 Internal Understanding

When broadcasting:

NumPy does NOT copy data.

It:

* Adjusts strides
* Virtually stretches array
* Performs vectorized operation in C

That is why it is efficient.

---

# 🎯 Interview Questions

1. Difference between `*` and `@`?
2. What is broadcasting?
3. Explain broadcasting rules.
4. Why NumPy operations are faster?
5. What is ufunc?

---

# 📌 Summary

You learned:

✔ Element-wise operations
✔ Scalar operations
✔ Comparison operations
✔ Logical operations
✔ Matrix multiplication
✔ Broadcasting rules
✔ Universal functions

---
