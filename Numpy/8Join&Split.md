

# 📘 NumPy – Topic 8: Joining & Splitting Arrays (Complete Deep Guide)

---

# 🔹 8.1 Concatenation (`np.concatenate()`)

![Image](https://www.includehelp.com/python/images/concatenate-2d-arrays-with-1d-array.jpg)

![Image](https://www.w3resource.com/w3r_images/numpy-manipulation-concatenate-function-image-a.png)

![Image](https://www.w3resource.com/w3r_images/python-numpy-image-exercise-58.png)

![Image](https://www.w3resource.com/w3r_images/numpy-manipulation-concatenate-function-image-1.png)

### 🔸 1D Example

```python
import numpy as np

a = np.array([1,2,3])
b = np.array([4,5,6])

np.concatenate((a,b))
```

Output:

```
[1 2 3 4 5 6]
```

---

## 🔸 2D Example

```python
A = np.array([[1,2],
              [3,4]])

B = np.array([[5,6],
              [7,8]])
```

---

### Axis = 0 (Row-wise join)

```python
np.concatenate((A,B), axis=0)
```

Output:

```
[[1 2]
 [3 4]
 [5 6]
 [7 8]]
```

Shape:

```
(4,2)
```

---

### Axis = 1 (Column-wise join)

```python
np.concatenate((A,B), axis=1)
```

Output:

```
[[1 2 5 6]
 [3 4 7 8]]
```

Shape:

```
(2,4)
```

---

# 🔥 Rule

To concatenate:

* All dimensions except concatenation axis must match.

---

# 🔹 8.2 `vstack()` – Vertical Stack

![Image](https://www.w3resource.com/w3r_images/numpy-manipulation-vstack-function-image-1.png)

![Image](https://www.w3resource.com/w3r_images/python-numpy-exercise-128.svg)

![Image](https://miro.medium.com/v2/resize%3Afit%3A1400/1%2AlFzT2UEpHRdSle9OxzFFyQ.png)

![Image](https://miro.medium.com/v2/resize%3Afit%3A1400/1%2AOOKSPKxT1TbeB9nig5t_Bg.jpeg)

Stacks row-wise.

```python
np.vstack((A,B))
```

Same as:

```
axis=0 concatenate
```

---

# 🔹 8.3 `hstack()` – Horizontal Stack

![Image](https://www.w3resource.com/w3r_images/numpy-manipulation-hstack-function-image-a.png)

![Image](https://www.w3resource.com/w3r_images/python-numpy-exercise-127.svg)

![Image](https://i.sstatic.net/Xreew.gif)

![Image](https://zoomchartswebstorage.blob.core.windows.net/blog/20250602-152258-mceu-471234293121748877779661.png)

Stacks column-wise.

```python
np.hstack((A,B))
```

Same as:

```
axis=1 concatenate
```

---

# 🔹 8.4 `np.stack()` – Add New Dimension

Very important difference.

```python
np.stack((a,b))
```

If:

```python
a = [1,2,3]
b = [4,5,6]
```

Result:

```
[[1 2 3]
 [4 5 6]]
```

Shape becomes:

```
(2,3)
```

Difference:

| concatenate          | stack               |
| -------------------- | ------------------- |
| joins existing axis  | creates new axis    |
| dimension stays same | dimension increases |

---

# 🔹 8.5 Splitting Arrays

![Image](https://www.w3resource.com/w3r_images/python-numpy-image-exercise-131.svg)

![Image](https://www.w3resource.com/w3r_images/numpy-manipulation-array-hsplit-function-image-2.png)

![Image](https://www.w3resource.com/w3r_images/numpy-manipulation-array-vsplit-function-image-2.png)

![Image](https://www.w3resource.com/w3r_images/numpy-manipulation-vsplit-function-image-a.png)

---

## 🔸 `np.split()`

```python
a = np.array([1,2,3,4,5,6])

np.split(a, 3)
```

Output:

```
[array([1,2]),
 array([3,4]),
 array([5,6])]
```

---

# 🔹 8.6 `vsplit()` – Split Row-wise

```python
np.vsplit(A, 2)
```

Splits matrix into row blocks.

---

# 🔹 8.7 `hsplit()` – Split Column-wise

```python
np.hsplit(A, 2)
```

Splits into column blocks.

---

# 🔥 Important Rule

Split requires equal division.

Example:

```python
np.split(a, 4) ❌
```

If elements not divisible → error.

---

# 🔹 8.8 Practical ML Example

Suppose dataset:

```python
data = np.random.rand(100,5)
```

Split features and labels:

```python
X = data[:,:4]
y = data[:,4]
```

Or:

```python
train, test = np.split(data, [80])
```

Very common in ML.

---

# 🧠 Internal Understanding

* Concatenation copies data.
* Stack increases dimension.
* Split creates views (usually).

Memory allocation happens for joined arrays.

---

# 🎯 Interview Questions

1. Difference between concatenate and stack?
2. Difference between vstack and hstack?
3. What happens if dimensions mismatch?
4. Can split create unequal parts?
5. Why stack increases dimension?

---

# 📌 Summary

You now understand:

✔ concatenate
✔ vstack
✔ hstack
✔ stack
✔ split
✔ vsplit
✔ hsplit
✔ Axis-based joining

---
