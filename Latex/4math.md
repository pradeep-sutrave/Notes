# 🟢 MODULE 4: Mathematical Typesetting in LaTeX (Complete Detailed Guide)

LaTeX is famous because of its **perfect mathematical formatting**.

---

# 4.1 Math Modes

There are two main types:

## 1️⃣ Inline Math (Inside Paragraph)

```latex
$a^2 + b^2 = c^2$
```

Example:

```latex
The equation $a^2 + b^2 = c^2$ is called Pythagoras theorem.
```

---

## 2️⃣ Display Math (Centered Equation)

```latex
\[
a^2 + b^2 = c^2
\]
```

or

```latex
\begin{equation}
a^2 + b^2 = c^2
\end{equation}
```

Difference:

* `\[ \]` → no numbering
* `equation` → auto-numbered

---

# 4.2 Superscripts & Subscripts

```latex
x^2
a_n
x^{10}
a_{n+1}
```

Example:

```latex
\[
x^{10} + a_{n+1}
\]
```

---

# 4.3 Fractions

```latex
\frac{a}{b}
```

Example:

```latex
\[
\frac{1}{2} + \frac{3}{4}
\]
```

---

# 4.4 Square Roots

```latex
\sqrt{x}
\sqrt[3]{x}
```

Example:

```latex
\[
\sqrt{x^2 + y^2}
\]
```

---

# 4.5 Greek Letters

Lowercase:

```latex
\alpha
\beta
\gamma
\theta
\lambda
\pi
```

Uppercase:

```latex
\Gamma
\Delta
\Sigma
```

Example:

```latex
\[
\alpha + \beta = \gamma
\]
```

---

# 4.6 Integrals

```latex
\int_0^1 x^2 dx
```

Example:

```latex
\[
\int_0^1 x^2 dx
\]
```

---

# 4.7 Summation

```latex
\sum_{i=1}^{n} i
```

Example:

```latex
\[
\sum_{i=1}^{n} i^2
\]
```

---

# 4.8 Limits

```latex
\lim_{x \to 0}
```

Example:

```latex
\[
\lim_{x \to 0} \frac{\sin x}{x}
\]
```

---

# 4.9 Matrices

You need:

```latex
\usepackage{amsmath}
```

### Basic Matrix

```latex
\[
\begin{matrix}
1 & 2 \\
3 & 4
\end{matrix}
\]
```

---

### Matrix with Brackets

```latex
\[
\begin{bmatrix}
1 & 2 \\
3 & 4
\end{bmatrix}
\]
```

Other types:

* `pmatrix` → ()
* `Bmatrix` → {}
* `vmatrix` → | |

---

# 4.10 Cases (Piecewise Functions)

```latex
\[
f(x) =
\begin{cases}
x^2 & x > 0 \\
0 & x = 0 \\
-x & x < 0
\end{cases}
\]
```

Very important for math subjects.

---

# 4.11 Aligning Multiple Equations

Use `align` (from amsmath package).

```latex
\usepackage{amsmath}
```

Example:

```latex
\begin{align}
a + b &= c \\
x + y &= z
\end{align}
```

`&` is alignment point.

---

# 4.12 Complete Professional Math Example

```latex
\documentclass{article}
\usepackage{amsmath}

\begin{document}

\section{Mathematical Model}

The function is defined as:

\[
f(x) =
\begin{cases}
x^2 & x > 0 \\
0 & x = 0
\end{cases}
\]

We compute the integral:

\[
\int_0^1 x^2 dx
\]

The matrix representation:

\[
\begin{bmatrix}
1 & 2 \\
3 & 4
\end{bmatrix}
\]

\end{document}
```

---

# 4.13 Important Math Symbols Cheat Sheet

| Symbol | Code     |
| ------ | -------- |
| ±      | `\pm`    |
| ×      | `\times` |
| ÷      | `\div`   |
| ≤      | `\leq`   |
| ≥      | `\geq`   |
| ≠      | `\neq`   |
| ∞      | `\infty` |

---

# 4.14 Common Beginner Mistakes

| Mistake                | Fix                        |
| ---------------------- | -------------------------- |
| Missing `$`            | Always close math mode     |
| Using `^` without `{}` | Use braces                 |
| Forgetting amsmath     | Add `\usepackage{amsmath}` |
| Using `_` outside math | Use inside `$ $`           |

---

# 🎯 Module 4 Learning Outcome

After this module, you can:

✔ Write professional equations
✔ Use integrals, limits, summations
✔ Create matrices
✔ Align equations
✔ Write piecewise functions
✔ Use advanced math symbols

---