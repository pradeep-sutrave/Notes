
# 🚀 NumPy Practice Problems (Basic → Advanced → Interview Level)

Since you're a CSE student building strong fundamentals, these problems are structured like:

* 🟢 Level 1: Foundation
* 🟡 Level 2: Intermediate
* 🔴 Level 3: Advanced / Interview
* 🧠 Level 4: ML-Oriented

Try solving before looking at solution (I’ll give hints only).

---

# 🟢 LEVEL 1 – Basics (Concept Strengthening)

---

### 🔹 Q1. Create a NumPy array of numbers from 10 to 50.

Expected Output:

```
[10 11 12 ... 50]
```

Hint: Use `arange()`.

---

### 🔹 Q2. Create a 3×3 matrix filled with zeros.

Hint: `zeros()`.

---

### 🔹 Q3. Create a 3×3 identity matrix.

Hint: `eye()`.

---

### 🔹 Q4. Generate 5 random numbers between 0 and 1.

Hint: `random.rand()`.

---

### 🔹 Q5. Find the shape, size, and dtype of:

```python
a = np.array([[1,2,3],
              [4,5,6]])
```

---

# 🟡 LEVEL 2 – Indexing & Operations

---

### 🔹 Q6. From this array:

```python
a = np.arange(10, 51)
```

Extract all even numbers.

Expected:

```
[10 12 14 ... 50]
```

Hint: Boolean indexing.

---

### 🔹 Q7. Reverse this array:

```python
a = np.array([1,2,3,4,5])
```

Expected:

```
[5 4 3 2 1]
```

---

### 🔹 Q8. Replace all values greater than 25 with 100.

```python
a = np.array([10,20,30,40,50])
```

Expected:

```
[10 20 100 100 100]
```

---

### 🔹 Q9. Add two arrays element-wise.

```python
a = np.array([1,2,3])
b = np.array([4,5,6])
```

---

### 🔹 Q10. Multiply this matrix by 2:

```python
A = np.array([[1,2],
              [3,4]])
```

---

# 🟡 LEVEL 3 – Broadcasting & Shape

---

### 🔹 Q11. Reshape array:

```python
a = np.arange(12)
```

Into shape (3,4).

---

### 🔹 Q12. Add 10 to each column of:

```python
A = np.array([[1,2,3],
              [4,5,6]])
```

Using broadcasting.

---

### 🔹 Q13. Flatten a 2D array.

---

### 🔹 Q14. Transpose:

```python
A = np.array([[1,2,3],
              [4,5,6]])
```

---

### 🔹 Q15. Stack two arrays vertically.

---

# 🔴 LEVEL 4 – Linear Algebra

---

### 🔹 Q16. Perform matrix multiplication:

```python
A = np.array([[1,2],
              [3,4]])

B = np.array([[5,6],
              [7,8]])
```

---

### 🔹 Q17. Find determinant of:

```python
A = np.array([[1,2],
              [3,4]])
```

---

### 🔹 Q18. Find inverse of A.

---

### 🔹 Q19. Solve:

[
Ax = B
]

Where:

```python
A = np.array([[3,1],
              [1,2]])

B = np.array([9,8])
```

Hint: `solve()`.

---

### 🔹 Q20. Find eigenvalues of:

```python
A = np.array([[2,0],
              [0,3]])
```

---

# 🧠 LEVEL 5 – ML-Oriented Problems

---

### 🔹 Q21. Normalize this dataset column-wise:

```python
X = np.array([[1000, 25],
              [1500, 30],
              [2000, 35]])
```

---

### 🔹 Q22. Standardize this dataset.

---

### 🔹 Q23. Generate random dataset of shape (100,5) and split 80-20.

---

### 🔹 Q24. Replace all negative values with 0.

---

### 🔹 Q25. Create one-hot encoding for:

```python
labels = np.array([0,1,2,1])
```

---

# 🔥 Bonus Interview Problems

---

### 🔹 Q26. What is difference between:

```python
a.flatten()
a.ravel()
```

Explain with example.

---

### 🔹 Q27. Why broadcasting does not copy memory?

---

### 🔹 Q28. What are strides?

---

### 🔹 Q29. Explain C-order vs F-order.

---

### 🔹 Q30. Why NumPy is faster than Python lists?

---