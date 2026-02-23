
# 🟢 MODULE 13: Creating Your Own LaTeX Templates (Professional Level)

In this module you will learn:

1. How to build reusable report templates
2. How to create your own resume template
3. How to design an IEEE-style paper layout
4. How to structure a thesis template
5. How document classes work internally

All in:

👉 **Code → Output → Explanation**

---

# 🔹 13.1 Why Create Templates?

Instead of rewriting formatting every time:

* Build once
* Reuse forever
* Maintain consistency
* Save hours of time

Very useful for:

* College projects
* Internship reports
* Research papers
* Resume

---

# 🔹 13.2 Creating a Basic Report Template

Let’s design a reusable project template.

---

## ✅ Code (project_template.tex)

```latex
\documentclass[12pt]{report}

\usepackage[a4paper, margin=1in]{geometry}
\usepackage{fancyhdr}
\usepackage{setspace}
\usepackage{graphicx}
\usepackage{amsmath}
\usepackage{hyperref}

\pagestyle{fancy}
\fancyhead[L]{Project Title}
\fancyhead[R]{Your Name}
\fancyfoot[C]{\thepage}

\onehalfspacing

\begin{document}

\begin{titlepage}
\centering
{\Huge PROJECT TITLE \par}
\vspace{1cm}
{\Large Submitted By \par}
{\Large Your Name \par}
\vfill
{\large Department of CSE \par}
{\large 2026}
\end{titlepage}

\pagenumbering{roman}
\tableofcontents
\newpage

\pagenumbering{arabic}

\chapter{Introduction}
Write introduction here.

\chapter{Implementation}
Write implementation here.

\chapter{Conclusion}
Write conclusion here.

\end{document}
```

---

## 🖨 Output Structure

* Professional title page
* Table of contents
* Roman numbering for front pages
* Arabic numbering for chapters
* Header with project name
* Clean margins

---

## 🔎 Why This Is Powerful?

You can now:

* Change title once
* Reuse this file for every project
* Just replace content

---

# 🔹 13.3 Creating a Resume Template

---

## ✅ Code (Basic Resume Template)

```latex
\documentclass[11pt]{article}
\usepackage[a4paper, margin=1in]{geometry}

\begin{document}

\begin{center}
{\Huge Bhupathi Tejavath} \\
CSE Student \\
Email: yourmail@email.com
\end{center}

\section*{Education}
B.Tech in Computer Science

\section*{Skills}
\begin{itemize}
\item C++
\item Python
\item Data Structures
\end{itemize}

\section*{Projects}
\textbf{Online Learning Platform} \\
Developed using HTML, CSS, JS.

\end{document}
```

---

## 🖨 Output

Clean one-page resume:

* Large name on top
* Sections bold
* Structured content

---

## 🔎 How To Improve?

You can later use advanced classes like:

* moderncv
* awesome-cv

But building manually helps you understand formatting deeply.

---

# 🔹 13.4 IEEE Research Paper Template (Basic Structure)

IEEE papers use:

```latex
\documentclass[conference]{IEEEtran}
```

---

## ✅ Code

```latex
\documentclass[conference]{IEEEtran}
\usepackage{graphicx}

\begin{document}

\title{Deep Learning in Healthcare}

\author{
\IEEEauthorblockN{Bhupathi Tejavath}
\IEEEauthorblockA{Department of CSE}
}

\maketitle

\begin{abstract}
This paper discusses deep learning applications.
\end{abstract}

\section{Introduction}
Deep learning is transforming healthcare.

\section{Methodology}
We applied neural networks.

\section{Conclusion}
Results show improvement.

\bibliographystyle{IEEEtran}
\bibliography{references}

\end{document}
```

---

## 🖨 Output

* Two-column layout
* IEEE formatting
* Proper abstract block
* Professional header

---

# 🔹 13.5 Thesis Template Structure

Large thesis projects should use:

```latex
\documentclass[12pt]{report}
```

Structure:

```
main.tex
│
├── chapters/
│   ├── intro.tex
│   ├── literature.tex
│   ├── methodology.tex
│   ├── results.tex
│   └── conclusion.tex
│
├── images/
├── references.bib
└── commands.tex
```

---

## Main File Example

```latex
\include{chapters/intro}
\include{chapters/literature}
\include{chapters/methodology}
```

---

## 🖨 Output

Fully structured thesis with:

* Separate chapters
* Automatic numbering
* Bibliography
* Figures & tables indexed

---

# 🔹 13.6 Understanding Document Classes Internally

When you write:

```latex
\documentclass{article}
```

LaTeX loads:

* Default margins
* Default fonts
* Section numbering rules
* Page layout

You can even create your own `.cls` file (advanced level).

---

# 🔹 13.7 How to Create Your Own Class (Concept Only)

Create file:

```text
myclass.cls
```

Define layout rules inside.

Then use:

```latex
\documentclass{myclass}
```

This is advanced and used by universities for thesis templates.

---

# 🔹 13.8 Best Practice for Professional Work

Always include:

```latex
\usepackage{hyperref}
\usepackage{amsmath}
\usepackage{graphicx}
\usepackage{geometry}
```

Keep project structured.

Use labels everywhere.

---

# 🎯 After Module 13 You Can

✔ Create reusable project templates
✔ Design your own resume template
✔ Write IEEE conference papers
✔ Structure thesis properly
✔ Manage large LaTeX projects
✔ Understand document classes

---

# 🏆 Congratulations

You have now completed:

✔ Basics
✔ Formatting
✔ Math
✔ Tables
✔ Images
✔ Cross Referencing
✔ Bibliography
✔ Page Layout
✔ Beamer
✔ TikZ
✔ Advanced Macros
✔ Template Creation

You now know **LaTeX from beginner to advanced professional level** 🔥
