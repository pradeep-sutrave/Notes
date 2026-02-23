
# 📘 NumPy – Topic 6: Mathematical & Statistical Functions (Deep Guide)

---

# 🔹 6.1 Basic Aggregation Functions

![Image](https://i.sstatic.net/Z29Nn.jpg)

![Image](https://www.w3resource.com/w3r_images/numpy-math-image-exercise-19.svg)

![Image](https://i.sstatic.net/GyEtA.png)

![Image](https://files.realpython.com/media/NumPy-max-vs-amax-vs-maximum_Watermarked.47deb5fab721.jpg)

Let’s start with a 2D array:

```python
import numpy as np

a = np.array([[1,2,3],
              [4,5,6]])
```

---

## 🔸 `np.sum()`

### Total sum:

```python
np.sum(a)
```

Output:

```
21
```

---

## 🔸 `np.mean()`

```python
np.mean(a)
```

Output:

```
3.5
```

---

## 🔸 `np.min()` and `np.max()`

```python
np.min(a)   # 1
np.max(a)   # 6
```

---

## 🔸 `np.median()`

```python
np.median(a)
```

Output:

```
3.5
```

---

# 🔹 6.2 Understanding Axis (Very Important)

This is where most beginners get confused.

### What is Axis?

Axis refers to the **direction of operation**.

---

### 🔥 Axis 0 → Column-wise operation

### 🔥 Axis 1 → Row-wise operation

---

## Example:

```python
np.sum(a, axis=0)
```

Output:

```
[5 7 9]
```

Explanation:

```
(1+4) (2+5) (3+6)
```

Column-wise sum.

---

```python
np.sum(a, axis=1)
```

Output:

```
[6 15]
```

Explanation:

```
(1+2+3)
(4+5+6)
```

Row-wise sum.

---

# 🔥 Easy Trick to Remember

Axis number = Dimension that collapses.

* axis=0 → rows collapse → result per column
* axis=1 → columns collapse → result per row

---

# 🔹 6.3 Standard Deviation & Variance

Important in ML.

---

## 🔸 `np.std()`

Measures spread of data.

```python
np.std(a)
```

---

## 🔸 `np.var()`

Variance = square of std.

```python
np.var(a)
```

---

### With Axis

```python
np.std(a, axis=0)
```

Gives column-wise std.

---

# 🔹 6.4 Cumulative Functions

![Image](https://pythontic.com/cumsum.jpg)

![Image](https://journaldev.nyc3.cdn.digitaloceanspaces.com/2019/09/Python-numpy-cumsum.png)

![Image](https://i.sstatic.net/yGALz.png)

---

## 🔸 `np.cumsum()`

```python
a = np.array([1,2,3,4])
np.cumsum(a)
```

Output:

```
[1 3 6 10]
```

Running total.

---

## 🔸 `np.cumprod()`

```python
np.cumprod(a)
```

Output:

```
[1 2 6 24]
```

Running multiplication.

---

# 🔹 6.5 Other Useful Math Functions

NumPy provides many vectorized math functions:

```python
np.sqrt(a)
np.power(a,2)
np.abs(a)
np.exp(a)
np.log(a)
np.log10(a)
np.round(a)
np.floor(a)
np.ceil(a)
```

All operate element-wise.

---

# 🔹 6.6 Arg Functions (Important for Interviews)

Return index of min/max.

```python
np.argmax(a)
np.argmin(a)
```

For 2D:

```python
np.argmax(a, axis=0)
```

---

# 🔹 6.7 Percentiles

Used in statistics & ML.

```python
np.percentile(a, 50)
```

50th percentile = median.

---

# 🔹 6.8 Weighted Average

```python
values = np.array([1,2,3])
weights = np.array([0.2,0.3,0.5])

np.average(values, weights=weights)
```

Very useful in ML.

---

# 🧠 Internal Understanding

When you do:

```python
np.sum(a, axis=0)
```

NumPy:

1. Iterates internally in C
2. Reduces dimension
3. Returns new array with one less dimension

This is called a **reduction operation**.

---

# 🎯 Interview Questions

1. Difference between sum and cumsum?
2. What does axis=0 mean?
3. What is variance?
4. How to find index of maximum element?
5. What is reduction operation?

---

# 📌 Summary

You learned:

✔ Sum, mean, min, max
✔ Axis concept
✔ Std & variance
✔ Cumulative functions
✔ Arg functions
✔ Percentile
✔ Reduction operations


