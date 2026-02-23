
# 🟢 MODULE 7: Cross Referencing (Detailed + Code + Output + Explanation)

Cross referencing allows you to automatically reference:

* Sections
* Subsections
* Figures
* Tables
* Equations
* Pages

If numbering changes → everything updates automatically ✅

---

# 🔹 7.1 Referencing Sections

---

## ✅ Code

```latex
\documentclass{article}

\begin{document}

\section{Introduction}
\label{sec:intro}

This is the introduction section.

As discussed in Section~\ref{sec:intro}, this document explains referencing.

\end{document}
```

---

## 🖨 Output

```
1 Introduction

This is the introduction section.

As discussed in Section 1, this document explains referencing.
```

---

## 🔎 What Is Happening?

* `\label{sec:intro}` stores section number (1)
* `\ref{sec:intro}` retrieves that number
* If section number changes → reference auto updates

---

# 🔹 7.2 Referencing Subsections

---

## ✅ Code

```latex
\section{Methods}

\subsection{Algorithm}
\label{sub:algo}

Details of the algorithm.

Refer to Subsection~\ref{sub:algo}.
```

---

## 🖨 Output

```
1 Methods
1.1 Algorithm

Refer to Subsection 1.1.
```

---

# 🔹 7.3 Referencing Figures

---

## ✅ Code

```latex
\documentclass{article}
\usepackage{graphicx}

\begin{document}

\begin{figure}[h]
\centering
\includegraphics[width=0.4\textwidth]{sample.png}
\caption{Architecture Diagram}
\label{fig:arch}
\end{figure}

As shown in Figure~\ref{fig:arch}, the modules interact.

\end{document}
```

---

## 🖨 Output

```
Figure 1: Architecture Diagram

As shown in Figure 1, the modules interact.
```

---

## 🔎 Important Rule

Always place `\label` **after** `\caption`.

Correct:

```
\caption{}
\label{}
```

Wrong:

```
\label{}
\caption{}
```

---

# 🔹 7.4 Referencing Tables

---

## ✅ Code

```latex
\begin{table}[h]
\centering
\begin{tabular}{|c|c|}
\hline
Name & Score \\
\hline
John & 90 \\
\hline
\end{tabular}
\caption{Exam Results}
\label{tab:results}
\end{table}

Table~\ref{tab:results} shows the marks.
```

---

## 🖨 Output

```
Table 1: Exam Results

Table 1 shows the marks.
```

---

# 🔹 7.5 Referencing Equations

---

## ✅ Code

```latex
\documentclass{article}
\usepackage{amsmath}

\begin{document}

\begin{equation}
a^2 + b^2 = c^2
\label{eq:pythagoras}
\end{equation}

From Equation~\ref{eq:pythagoras}, we derive the result.

\end{document}
```

---

## 🖨 Output

```
(1)  a² + b² = c²

From Equation (1), we derive the result.
```

---

## 🔎 What Is Happening?

* `equation` automatically numbers
* `\label` stores equation number
* `\ref` prints number inside parentheses

---

# 🔹 7.6 Referencing Page Numbers

---

## ✅ Code

```latex
\section{Conclusion}
\label{sec:conclusion}

See page~\pageref{sec:conclusion} for conclusion.
```

---

## 🖨 Output

```
See page 3 for conclusion.
```

---

# 🔹 7.7 Using hyperref (Clickable References)

Add package:

```latex
\usepackage{hyperref}
```

Now all references become clickable in PDF.

---

## ✅ Example

```latex
\usepackage{hyperref}

As shown in Section~\ref{sec:intro}.
```

---

## 🖨 Output

"Section 1" becomes clickable link in PDF.

---

# 🔹 7.8 Full Professional Example

---

## ✅ Code

```latex
\documentclass{article}
\usepackage{amsmath}
\usepackage{hyperref}

\begin{document}

\tableofcontents
\newpage

\section{Introduction}
\label{sec:intro}

This is introduction.

\section{Mathematics}
\label{sec:math}

\begin{equation}
E = mc^2
\label{eq:einstein}
\end{equation}

Refer to Equation~\ref{eq:einstein} in Section~\ref{sec:math}.

\section{Conclusion}
\label{sec:conclusion}

See page~\pageref{sec:conclusion}.

\end{document}
```

---

## 🖨 Output Structure

* TOC auto generated
* Equation numbered (1)
* References auto inserted
* Page numbers printed
* Clickable links

---

# 🔹 7.9 Why This Is Powerful

Imagine:

* You insert new section at top
* All section numbers change
* All references update automatically

No manual editing needed 🔥

---

# ⚠ Common Beginner Mistakes

| Mistake                | Fix                       |
| ---------------------- | ------------------------- |
| Reference shows ??     | Compile twice             |
| Wrong number           | Place label after caption |
| Using same label twice | Use unique labels         |
| Forgetting amsmath     | Add package               |

---

# 🎯 After Module 7 You Can

✔ Reference sections
✔ Reference figures
✔ Reference tables
✔ Reference equations
✔ Reference pages
✔ Make clickable PDFs

---
