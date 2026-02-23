
# 📘 NumPy – Topic 7: Shape Manipulation (Complete Deep Guide)

This topic covers:

* `reshape()`
* `flatten()`
* `ravel()`
* `transpose()`
* `T`
* `expand_dims()`
* `squeeze()`

---

# 🔹 7.1 `reshape()` – Changing Shape Without Changing Data

![Image](https://miro.medium.com/1%2AlFZzE9PgKTRR8jlFI4EUtw.png)

![Image](https://i.sstatic.net/OUjlv.png)

![Image](https://files.realpython.com/media/reshape-c-and-fortran-order.6108f2cc8010.png)

![Image](https://miro.medium.com/v2/resize%3Afit%3A1400/1%2A2gr2mIweIusX1IPrMEz6jQ.png)

---

## 🔸 Example

```python
import numpy as np

a = np.arange(6)
print(a)
```

Output:

```
[0 1 2 3 4 5]
```

---

### Convert to 2×3 Matrix

```python
b = a.reshape(2,3)
print(b)
```

Output:

```
[[0 1 2]
 [3 4 5]]
```

---

## 🔥 Important Rule

Total elements must remain same.

```
Original size = 6
New shape must multiply to 6
```

Valid:

```
(2,3)
(3,2)
(1,6)
(6,1)
```

Invalid:

```
(4,2) ❌
```

---

## 🔸 Using `-1` (Automatic Calculation)

```python
a.reshape(3,-1)
```

NumPy calculates automatically.

Very useful in ML preprocessing.

---

# 🔹 7.2 `flatten()` vs `ravel()`

![Image](https://www.w3resource.com/w3r_images/numpy-manipulation-ndarray-flatten-function-image-1.png)

![Image](https://miro.medium.com/0%2AWyfYpMmIVogfufOK.png)

![Image](https://forums.ni.com/t5/image/serverpage/image-id/172184i68E789283309ABF9?v=v2)

![Image](https://i.sstatic.net/AjAC8.png)

Given:

```python
b = np.array([[1,2,3],
              [4,5,6]])
```

---

## 🔸 `flatten()`

```python
b.flatten()
```

Output:

```
[1 2 3 4 5 6]
```

✔ Returns **copy**
✔ Changes do NOT affect original

---

## 🔸 `ravel()`

```python
b.ravel()
```

Output:

```
[1 2 3 4 5 6]
```

✔ Returns **view** (if possible)
✔ Changes MAY affect original

---

### 🔥 Interview Difference

| Feature           | flatten         | ravel        |
| ----------------- | --------------- | ------------ |
| Copy?             | Yes             | No (usually) |
| Faster?           | Slightly slower | Faster       |
| Memory efficient? | No              | Yes          |

---

# 🔹 7.3 `transpose()` – Swapping Axes

![Image](https://scaler.com/topics/images/transpose-of-a-2x3-matrix.webp)

![Image](https://journaldev.nyc3.cdn.digitaloceanspaces.com/2019/09/numpy-array-transpose.png)

![Image](https://i.sstatic.net/hHZ2I.png)

![Image](https://i.sstatic.net/7Vppf.png)

Given:

```python
A = np.array([[1,2,3],
              [4,5,6]])
```

Shape:

```
(2,3)
```

---

## 🔸 Transpose

```python
A.T
```

Output:

```
[[1 4]
 [2 5]
 [3 6]]
```

New shape:

```
(3,2)
```

---

### Another Way

```python
np.transpose(A)
```

---

# 🔹 7.4 Transpose in 3D Arrays

For 3D arrays:

```python
np.transpose(array, axes=(1,0,2))
```

This rearranges dimensions.

Important in Deep Learning.

---

# 🔹 7.5 `expand_dims()` – Add New Axis

![Image](https://www.w3resource.com/w3r_images/numpy-manipulation-expand-dims-function-image-2.png)

![Image](https://www.w3resource.com/w3r_images/python-numpy-image-exercise-56.png)

![Image](https://miro.medium.com/1%2AlFZzE9PgKTRR8jlFI4EUtw.png)

![Image](https://miro.medium.com/v2/resize%3Afit%3A1400/1%2A2gr2mIweIusX1IPrMEz6jQ.png)

Given:

```python
a = np.array([1,2,3])
```

Shape:

```
(3,)
```

---

## 🔸 Add New Axis

```python
np.expand_dims(a, axis=0)
```

Shape:

```
(1,3)
```

---

```python
np.expand_dims(a, axis=1)
```

Shape:

```
(3,1)
```

---

🔥 Used heavily when adding batch dimension in ML.

---

# 🔹 7.6 `squeeze()` – Remove Extra Dimensions

Given:

```python
a = np.array([[[1,2,3]]])
```

Shape:

```
(1,1,3)
```

---

## 🔸 Remove dimensions of size 1

```python
np.squeeze(a)
```

New shape:

```
(3,)
```

---

# 🔹 7.7 Practical ML Example

Suppose image dataset:

```
(1000, 28, 28)
```

Flatten for ML model:

```python
data.reshape(1000, -1)
```

New shape:

```
(1000, 784)
```

Very common preprocessing step.

---

# 🧠 Internal Understanding

NumPy array contains:

```
Data Block + Shape + Strides + Dtype
```

When reshaping:

* Data remains same
* Only metadata (shape) changes

Unless copying is required.

---

# 🎯 Interview Questions

1. Difference between reshape and flatten?
2. Difference between flatten and ravel?
3. What does -1 mean in reshape?
4. What is transpose?
5. Why expand_dims is used in ML?

---

# 📌 Summary

You now understand:

✔ reshape
✔ flatten
✔ ravel
✔ transpose
✔ expand_dims
✔ squeeze
✔ Memory behavior