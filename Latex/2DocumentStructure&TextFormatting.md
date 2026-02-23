
# 🟢 MODULE 2: Document Structure & Text Formatting (Detailed)

This module makes your document look **professional and structured** — very important for project reports and assignments.

---

# 2.1 Document Classes (Deep Understanding)

The document class defines overall layout.

```latex
\documentclass{article}
```

## Common Classes

| Class     | Used For                   |
| --------- | -------------------------- |
| `article` | Assignments, small reports |
| `report`  | Project reports            |
| `book`    | Books, thesis              |
| `beamer`  | Presentations              |

### Example – Report Class

```latex
\documentclass{report}

\begin{document}

\chapter{Introduction}
This is a chapter.

\end{document}
```

👉 Note: `\chapter` works only in `report` and `book`, not in `article`.

---

# 2.2 Title Page (Advanced Usage)

Basic:

```latex
\title{Data Structures Project}
\author{Bhupathi Tejavath}
\date{\today}
```

Print it using:

```latex
\maketitle
```

---

### Custom Title Page Example

```latex
\begin{titlepage}
\centering
{\Huge Data Structures Project \par}
\vspace{1cm}
{\Large Submitted by Bhupathi Tejavath \par}
\vfill
{\large \today}
\end{titlepage}
```

This gives full control over formatting.

---

# 2.3 Sectioning Commands

LaTeX automatically numbers sections.

```latex
\section{Introduction}
\subsection{Background}
\subsubsection{History}
```

---

## Numbering Style Example

Output becomes:

```
1 Introduction
1.1 Background
1.1.1 History
```

---

## Unnumbered Sections

```latex
\section*{Acknowledgement}
```

`*` removes numbering.

---

# 2.4 Table of Contents

```latex
\tableofcontents
```

Full Example:

```latex
\documentclass{article}

\begin{document}

\tableofcontents

\section{Introduction}
Text here.

\section{Conclusion}
Text here.

\end{document}
```

⚠ Compile twice to update TOC.

---

# 2.5 Text Formatting

---

## Bold, Italic, Underline

```latex
\textbf{Bold Text}
\textit{Italic Text}
\underline{Underline Text}
```

---

## Font Sizes

```latex
{\tiny Small}
{\small Small}
{\large Large}
{\Large Larger}
{\huge Huge}
```

---

## Text Alignment

### Center

```latex
\begin{center}
Centered Text
\end{center}
```

### Right Align

```latex
\begin{flushright}
Right Text
\end{flushright}
```

### Left Align

```latex
\begin{flushleft}
Left Text
\end{flushleft}
```

---

# 2.6 Line Breaks & Paragraphs

### New Paragraph

Leave one empty line in code.

### Line Break

```latex
This is line one. \\
This is line two.
```

### Page Break

```latex
\newpage
```

---

# 2.7 Spacing

### Vertical Space

```latex
\vspace{1cm}
```

### Horizontal Space

```latex
\hspace{1cm}
```

---

# 2.8 Complete Example (Professional Structure)

```latex
\documentclass{article}

\title{Operating Systems Assignment}
\author{Bhupathi Tejavath}
\date{\today}

\begin{document}

\maketitle
\tableofcontents
\newpage

\section{Introduction}

Operating Systems manage hardware and software resources.

\section{Features}

\subsection{Process Management}
The OS handles processes efficiently.

\subsection{Memory Management}
Memory allocation is done dynamically.

\section*{Conclusion}

This assignment explains OS basics.

\end{document}
```

---

# 2.9 Common Beginner Mistakes

| Mistake                     | Fix              |
| --------------------------- | ---------------- |
| Using `\chapter` in article | Use report class |
| Forgetting `\maketitle`     | Add it           |
| TOC not updating            | Compile twice    |
| Misplaced braces `{}`       | Check matching   |

---

# 🎯 Module 2 Learning Outcome

After this module you can:

✔ Create structured academic documents
✔ Add title page
✔ Create table of contents
✔ Use sections & subsections
✔ Format text professionally
✔ Control spacing and alignment

---