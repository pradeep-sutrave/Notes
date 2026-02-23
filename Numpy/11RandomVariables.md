

# 📘 NumPy – Topic 11: Random Module (Complete Deep Guide)

NumPy provides random functions under:

```python
np.random
```

⚠ In modern NumPy, `np.random.default_rng()` is recommended, but we’ll first understand the classic approach (important for interviews).

---

# 🔹 11.1 Why Random Module is Important?

Used for:

* Initializing neural network weights
* Creating dummy datasets
* Random sampling
* Statistical simulations
* Shuffling data

---

# 🔹 11.2 Random Numbers Between 0 and 1 → `rand()`

![Image](https://www.itl.nist.gov/div898/handbook/eda/section3/gif/unipdf.gif)

![Image](https://i.sstatic.net/JpdwO.png)

![Image](https://i.sstatic.net/lleYw.png)

![Image](https://i.sstatic.net/7AMH1.png)

---

### Example

```python
import numpy as np

np.random.rand(3)
```

Output (example):

```
[0.23 0.91 0.45]
```

Range:

```
0 ≤ value < 1
```

---

### 2D Example

```python
np.random.rand(2,3)
```

Creates 2×3 matrix.

---

# 🔹 11.3 Random Integers → `randint()`

```python
np.random.randint(low, high, size)
```

---

### Example

```python
np.random.randint(1, 10, size=(2,3))
```

Output example:

```
[[3 7 1]
 [9 2 6]]
```

Range:

```
1 ≤ value < 10
```

---

# 🔹 11.4 Normal Distribution → `randn()`

![Image](https://images.openai.com/static-rsc-3/-PWhk6QHW0GXrfnk-_nKyK8jkoN-8qJ_6iWHfZGjeaPGjmMPrGoqacNLWY6caIO1ZUrcijKx8KiyZqBOH2ZBbNt3oPZAOcH63Pi-s1MmET0?purpose=fullsize\&v=1)

![Image](https://numpy.org/doc/2.1/_images/numpy-random-normal-1_00_00.png)

![Image](https://images.openai.com/static-rsc-3/HMkVGoIIx3g8ruUvI9GLxtpIPjK9UPJ2Pp9lEdFzy9eN7lJYzxa53KJ3tMG10Ym2vtOsIeBw1yh1rWuZyUzQoXwJglfFWUUr5oP44PNh368?purpose=fullsize\&v=1)

![Image](https://images.openai.com/static-rsc-3/CzA7gSTUuKbQnJjyWo2XhLwMDFUwgAxm03kSGJZKeXNn4hGvY7htVW5Q7v0cwAix2mmTx1KhXQrYW8MeV82QG38V5ZOoCx46ce1p_TNtVxY?purpose=fullsize\&v=1)

Generates values from:

```
Mean = 0
Standard deviation = 1
```

---

### Example

```python
np.random.randn(5)
```

Output example:

```
[-0.45  0.89 -1.2  0.33  0.1]
```

Used heavily in ML weight initialization.

---

# 🔹 11.5 Random Choice → `choice()`

Select random values from array.

---

### Example

```python
a = np.array([10,20,30,40])

np.random.choice(a)
```

Returns single random element.

---

### Multiple Choice

```python
np.random.choice(a, size=3)
```

---

### With Probabilities

```python
np.random.choice(a, size=5, p=[0.1,0.2,0.3,0.4])
```

Used in probability simulations.

---

# 🔹 11.6 Shuffle

Randomly rearranges elements.

---

### Example

```python
a = np.array([1,2,3,4,5])

np.random.shuffle(a)
```

Modifies original array.

---

# 🔹 11.7 Seed (Very Important)

![Image](https://www.researchgate.net/publication/366266834/figure/fig1/AS%3A11431281115096172%401674758909327/A-visualization-of-the-spread-of-results-of-the-random-seed-variation-experiment-The.jpg)

![Image](https://miro.medium.com/v2/resize%3Afit%3A1360/1%2AeVSON0Yh-j89b1xgLI_H7A.png)

![Image](https://i.sstatic.net/VqYPm.png)

![Image](https://forums.fast.ai/uploads/default/original/3X/e/0/e0f60236eaad8d5b55bcc3e0e6eda7a3537f0686.png)

Seed ensures reproducibility.

---

### Example

```python
np.random.seed(42)
np.random.rand(3)
```

Every time you run this → same output.

Important in:

* Research
* ML experiments
* Interview coding

---

# 🔹 11.8 Uniform Distribution

```python
np.random.uniform(low=5, high=10, size=5)
```

Range:

```
5 ≤ value < 10
```

---

# 🔹 11.9 Generating Random Samples from Normal Distribution (Custom Mean & Std)

```python
np.random.normal(loc=5, scale=2, size=5)
```

Where:

* loc = mean
* scale = std

---

# 🔹 11.10 Modern Approach (Recommended)

Instead of:

```python
np.random.seed(42)
```

Use:

```python
rng = np.random.default_rng(42)
rng.random((2,2))
```

Better and more robust.

---

# 🔹 11.11 Practical ML Example

Initialize neural network weights:

```python
weights = np.random.randn(3,4) * 0.01
```

Shuffle dataset:

```python
np.random.shuffle(data)
```

Split train/test randomly:

```python
indices = np.random.permutation(len(data))
```

---

# 🧠 Internal Understanding

NumPy random uses:

* Pseudo-random number generators (PRNG)
* Mathematical algorithms
* Deterministic with seed

It is NOT truly random.

---

# 🔥 Common Interview Questions

1. Difference between rand and randn?
2. What is seed?
3. Why reproducibility matters?
4. How to generate normal distribution with mean 10?
5. What is uniform distribution?

---

# 📌 Summary

You now understand:

✔ rand
✔ randint
✔ randn
✔ choice
✔ shuffle
✔ seed
✔ uniform
✔ normal
✔ default_rng

---