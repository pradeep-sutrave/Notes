
# 📘 NumPy – Topic 13: File Handling in NumPy (Save & Load Data)

NumPy provides efficient binary and text-based storage methods.

---

# 🔹 13.1 Why Use NumPy File Handling?

If you do:

```python
import pickle
```

or store data manually — it’s slower and less efficient.

NumPy provides:

✔ Fast binary storage
✔ Memory-efficient format
✔ Easy loading
✔ Compatible with ML pipelines

---

# 🔹 13.2 Saving Arrays (Binary Format) → `np.save()`

![Image](https://i.sstatic.net/DwdIr.png)

![Image](https://substackcdn.com/image/fetch/%24s_%214MGZ%21%2Cf_auto%2Cq_auto%3Agood%2Cfl_progressive%3Asteep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fcc69ef57-f1c4-4e65-a1e4-6669526d8ade_1368x900.png)

![Image](https://i.sstatic.net/4d6yo.png)

![Image](https://numpy.org/devdocs/_images/np_reshape.png)

---

### 🔸 Example

```python
import numpy as np

a = np.array([[1,2,3],
              [4,5,6]])

np.save("my_array.npy", a)
```

This creates:

```
my_array.npy
```

Binary format (.npy)

---

### 🔥 Why Binary?

* Faster than text
* Preserves dtype
* Preserves shape
* More compact

---

# 🔹 13.3 Loading Binary File → `np.load()`

```python
b = np.load("my_array.npy")
print(b)
```

Output:

```
[[1 2 3]
 [4 5 6]]
```

Everything restored:

✔ Shape
✔ Data type
✔ Values

---

# 🔹 13.4 Saving Multiple Arrays → `np.savez()`

If you want to save multiple arrays:

```python
np.savez("data.npz", arr1=a, arr2=b)
```

Creates:

```
data.npz
```

---

### Loading

```python
data = np.load("data.npz")

print(data["arr1"])
print(data["arr2"])
```

---

# 🔹 13.5 Saving as Text File → `np.savetxt()`

![Image](https://manifold.net/doc/mfd9/images/eg_formats_csv01_01.png)

![Image](https://i.sstatic.net/idAK0.png)

![Image](https://www.researchgate.net/publication/41848044/figure/fig2/AS%3A277443949678593%401443159200108/Simple-text-file-format-A-whole-investigation-can-be-stored-by-using-easy-to-create.png)

![Image](https://www.researchgate.net/publication/369199555/figure/fig2/AS%3A11431281126591445%401678764454558/The-bag-of-words-representation-of-documents-using-a-matrix-with-documents-as-rows-and.png)

Used when:

* Human-readable format needed
* Sharing with Excel
* Exporting to CSV

---

### Example

```python
np.savetxt("data.txt", a)
```

File content:

```
1.000000 2.000000 3.000000
4.000000 5.000000 6.000000
```

---

### Save as CSV

```python
np.savetxt("data.csv", a, delimiter=",")
```

---

# 🔹 13.6 Loading Text File → `np.loadtxt()`

```python
c = np.loadtxt("data.txt")
```

For CSV:

```python
c = np.loadtxt("data.csv", delimiter=",")
```

---

# 🔹 13.7 When to Use What?

| Method  | Use Case            |
| ------- | ------------------- |
| save    | Fast binary storage |
| load    | Load binary         |
| savez   | Multiple arrays     |
| savetxt | Human readable      |
| loadtxt | Read text data      |

---

# 🔹 13.8 Real ML Workflow Example

Imagine training a model:

```python
weights = np.random.randn(100,50)
```

Save weights:

```python
np.save("weights.npy", weights)
```

Later reload:

```python
weights = np.load("weights.npy")
```

No retraining needed.

---

# 🔹 13.9 Performance Difference

Binary format:

✔ Fast
✔ Small size
✔ Keeps metadata

Text format:

❌ Larger file
❌ Slower
✔ Human readable

---

# 🔹 13.10 Security Note

When loading files:

```python
np.load("file.npy", allow_pickle=False)
```

Safer option.

---

# 🧠 Internal Understanding

`.npy` file stores:

```text
Header (shape, dtype, metadata)
Raw binary data
```

That’s why loading is very fast.

---

# 🎯 Interview Questions

1. Difference between save and savetxt?
2. Why binary format is faster?
3. What is .npz file?
4. How to save multiple arrays?
5. Why loadtxt needs delimiter?

---

# 📌 Summary

You now understand:

✔ save
✔ load
✔ savez
✔ savetxt
✔ loadtxt
✔ Binary vs Text
✔ ML workflow usage

---