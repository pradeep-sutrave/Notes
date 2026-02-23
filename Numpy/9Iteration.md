
# 📘 NumPy – Topic 9: Iterating Over Arrays & `nditer` (Deep Guide)

---

# 🔹 9.1 Iterating Over 1D Arrays

![Image](https://i.sstatic.net/O7YXR.png)

![Image](https://i.sstatic.net/EeBUb.png)

![Image](https://talentbattle.in/Files/C4U_Images/C4U_CKEDITOR_IMAGES/IMG12622_Arrays%20%286%29.png)

![Image](https://scaler.com/topics/images/1-%281%29.webp)

### Example

```python
import numpy as np

a = np.array([10,20,30,40])
```

---

### Basic Loop

```python
for element in a:
    print(element)
```

Output:

```
10
20
30
40
```

✔ Iterates element by element
✔ Works like Python list

---

# 🔹 9.2 Iterating Over 2D Arrays

![Image](https://i.sstatic.net/O7YXR.png)

![Image](https://www.mathworks.com/content/dam/mathworks/videos/m/Making-a-Matrix-in-a-Loop-R2017a.mp4/jcr%3Acontent/renditions/cq5dam.user-uploaded-1.thumbnail.640.360.png)

![Image](https://journaldev.nyc3.cdn.digitaloceanspaces.com/2020/03/2D-array-representation.png)

![Image](https://courses.cs.washington.edu/courses/cse121/24su/resources/cheatsheets/images/2D_Array_Visual.png)

Example:

```python
b = np.array([[1,2,3],
              [4,5,6]])
```

---

### Iterating Row-wise

```python
for row in b:
    print(row)
```

Output:

```
[1 2 3]
[4 5 6]
```

Notice: It gives full rows.

---

### Iterating Element-wise (Nested Loop)

```python
for row in b:
    for element in row:
        print(element)
```

Output:

```
1 2 3 4 5 6
```

---

# 🔹 9.3 Iterating Over 3D Arrays

Example:

```python
c = np.array([
    [[1,2],[3,4]],
    [[5,6],[7,8]]
])
```

Loop:

```python
for block in c:
    print(block)
```

Returns 2D matrices.

---

# 🔹 9.4 `np.nditer()` – Efficient Multi-Dimensional Iterator

![Image](https://s3.ap-south-1.amazonaws.com/s3.studytonight.com/tutorials/uploads/pictures/1598422658-71449.png)

![Image](https://miro.medium.com/v2/resize%3Afit%3A1400/1%2AQMrmnjHjCt0YH7lVrltwMQ.jpeg)

![Image](https://www.w3resource.com/w3r_images/numpy-manipulation-ndarray-flat-function-image.png)

![Image](https://www.includehelp.com/python/images/flatten-numpy-array.jpg)

`nditer` allows efficient element-wise traversal.

---

### Example

```python
for element in np.nditer(b):
    print(element)
```

Output:

```
1 2 3 4 5 6
```

✔ Works for any dimension
✔ More efficient internally

---

# 🔹 9.5 Modifying Values During Iteration

Normally:

```python
for x in b:
    x = x * 2   ❌
```

This won’t modify original array.

---

### Correct Way

```python
for x in np.nditer(b, op_flags=['readwrite']):
    x[...] = x * 2
```

Now array updates.

---

# 🔹 9.6 Iterating With Index

Sometimes we need index positions.

---

### Using `ndenumerate`

```python
for index, value in np.ndenumerate(b):
    print(index, value)
```

Output:

```
(0,0) 1
(0,1) 2
(0,2) 3
(1,0) 4
(1,1) 5
(1,2) 6
```

Very useful in debugging.

---

# 🔹 9.7 Flat Iterator

```python
for element in b.flat:
    print(element)
```

Flattens internally and iterates.

---

# 🔹 9.8 Why Loops Are Slow in NumPy?

Because:

* Python loops run in Python interpreter
* NumPy vectorized operations run in C

Example:

```python
# Slow
for i in range(len(a)):
    a[i] = a[i] * 2
```

Better:

```python
a = a * 2
```

Always prefer vectorization.

---

# 🔹 9.9 Performance Understanding

NumPy array stores:

```
Data Block + Metadata + Strides
```

`nditer` respects memory layout and strides for efficient traversal.

---

# 🔥 When Should You Use Iteration?

Use loops when:

✔ Writing custom logic
✔ Complex element-wise conditions
✔ Debugging
✔ Educational understanding

Avoid loops when:

❌ Doing simple math
❌ Performing reductions
❌ Filtering

---

# 🎯 Interview Questions

1. Why vectorization is faster than loops?
2. What is nditer?
3. How to modify array during iteration?
4. What does flat do?
5. Why loops are discouraged in NumPy?

---

# 📌 Summary

You now understand:

✔ 1D iteration
✔ 2D iteration
✔ Nested iteration
✔ nditer
✔ ndenumerate
✔ flat iterator
✔ Performance differences
