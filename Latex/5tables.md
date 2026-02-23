
# 🟢 MODULE 5: Tables in LaTeX (With Code + Output)

---

# 5.1 Basic Table

---

## ✅ Code (Content)

```latex
\documentclass{article}
\begin{document}

\begin{tabular}{|c|c|}
\hline
Name & Age \\
\hline
John & 20 \\
Alice & 22 \\
\hline
\end{tabular}

\end{document}
```

---

## 🖨 Output (What You See)

```
-----------------
| Name  |  Age  |
-----------------
| John  |  20   |
| Alice |  22   |
-----------------
```

(Properly aligned and formatted in PDF)

---

## 🔎 What Is Happening?

* `{|c|c|}` → 2 centered columns with vertical lines
* `&` → separates columns
* `\\` → moves to next row
* `\hline` → horizontal line

---

# 5.2 Left, Center, Right Alignment

---

## ✅ Code

```latex
\begin{tabular}{|l|c|r|}
\hline
Left & Center & Right \\
\hline
A & B & C \\
\hline
\end{tabular}
```

---

## 🖨 Output

```
--------------------------
| Left | Center | Right |
--------------------------
| A    |   B    |     C |
--------------------------
```

---

## 🔎 What Is Happening?

* `l` → left aligned
* `c` → centered
* `r` → right aligned

---

# 5.3 Adding Caption (Professional Way)

Now we use `table` environment.

---

## ✅ Code

```latex
\documentclass{article}
\begin{document}

\begin{table}[h]
\centering
\begin{tabular}{|c|c|}
\hline
Subject & Marks \\
\hline
Math & 90 \\
CS & 95 \\
\hline
\end{tabular}
\caption{Student Marks}
\end{table}

\end{document}
```

---

## 🖨 Output

Centered table

Below it:

```
Table 1: Student Marks
```

---

## 🔎 What Is Happening?

* `table` → floating object
* `[h]` → try placing here
* `\centering` → centers table
* `\caption{}` → auto numbering

---

# 5.4 Referencing Table

---

## ✅ Code

```latex
\label{tab:marks}
```

And in text:

```latex
As shown in Table~\ref{tab:marks}, the results are good.
```

---

## 🖨 Output

```
As shown in Table 1, the results are good.
```

---

## 🔎 What Is Happening?

* `\label{}` stores table number
* `\ref{}` retrieves it

Automatic numbering = professional formatting ✅

---

# 5.5 Multi-Column (Merge Columns)

---

## ✅ Code

```latex
\begin{tabular}{|c|c|c|}
\hline
\multicolumn{3}{|c|}{Student Data} \\
\hline
Name & Age & Grade \\
\hline
John & 20 & A \\
\hline
\end{tabular}
```

---

## 🖨 Output

```
--------------------------------
|       Student Data           |
--------------------------------
| Name | Age | Grade           |
--------------------------------
| John | 20  | A               |
--------------------------------
```

---

## 🔎 What Is Happening?

`\multicolumn{3}{|c|}{Student Data}`

* 3 → spans 3 columns
* `|c|` → centered with vertical lines
* Text inside becomes merged header

---

# 5.6 Multi-Row (Merge Rows)

Need package:

```latex
\usepackage{multirow}
```

---

## ✅ Code

```latex
\usepackage{multirow}

\begin{tabular}{|c|c|}
\hline
\multirow{2}{*}{John} & Math \\
\cline{2-2}
 & CS \\
\hline
\end{tabular}
```

---

## 🖨 Output

```
-----------------
| John | Math   |
|      | CS     |
-----------------
```

---

## 🔎 What Is Happening?

`\multirow{2}{*}{John}`

* 2 → spans 2 rows
* `*` → automatic width

`\cline{2-2}` → draws line only for column 2

---

# 5.7 Professional Research Table (booktabs)

Add:

```latex
\usepackage{booktabs}
```

---

## ✅ Code

```latex
\begin{tabular}{ccc}
\toprule
Algorithm & Time (ms) & Accuracy \\
\midrule
Dijkstra & 25 & 98\% \\
A* & 18 & 97\% \\
\bottomrule
\end{tabular}
```

---

## 🖨 Output

Clean, professional style:

```
Algorithm   Time(ms)   Accuracy
--------------------------------
Dijkstra      25         98%
A*            18         97%
--------------------------------
```

(No vertical lines — academic style)

---

## 🔎 What Is Happening?

* `\toprule` → top thick line
* `\midrule` → middle line
* `\bottomrule` → bottom line

Used in research papers ✅

---

# 5.8 Controlling Column Width

---

## ✅ Code

```latex
\begin{tabular}{|p{3cm}|p{5cm}|}
\hline
Name & Description \\
\hline
CPU & Central Processing Unit responsible for computation \\
\hline
\end{tabular}
```

---

## 🖨 Output

Column width fixed:

Left column → 3cm
Right column → 5cm

Text wraps automatically.

---

## 🔎 What Is Happening?

`p{3cm}` → fixed width column

Useful for:

* Long text
* Project reports

---

# 🎯 After Module 5 You Understand

✔ How tables are structured
✔ What `&` and `\\` do
✔ How merging works
✔ How captions work
✔ How referencing works
✔ Research-style formatting

--