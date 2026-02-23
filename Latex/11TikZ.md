
# 🟢 MODULE 11: TikZ – Drawing Diagrams in LaTeX (Detailed)

TikZ allows you to draw:

* Flowcharts
* Graphs
* Trees
* Network diagrams
* Geometry figures
* Automata diagrams

Everything directly inside LaTeX.

---

# 🔹 11.1 Required Package

---

## ✅ Code

```latex
\usepackage{tikz}
```

If using advanced positioning:

```latex
\usetikzlibrary{positioning}
```

---

## 🖨 Output

Nothing visible — it just enables drawing.

---

# 🔹 11.2 Drawing a Simple Line

---

## ✅ Code

```latex
\documentclass{article}
\usepackage{tikz}

\begin{document}

\begin{tikzpicture}
\draw (0,0) -- (3,0);
\end{tikzpicture}

\end{document}
```

---

## 🖨 Output

A straight horizontal line from (0,0) to (3,0).

---

## 🔎 What Is Happening?

* `(0,0)` → starting coordinate
* `(3,0)` → ending coordinate
* `--` → draws straight line

---

# 🔹 11.3 Drawing Shapes

---

## ✅ Code

```latex
\begin{tikzpicture}
\draw (0,0) rectangle (3,2);
\draw (4,1) circle (1);
\end{tikzpicture}
```

---

## 🖨 Output

* Rectangle from (0,0) to (3,2)
* Circle centered at (4,1) with radius 1

---

# 🔎 Explanation

* `rectangle` → draws rectangle
* `circle (1)` → radius = 1

---

# 🔹 11.4 Adding Text Inside Shapes

---

## ✅ Code

```latex
\begin{tikzpicture}
\draw (0,0) rectangle (4,2);
\node at (2,1) {Process};
\end{tikzpicture}
```

---

## 🖨 Output

Rectangle with word:

```text
Process
```

centered inside it.

---

## 🔎 What Is Happening?

* `\node` places text
* `(2,1)` is center of rectangle

---

# 🔹 11.5 Creating a Flowchart (Important 🔥)

---

## ✅ Code

```latex
\documentclass{article}
\usepackage{tikz}
\usetikzlibrary{positioning}

\begin{document}

\begin{tikzpicture}[node distance=2cm]

\node (start) [draw, rectangle] {Start};
\node (process) [draw, rectangle, below of=start] {Process};
\node (end) [draw, rectangle, below of=process] {End};

\draw[->] (start) -- (process);
\draw[->] (process) -- (end);

\end{tikzpicture}

\end{document}
```

---

## 🖨 Output

Flowchart:

```
Start
  ↓
Process
  ↓
End
```

---

## 🔎 Explanation

* `node distance=2cm` → vertical spacing
* `below of=start` → position relative to start
* `->` → arrow

---

# 🔹 11.6 Decision Box (Diamond)

---

## ✅ Code

```latex
\node (decision) [draw, diamond, aspect=2] {Condition};
```

---

## 🖨 Output

Diamond shape with text “Condition”.

---

# 🔹 11.7 Drawing Graph (Like Data Structures)

---

## ✅ Code

```latex
\begin{tikzpicture}
\node (A) at (0,0) [circle, draw] {A};
\node (B) at (2,1) [circle, draw] {B};
\node (C) at (2,-1) [circle, draw] {C};

\draw (A) -- (B);
\draw (A) -- (C);
\end{tikzpicture}
```

---

## 🖨 Output

Graph:

```
     B
    /
A
    \
     C
```

---

## 🔎 What Is Happening?

* Nodes positioned manually using coordinates
* Circles drawn
* Edges created using `--`

---

# 🔹 11.8 Drawing Tree Structure

---

## ✅ Code

```latex
\begin{tikzpicture}
\node {Root}
  child {node {Left}}
  child {node {Right}};
\end{tikzpicture}
```

---

## 🖨 Output

```
     Root
     /   \
  Left   Right
```

---

# 🔹 11.9 Styling Nodes (Colors & Shapes)

---

## ✅ Code

```latex
\begin{tikzpicture}
\node [circle, draw, fill=blue!20] at (0,0) {Node};
\end{tikzpicture}
```

---

## 🖨 Output

Light blue circular node labeled “Node”.

---

## 🔎 What Is Happening?

* `fill=blue!20` → 20% blue shade
* `circle` → circular shape

---

# 🔹 11.10 Complete Professional Example (Flowchart)

---

## ✅ Code

```latex
\documentclass{article}
\usepackage{tikz}
\usetikzlibrary{positioning, shapes.geometric}

\begin{document}

\begin{tikzpicture}[node distance=2cm]

\node (start) [draw, rectangle] {Start};
\node (input) [draw, rectangle, below of=start] {Input Data};
\node (decision) [draw, diamond, below of=input, aspect=2] {Valid?};
\node (end) [draw, rectangle, below of=decision] {End};

\draw[->] (start) -- (input);
\draw[->] (input) -- (decision);
\draw[->] (decision) -- node[right] {Yes} (end);

\end{tikzpicture}

\end{document}
```

---

## 🖨 Output

Professional flowchart with:

Start → Input → Decision → End

---

# 🔹 11.11 Common Beginner Mistakes

| Problem              | Fix                         |
| -------------------- | --------------------------- |
| Shapes not working   | Load correct tikz libraries |
| Nodes overlapping    | Adjust `node distance`      |
| Arrows not appearing | Use `->`                    |
| Text misplaced       | Adjust coordinates          |

---

# 🎯 After Module 11 You Can

✔ Draw flowcharts
✔ Draw graphs
✔ Draw trees
✔ Draw decision boxes
✔ Create research-level diagrams
✔ Create network diagrams
