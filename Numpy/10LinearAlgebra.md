
# 📘 NumPy – Topic 10: Linear Algebra in NumPy (Deep & Complete Guide)

Linear algebra is handled inside NumPy using:

```python
np.linalg
```

---

# 🔹 10.1 Matrix Multiplication

![Image](https://d138zd1ktt9iqe.cloudfront.net/media/seo_landing_files/multiplication-of-matrices-of-order-2-x-2-1627879189.png)

![Image](https://i.sstatic.net/HSp5c.png)

![Image](https://eli.thegreenplace.net/images/2015/matcomb.png)

![Image](https://miro.medium.com/1%2AEgM20_NbF3p6xxu7LTSzrQ.png)

---

## 🔸 Example

```python
import numpy as np

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

### Using `@` Operator (Recommended)

```python
A @ B
```

Output:

```
[[19 22]
 [43 50]]
```

---

### 🔥 Important Rule

Matrix multiplication is valid only if:

```
(columns of A) = (rows of B)
```

---

# 🔹 10.2 Determinant

![Image](https://cdn.virtualnerd.com/thumbnails/Alg2_04_01_0017-diagram_thumb-lg.png)

![Image](https://images.openai.com/static-rsc-3/zmkOa3nQb6zmnZUUkhKg9U4_ZVF_3PCugEYXEFNlesB7pVEuPTceD9HM0oJAQxj9syZ-kudPpktZDEvXZ9GAwOKOTQ6EfheC-nYCPHFDKpA?purpose=fullsize\&v=1)

![Image](https://df6asyv2kv4zi.cloudfront.net/calculate-determinant-of-matrix-or-ndarray/images/python_matrix_determinant_without_numpy.webp)

![Image](https://www.thesecuritybuddy.com/wordpress/bdr/uploads/2023/10/Determinant.jpg)

The determinant tells:

* If matrix is invertible
* Scaling factor of transformation

---

## 🔸 Example

```python
np.linalg.det(A)
```

For:

```
|1 2|
|3 4|
```

Determinant:

```
(1×4) − (2×3) = -2
```

If determinant = 0 → matrix is singular (not invertible)

---

# 🔹 10.3 Inverse of Matrix

![Image](https://study.com/cimages/videopreview/videopreview-full/t6pcny4dk8.jpg)

![Image](https://df6asyv2kv4zi.cloudfront.net/invert-matrix-or-narray-in-python/images/Python_inverse_matrix_without_NumPy.webp)

![Image](https://images.openai.com/static-rsc-3/KJkM1fmwZQIxYosQ518k41LO2k3XV6k-SD9tpYr_UQZ5ifNW2SacKMJrVRdhJZB3gCJ5n8SsZZk2ES3dCaXwul8YQdd3fNjSHQr2cbCHZJ0?purpose=fullsize\&v=1)

![Image](https://www.3blue1brown.com/content/lessons/2016/inverse-matrices/rotation_inverse.svg)

Only possible if determinant ≠ 0.

---

### Example

```python
np.linalg.inv(A)
```

---

### Verification

```python
A @ np.linalg.inv(A)
```

Output ≈ Identity matrix

```
[[1 0]
 [0 1]]
```

---

# 🔹 10.4 Identity Matrix

```python
np.eye(3)
```

Output:

```
[[1 0 0]
 [0 1 0]
 [0 0 1]]
```

Used in:

* ML regularization
* Linear equation solving

---

# 🔹 10.5 Solving Linear Equations

Suppose:

```
Ax = B
```

Instead of:

```
x = inv(A) @ B  ❌ (not recommended)
```

Use:

```python
np.linalg.solve(A, B)
```

Faster and numerically stable.

---

# 🔹 10.6 Eigenvalues & Eigenvectors

![Image](https://study.com/cimages/multimages/16/ev2x2_pt3.png)

![Image](https://setosa.io/ev/eigenvectors-and-eigenvalues/fb-thumb.png)

![Image](https://www.includehelp.com/python/images/linalg-eig-and-linalg-eigh.jpg)

![Image](https://scriptverse.academy/img/tutorials/python-eigenvalues-eigenvectors-output-labels.png)

Very important in:

* PCA (Principal Component Analysis)
* ML dimensionality reduction
* Stability analysis

---

## 🔸 Example

```python
values, vectors = np.linalg.eig(A)
```

* `values` → Eigenvalues
* `vectors` → Eigenvectors

---

### Meaning

Eigenvector:

Direction that does not change after transformation.

Eigenvalue:

Scaling factor in that direction.

---

# 🔹 10.7 Matrix Rank

```python
np.linalg.matrix_rank(A)
```

Rank tells:

* Number of independent rows
* System solvability

---

# 🔹 10.8 Norm of Matrix

Used in ML for regularization.

```python
np.linalg.norm(A)
```

Different norms:

* L1 norm
* L2 norm
* Frobenius norm

---

# 🔹 10.9 Trace of Matrix

```python
np.trace(A)
```

Sum of diagonal elements.

---

# 🔹 10.10 Practical ML Example

Suppose dataset:

```python
X = np.random.rand(100, 3)
```

Compute covariance matrix:

```python
cov = np.cov(X.T)
```

Then eigenvalues for PCA:

```python
values, vectors = np.linalg.eig(cov)
```

This is real ML pipeline.

---

# 🧠 Internal Understanding

When you call:

```python
np.linalg.inv(A)
```

NumPy internally calls:

* LAPACK (Linear Algebra Package)
* Highly optimized C/Fortran code

That’s why it is fast.

---

# 🔥 Common Mistakes

❌ Using `*` instead of `@`
❌ Using inverse to solve equations
❌ Ignoring determinant before inverse
❌ Shape mismatch in multiplication

---

# 🎯 Interview Questions

1. Difference between `*` and `@`?
2. What is determinant?
3. When matrix is invertible?
4. What are eigenvalues?
5. Why use solve() instead of inverse?
6. What is rank?

---

# 📌 Summary

You now understand:

✔ Matrix multiplication
✔ Determinant
✔ Inverse
✔ Identity matrix
✔ Solving equations
✔ Eigenvalues & eigenvectors
✔ Rank
✔ Norm
✔ Trace

---
