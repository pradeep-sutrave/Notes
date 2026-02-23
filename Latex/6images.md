

# 🟢 MODULE 6: Images & Figures in LaTeX (With Code + Output)

Images are used in:

* Project reports
* Research papers
* Diagrams
* Architecture designs
* Lab records

---

# 6.1 Required Package

---

## ✅ Code

```latex
\usepackage{graphicx}
```

---

## 🖨 Output

Nothing visible in PDF.

---

## 🔎 What Is Happening?

This package enables the command:

```
\includegraphics
```

Without this → images won’t work ❌

---

# 6.2 Basic Image Insertion

Assume your image file is: `sample.png`

---

## ✅ Code

```latex
\documentclass{article}
\usepackage{graphicx}

\begin{document}

\includegraphics{sample.png}

\end{document}
```

---

## 🖨 Output

Image appears:

📷 (Full size image, left aligned)

---

## 🔎 What Is Happening?

* LaTeX searches for `sample.png` in same folder
* Prints image at original resolution
* Default alignment = left

---

# 6.3 Resize Image (Very Important)

---

## ✅ Code

```latex
\includegraphics[width=0.5\textwidth]{sample.png}
```

---

## 🖨 Output

Image appears at **50% of page width**

---

## 🔎 What Is Happening?

`width=0.5\textwidth`

* `\textwidth` = full text area width
* `0.5` = half of that
* Aspect ratio maintained automatically

---

# 6.4 Scaling Instead of Width

---

## ✅ Code

```latex
\includegraphics[scale=0.6]{sample.png}
```

---

## 🖨 Output

Image appears at 60% of original size.

---

## 🔎 What Is Happening?

* `scale=0.6` reduces size proportionally
* Both height and width scale equally

---

# 6.5 Centering Image

---

## ✅ Code

```latex
\begin{center}
\includegraphics[width=0.5\textwidth]{sample.png}
\end{center}
```

---

## 🖨 Output

Image appears centered on page.

---

## 🔎 What Is Happening?

`center` environment aligns content horizontally.

---

# 6.6 Professional Way: Figure Environment

Always use this in projects.

---

## ✅ Code

```latex
\documentclass{article}
\usepackage{graphicx}

\begin{document}

\begin{figure}[h]
\centering
\includegraphics[width=0.6\textwidth]{sample.png}
\caption{System Architecture}
\label{fig:arch}
\end{figure}

\end{document}
```

---

## 🖨 Output

Centered image

Below image:

```
Figure 1: System Architecture
```

---

## 🔎 What Is Happening?

* `figure` → floating object
* `[h]` → try placing here
* `\caption{}` → auto numbering
* `\label{}` → stores figure number

---

# 6.7 Referencing Figure

---

## ✅ Code

```latex
As shown in Figure~\ref{fig:arch}, the modules are connected.
```

---

## 🖨 Output

```
As shown in Figure 1, the modules are connected.
```

---

## 🔎 What Is Happening?

* `\ref{fig:arch}` replaces with figure number
* If numbering changes → auto updates

Professional formatting ✅

---

# 6.8 Rotating Image

---

## ✅ Code

```latex
\includegraphics[angle=45,width=0.4\textwidth]{sample.png}
```

---

## 🖨 Output

Image rotated 45 degrees.

---

## 🔎 What Is Happening?

* `angle=45` rotates image clockwise

---

# 6.9 Forcing Placement

Sometimes image moves automatically.

Use:

```latex
\usepackage{float}
```

Then:

```latex
\begin{figure}[H]
```

`H` → exactly here (no floating)

---

# 6.10 Complete Professional Example

---

## ✅ Code

```latex
\documentclass{article}
\usepackage{graphicx}
\usepackage{float}

\begin{document}

\section{System Design}

The architecture is shown below.

\begin{figure}[H]
\centering
\includegraphics[width=0.6\textwidth]{sample.png}
\caption{System Design Diagram}
\label{fig:design}
\end{figure}

As seen in Figure~\ref{fig:design}, the system has three layers.

\end{document}
```

---

## 🖨 Output Structure

1. Section title
2. Paragraph
3. Centered image
4. Caption: "Figure 1: System Design Diagram"
5. Proper reference in text

---

# ⚠ Common Beginner Mistakes

| Problem           | Reason                  |
| ----------------- | ----------------------- |
| Image not showing | File not in same folder |
| Wrong file name   | Case sensitive          |
| Too big image     | Forgot width option     |
| No numbering      | Caption outside figure  |

---

# 🎯 After Module 6 You Can

✔ Insert images
✔ Resize properly
✔ Add captions
✔ Reference images
✔ Control placement
✔ Rotate & scale
