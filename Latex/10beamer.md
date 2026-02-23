

# 🟢 MODULE 10: Beamer – Creating Presentation Slides in LaTeX (Detailed)

LaTeX presentations are created using the **`beamer` document class**.

Used for:

* Seminar presentations
* Project defense
* Research conferences
* Technical talks

---

# 🔹 10.1 Basic Beamer Structure

---

## ✅ Code (Minimum Working Example)

```latex
\documentclass{beamer}

\begin{document}

\begin{frame}
Hello World
\end{frame}

\end{document}
```

---

## 🖨 Output

* A single slide
* White background
* “Hello World” in center

---

## 🔎 What Is Happening?

* `beamer` class creates slides instead of pages
* `frame` = one slide

---

# 🔹 10.2 Title Slide

---

## ✅ Code

```latex
\documentclass{beamer}

\title{Operating Systems}
\author{Bhupathi Tejavath}
\date{\today}

\begin{document}

\frame{\titlepage}

\end{document}
```

---

## 🖨 Output

Slide showing:

```
Operating Systems
Bhupathi Tejavath
Today's Date
```

Centered and professionally formatted.

---

## 🔎 What Is Happening?

* `\titlepage` automatically creates formatted title slide
* Beamer handles layout

---

# 🔹 10.3 Sections in Beamer

---

## ✅ Code

```latex
\section{Introduction}

\begin{frame}
\frametitle{Introduction}
Operating systems manage hardware.
\end{frame}
```

---

## 🖨 Output

Slide title:

```
Introduction
```

Content below it.

---

# 🔹 10.4 Bullet Points

---

## ✅ Code

```latex
\begin{frame}
\frametitle{Features}

\begin{itemize}
\item Process Management
\item Memory Management
\item File System
\end{itemize}

\end{frame}
```

---

## 🖨 Output

Slide with bullet list:

• Process Management
• Memory Management
• File System

---

# 🔹 10.5 Step-by-Step Reveal (Animation)

---

## ✅ Code

```latex
\begin{frame}
\frametitle{Advantages}

\begin{itemize}
\item<1-> Easy Formatting
\item<2-> Professional Output
\item<3-> Great for Research
\end{itemize}

\end{frame}
```

---

## 🖨 Output

Slide behavior:

1st click → shows first point
2nd click → shows second
3rd click → shows third

---

## 🔎 What Is Happening?

`<1->` means:

* Show from slide 1 onward
* Creates incremental animation

---

# 🔹 10.6 Blocks (Important for Presentations)

---

## ✅ Code

```latex
\begin{frame}
\frametitle{Definition}

\begin{block}{Operating System}
An OS manages hardware and software.
\end{block}

\end{frame}
```

---

## 🖨 Output

A colored box:

```
Operating System
An OS manages hardware and software.
```

---

## Other Block Types

```latex
\begin{alertblock}{Warning}
This is important!
\end{alertblock}

\begin{exampleblock}{Example}
This is an example.
\end{exampleblock}
```

---

# 🔹 10.7 Adding Images in Beamer

---

## ✅ Code

```latex
\usepackage{graphicx}

\begin{frame}
\frametitle{System Architecture}

\centering
\includegraphics[width=0.6\textwidth]{sample.png}

\end{frame}
```

---

## 🖨 Output

Slide with centered image scaled to 60% width.

---

# 🔹 10.8 Mathematical Equations in Beamer

---

## ✅ Code

```latex
\begin{frame}
\frametitle{Equation}

\[
E = mc^2
\]

\end{frame}
```

---

## 🖨 Output

Slide showing centered equation.

---

# 🔹 10.9 Themes (Very Important)

Beamer has built-in themes.

---

## ✅ Code

```latex
\documentclass{beamer}
\usetheme{Madrid}
```

---

## 🖨 Output

Slides with professional theme:

* Colored header
* Modern layout
* Navigation bar

---

Popular themes:

| Theme       |
| ----------- |
| Madrid      |
| Warsaw      |
| CambridgeUS |
| Berlin      |

---

# 🔹 10.10 Table of Contents Slide

---

## ✅ Code

```latex
\begin{frame}
\frametitle{Outline}
\tableofcontents
\end{frame}
```

---

## 🖨 Output

Slide showing all sections as agenda.

---

# 🔹 10.11 Complete Professional Presentation Example

---

## ✅ Code

```latex
\documentclass{beamer}
\usetheme{Madrid}
\usepackage{graphicx}

\title{Data Structures}
\author{Bhupathi Tejavath}
\date{\today}

\begin{document}

\frame{\titlepage}

\begin{frame}
\frametitle{Outline}
\tableofcontents
\end{frame}

\section{Introduction}

\begin{frame}
\frametitle{Introduction}
\begin{itemize}
\item Definition
\item Importance
\item Applications
\end{itemize}
\end{frame}

\section{Conclusion}

\begin{frame}
\frametitle{Conclusion}
\begin{block}{Summary}
Data structures organize data efficiently.
\end{block}
\end{frame}

\end{document}
```

---

## 🖨 Output Structure

* Title slide
* Outline slide
* Bullet slides
* Themed design
* Clean formatting

---

# 🔹 10.12 Common Beginner Mistakes

| Problem               | Fix                                         |
| --------------------- | ------------------------------------------- |
| Frame not showing     | Must use `frame` environment                |
| Image too large       | Use width option                            |
| Animation not working | Use `<1->` syntax                           |
| Theme not changing    | Add `\usetheme{}` before `\begin{document}` |

---

# 🎯 After Module 10 You Can

✔ Create presentation slides
✔ Add animations
✔ Add blocks
✔ Insert images
✔ Add equations
✔ Use themes
✔ Create full seminar presentation

---
