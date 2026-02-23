
# 🟢 MODULE 12: Advanced LaTeX (Custom Commands, Macros & Environments)

This module will teach you:

1. Creating your own commands
2. Redefining existing commands
3. Creating custom environments
4. Multi-file projects
5. Creating your own document structure
6. Professional thesis structure

Everything in:

👉 **Code → Output → Explanation**

---

# 🔹 12.1 Creating Custom Commands (`\newcommand`)

If you repeatedly type something like:

```latex
\mathbb{R}
```

You can create shortcut.

---

## ✅ Code

```latex
\documentclass{article}
\usepackage{amsmath, amssymb}

\newcommand{\R}{\mathbb{R}}

\begin{document}

Let $x \in \R$.

\end{document}
```

---

## 🖨 Output

```text
Let x ∈ ℝ.
```

---

## 🔎 What Is Happening?

* `\newcommand{\R}{\mathbb{R}}`
* Now `\R` behaves like built-in command
* Saves time and keeps consistency

---

# 🔹 12.2 Command with Arguments

You can create command with parameters.

---

## ✅ Code

```latex
\newcommand{\sq}[1]{#1^2}

$sq{5}$
```

---

Correction (proper usage inside math):

```latex
\newcommand{\sq}[1]{#1^2}

\[
\sq{5}
\]
```

---

## 🖨 Output

```text
5²
```

---

## 🔎 Explanation

* `#1` → first argument
* `\sq{5}` → replaces `#1` with 5

---

# 🔹 12.3 Multiple Arguments

---

## ✅ Code

```latex
\newcommand{\add}[2]{#1 + #2}

\[
\add{3}{4}
\]
```

---

## 🖨 Output

```text
3 + 4
```

---

# 🔹 12.4 Redefining Existing Commands

Use:

```latex
\renewcommand
```

Example:

```latex
\renewcommand{\thesection}{\Roman{section}}
```

---

## 🖨 Output

Sections become:

```text
I
II
III
```

Instead of:

```text
1
2
3
```

---

# 🔹 12.5 Creating Custom Environment

Suppose you want special "Definition" environment.

---

## ✅ Code

```latex
\newenvironment{mydef}
{\begin{center}\begin{tabular}{|p{10cm}|}\hline}
{\\\hline\end{tabular}\end{center}}

\begin{mydef}
An Operating System manages hardware.
\end{mydef}
```

---

## 🖨 Output

Text inside a bordered box.

---

## 🔎 Explanation

* First part → how environment begins
* Second part → how it ends
* Useful for custom formatting

---

# 🔹 12.6 Multi-File Projects (Very Important 🔥)

Large projects should not be single file.

---

## Main File (main.tex)

```latex
\documentclass{report}

\begin{document}

\include{chapter1}
\include{chapter2}

\end{document}
```

---

## chapter1.tex

```latex
\chapter{Introduction}
This is introduction.
```

---

## chapter2.tex

```latex
\chapter{Implementation}
This is implementation.
```

---

## 🖨 Output

Combined report with chapters.

---

## 🔎 What Is Happening?

* `\include{}` inserts separate file
* Keeps project organized
* Essential for thesis

---

# 🔹 12.7 Custom Numbering Style

Example: Number equations by section.

---

## ✅ Code

```latex
\numberwithin{equation}{section}
```

---

## 🖨 Output

Equation numbering becomes:

```text
1.1
1.2
2.1
```

Instead of:

```text
1
2
3
```

---

# 🔹 12.8 Creating Your Own Command File

Create file: `commands.tex`

```latex
\newcommand{\R}{\mathbb{R}}
\newcommand{\N}{\mathbb{N}}
```

Then in main file:

```latex
\input{commands}
```

Very useful for large research projects.

---

# 🔹 12.9 Custom Document Structure (Professional Thesis Example)

---

## ✅ Code

```latex
\documentclass{report}
\usepackage[a4paper, margin=1in]{geometry}

\begin{document}

\begin{titlepage}
\centering
{\Huge Thesis Title}
\vfill
{\Large Author Name}
\end{titlepage}

\pagenumbering{roman}
\tableofcontents
\newpage

\pagenumbering{arabic}

\chapter{Introduction}
Text here.

\chapter{Literature Review}
Text here.

\chapter{Conclusion}
Text here.

\end{document}
```

---

## 🖨 Output Structure

* Title page
* Roman page numbers for TOC
* Arabic numbers for chapters
* Professional report format

---

# 🔹 12.10 When to Use Advanced Features?

Use custom commands when:

* Writing math-heavy documents
* Repeating symbols
* Writing thesis
* Writing research papers

Use multi-file structure when:

* Project > 10 pages
* Thesis
* Book writing

---

# 🔹 12.11 Common Mistakes

| Problem             | Fix                                         |
| ------------------- | ------------------------------------------- |
| Command not working | Place before `\begin{document}`             |
| Infinite loop error | Don't redefine built-in commands carelessly |
| Missing file        | Check filename spelling                     |
| Command inside math | Define correctly                            |

---

# 🎯 After Module 12 You Can

✔ Create custom commands
✔ Create shortcuts
✔ Redefine numbering
✔ Build thesis structure
✔ Organize large projects
✔ Write research-level LaTeX

---