# 🟢 MODULE 3: Lists in LaTeX (Complete Detailed Guide)

Lists are used in:

* Assignments
* Project reports
* Research papers
* Notes
* Documentation

---

# 3.1 Unordered List (itemize)

Used for bullet points.

```latex
\begin{itemize}
\item Apple
\item Banana
\item Mango
\end{itemize}
```

### Output:

• Apple
• Banana
• Mango

---

## Nested Unordered List

```latex
\begin{itemize}
\item Fruits
  \begin{itemize}
  \item Apple
  \item Banana
  \end{itemize}
\item Vegetables
\end{itemize}
```

---

# 3.2 Ordered List (enumerate)

Used for numbering.

```latex
\begin{enumerate}
\item First Step
\item Second Step
\item Third Step
\end{enumerate}
```

### Output:

1. First Step
2. Second Step
3. Third Step

---

## Nested Ordered List

```latex
\begin{enumerate}
\item Main Topic
  \begin{enumerate}
  \item Subtopic 1
  \item Subtopic 2
  \end{enumerate}
\item Next Topic
\end{enumerate}
```

Output:
1
1.1
1.2

---

# 3.3 Description List

Used when you want label + explanation.

```latex
\begin{description}
\item[CPU] Central Processing Unit
\item[RAM] Random Access Memory
\end{description}
```

Output:
CPU — Central Processing Unit
RAM — Random Access Memory

---

# 3.4 Custom Numbering Styles

By default:

1, 2, 3

But we can change it.

---

## Roman Numbers

```latex
\begin{enumerate}
\renewcommand{\labelenumi}{\roman{enumi}}
\item First
\item Second
\end{enumerate}
```

Output:
i. First
ii. Second

---

## Alphabet Style

```latex
\begin{enumerate}
\renewcommand{\labelenumi}{\alph{enumi}}
\item Option A
\item Option B
\end{enumerate}
```

Output:
a. Option A
b. Option B

---

# 3.5 Custom Bullets

We can change bullet symbol.

```latex
\usepackage{enumitem}
```

Then:

```latex
\begin{itemize}[label=--]
\item Item 1
\item Item 2
\end{itemize}
```

---

# 3.6 Controlling Spacing in Lists

Default lists sometimes have extra spacing.

Using enumitem:

```latex
\begin{itemize}[noitemsep]
\item Item 1
\item Item 2
\end{itemize}
```

---

# 3.7 Professional Example (Project Style)

```latex
\documentclass{article}
\usepackage{enumitem}

\begin{document}

\section{Algorithm Steps}

\begin{enumerate}
\item Initialize variables
\item Take input
\item Process data
  \begin{itemize}
  \item Validate input
  \item Compute result
  \end{itemize}
\item Display output
\end{enumerate}

\end{document}
```

---

# 3.8 Common Mistakes

| Mistake                 | Solution                   |
| ----------------------- | -------------------------- |
| Forgetting `\item`      | Add before each entry      |
| Missing `\end{itemize}` | Close environment properly |
| Incorrect nesting       | Check indentation          |

---

# 🎯 Module 3 Learning Outcome

After this module, you can:

✔ Create bullet lists
✔ Create numbered lists
✔ Create nested lists
✔ Create description lists
✔ Customize numbering style
✔ Control list spacing

---
