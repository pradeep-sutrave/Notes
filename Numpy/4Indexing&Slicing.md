
# 📘 NumPy – Topic 4: Indexing and Slicing (Complete Deep Guide)

---

# 🔹 4.1 Basic Indexing (1D Arrays)

![Image](https://scipy-lectures.org/_images/numpy_fancy_indexing.png)

![Image](https://jalammar.github.io/images/numpy/numpy-array.png)

![Image](https://dphi-live.s3.amazonaws.com/media_uploads/image_90f5fdc17e2349c191f1dd878c3bca7c.png)

![Image](https://dphi-live.s3.amazonaws.com/media_uploads/image_5b22edf8316b434db20d19d2ac9d5bda.png)

### Example

```python
import numpy as np

a = np.array([10, 20, 30, 40, 50])
```

---

### 🔸 Access Single Element

```python
a[0]   # 10
a[2]   # 30
```

---

### 🔸 Negative Indexing

```python
a[-1]  # 50
a[-2]  # 40
```

Negative indexing starts from end.

---

# 🔹 4.2 Slicing (1D Arrays)

Syntax:

```python
array[start : stop : step]
```

---

### Example

```python
a[1:4]
```

Output:

```
[20 30 40]
```

---

### Step Example

```python
a[0:5:2]
```

Output:

```
[10 30 50]
```

---

### Reverse Array

```python
a[::-1]
```

Output:

```
[50 40 30 20 10]
```

---

# 🔥 Important Rule

Slicing creates a **view**, not a copy.

Example:

```python
b = a[1:4]
b[0] = 999
```

Now original `a` also changes.

This is very important.

---

# 🔹 4.3 Indexing in 2D Arrays

![Image](https://journaldev.nyc3.cdn.digitaloceanspaces.com/2020/03/2D-array-representation.png)

![Image](https://storage.googleapis.com/lds-media/images/numpy-indexing-arrays.width-1200.jpg)

![Image](https://www.mathworks.com/company/technical-articles/matrix-indexing-in-matlab/_jcr_content/mainParsys/columns_1735561276/c3733e7f-5a71-4d62-ac3f-bbd01c7a2563/image.adapt.full.medium.jpg/1727193217514.jpg)

![Image](https://mil-tokyo.github.io/sushi2/images/memory_layout_3d.png)

Example:

```python
b = np.array([[1,2,3],
              [4,5,6],
              [7,8,9]])
```

---

### 🔸 Access Single Element

```python
b[0,1]   # 2
b[2,2]   # 9
```

Format:

```python
array[row, column]
```

---

### 🔸 Access Entire Row

```python
b[1]
```

Output:

```
[4 5 6]
```

---

### 🔸 Access Entire Column

```python
b[:,1]
```

Output:

```
[2 5 8]
```

---

# 🔹 4.4 2D Slicing

### Example

```python
b[0:2, 1:3]
```

Output:

```
[[2 3]
 [5 6]]
```

Meaning:

* Rows: 0 to 1
* Columns: 1 to 2

---

### 🔥 Rule

```python
array[row_slice, column_slice]
```

---

# 🔹 4.5 Boolean Indexing (Very Important in ML)

![Image](https://matthew-brett.github.io/cfd2020/_images/easiness_values.png)

![Image](https://learn-attachment.microsoft.com/api/attachments/499986de-7759-4403-bcb4-52fffdc21d4a?platform=QnA)

![Image](https://i.sstatic.net/8kvPA.png)

![Image](https://df6asyv2kv4zi.cloudfront.net/select-elements-from-numpy-array-in-python/images/image_39118269971708607102192.png)

This is used for filtering data.

---

### Example

```python
a = np.array([10, 20, 30, 40, 50])

a > 25
```

Output:

```
[False False True True True]
```

Now use it:

```python
a[a > 25]
```

Output:

```
[30 40 50]
```

This is called **masking**.

---

### Real-world Example

Remove negative values:

```python
a[a >= 0]
```

---

# 🔹 4.6 Fancy Indexing

Using index arrays.

---

### Example

```python
a = np.array([10,20,30,40,50])

a[[0,2,4]]
```

Output:

```
[10 30 50]
```

You pass list of indices.

---

### 2D Fancy Indexing

```python
b[[0,2], :]
```

Selects rows 0 and 2.

---

# 🔹 4.7 Conditional Replacement

Replace values conditionally.

---

### Example

```python
a = np.array([10,20,30,40])

a[a > 25] = 0
```

Output:

```
[10 20 0 0]
```

Very useful in preprocessing.

---

# 🔹 4.8 Difference: Slice vs Fancy Indexing

| Feature            | Slice | Fancy |
| ------------------ | ----- | ----- |
| Returns            | View  | Copy  |
| Memory shared?     | Yes   | No    |
| Modifies original? | Yes   | No    |

This is a common interview question.

---

# 🧠 Internal Understanding

When you do:

```python
a[1:4]
```

NumPy does NOT copy data.

It creates:

```text
New metadata pointing to same memory block
```

Efficient and fast.

---

# 🎯 Interview Questions

1. Difference between slicing and fancy indexing?
2. What is boolean masking?
3. How to select column from 2D array?
4. How to reverse array?
5. Why slicing is faster?

---

# 📌 Summary

You now understand:

✔ 1D indexing
✔ 2D indexing
✔ Slicing
✔ Boolean indexing
✔ Fancy indexing
✔ Conditional replacement
✔ View vs Copy difference

---
