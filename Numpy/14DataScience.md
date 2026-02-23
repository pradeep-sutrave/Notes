

# 📘 NumPy – Topic 14: NumPy for Data Science (Feature Scaling & Preprocessing)

---

# 🔹 14.1 Why Preprocessing is Needed?

In Machine Learning:

Different features may have different scales.

Example:

| Feature | Range              |
| ------- | ------------------ |
| Age     | 0 – 100            |
| Salary  | 10,000 – 1,000,000 |
| Rating  | 1 – 5              |

Large-scale features dominate small ones.

So we scale them.

---

# 🔹 14.2 Normalization (Min-Max Scaling)

![Image](https://static-assets.codecademy.com/Paths/data-science-career-path/MachineLearning/outlier.png)

![Image](https://miro.medium.com/v2/resize%3Afit%3A1400/1%2Ap5ME1RpYfIWidAnMOrf0rg.png)

![Image](https://i.sstatic.net/vZ3Uw.png)

![Image](https://i.sstatic.net/J1Vdp.png)

---

## 🔸 Formula

[
X_{norm} = \frac{X - X_{min}}{X_{max} - X_{min}}
]

Range becomes:

```text
0 to 1
```

---

## 🔸 Example

```python
import numpy as np

data = np.array([10,20,30,40,50])

normalized = (data - np.min(data)) / (np.max(data) - np.min(data))

print(normalized)
```

Output:

```
[0.   0.25 0.5  0.75 1.  ]
```

---

## 🔥 When to Use?

* Neural Networks
* KNN
* Distance-based algorithms

---

# 🔹 14.3 Standardization (Z-score Scaling)

![Image](https://images.openai.com/static-rsc-3/fYiynQLZ_BAK48YKf-783NUdJehceQdhi6-oZb99LGTXSZ4-TxVhzj0fHeDoFTmq6aBkwagO85ac6vxS_BHTOHioA3otpoO6ntGJQL5nqdE?purpose=fullsize\&v=1)

![Image](https://www.researchgate.net/publication/270813044/figure/fig2/AS%3A667717396869122%401536207641481/The-z-distribution-a-standardised-normal-distribution-with-mean-0-and-standard-deviation.ppm)

![Image](https://static-assets.codecademy.com/Paths/data-science-career-path/MachineLearning/z-score.png)

![Image](https://cdn-images-1.medium.com/max/729/0%2AmvQMxnXztGZU_9zP)

---

## 🔸 Formula

[
X_{std} = \frac{X - \mu}{\sigma}
]

Where:

* μ = mean
* σ = standard deviation

Result:

* Mean ≈ 0
* Std ≈ 1

---

## 🔸 Example

```python
data = np.array([10,20,30,40,50])

standardized = (data - np.mean(data)) / np.std(data)

print(standardized)
```

---

## 🔥 When to Use?

* Logistic Regression
* SVM
* PCA
* Linear Regression

---

# 🔹 14.4 Feature Scaling in 2D Dataset

Example dataset:

```python
X = np.array([[1000, 25],
              [1500, 30],
              [2000, 35]])
```

Normalize column-wise:

```python
X_norm = (X - np.min(X, axis=0)) / (np.max(X, axis=0) - np.min(X, axis=0))
```

Note:

```text
axis=0 → column-wise
```

---

# 🔹 14.5 Handling Missing Values

Replace NaN values:

```python
data = np.array([1,2,np.nan,4])

np.nan_to_num(data)
```

Replace with mean:

```python
mean_value = np.nanmean(data)
data[np.isnan(data)] = mean_value
```

Very important in data cleaning.

---

# 🔹 14.6 One-Hot Encoding (Basic Implementation)

Suppose categories:

```python
labels = np.array([0,1,2,1])
```

One-hot:

```python
one_hot = np.eye(3)[labels]
```

Output:

```
[[1 0 0]
 [0 1 0]
 [0 0 1]
 [0 1 0]]
```

Used in classification problems.

---

# 🔹 14.7 Train-Test Split Using NumPy

```python
data = np.random.rand(100,5)

indices = np.random.permutation(len(data))

train_size = int(0.8 * len(data))

train_idx = indices[:train_size]
test_idx = indices[train_size:]

train = data[train_idx]
test = data[test_idx]
```

Core ML preprocessing concept.

---

# 🔹 14.8 Feature Engineering Example

Polynomial feature:

```python
x = np.array([1,2,3])

x_squared = x**2
```

Add bias column:

```python
X = np.column_stack((np.ones(len(x)), x))
```

Used in linear regression.

---

# 🔹 14.9 Correlation Matrix

```python
np.corrcoef(X.T)
```

Used to check multicollinearity.

---

# 🔹 14.10 Covariance Matrix

```python
np.cov(X.T)
```

Used in PCA.

---

# 🧠 Complete ML Preprocessing Pipeline Example

```python
X = np.random.rand(100,3)

# Standardize
X = (X - np.mean(X, axis=0)) / np.std(X, axis=0)

# Shuffle
np.random.shuffle(X)

# Split
train, test = np.split(X, [80])
```

This is real-world ML preparation.

---

# 🎯 Interview Questions

1. Difference between normalization and standardization?
2. When to use which?
3. Why scaling is important?
4. How to handle missing values in NumPy?
5. How to implement one-hot encoding using NumPy?
6. Why axis=0 used in scaling?

---

# 📌 Final NumPy Syllabus Summary

You have now completed:

1. Introduction
2. Array Creation
3. Attributes
4. Indexing & Slicing
5. Operations & Broadcasting
6. Math & Statistics
7. Shape Manipulation
8. Joining & Splitting
9. Iteration
10. Linear Algebra
11. Random Module
12. Advanced Concepts
13. File Handling
14. Data Science Applications

---

