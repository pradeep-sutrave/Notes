
# 🟢 MODULE 9: Page Layout & Document Design (Detailed)

We will cover:

1. Margins
2. Page Size
3. Headers & Footers
4. Page Numbering Styles
5. Line Spacing
6. Custom Title Pages
7. Professional Report Layout

All with **Code → Output → Explanation**.

---

# 🔹 9.1 Changing Margins

By default LaTeX sets margins automatically.

To customize:

---

## ✅ Code

```latex
\usepackage[a4paper, margin=1in]{geometry}
```

---

## 🖨 Output

Margins become exactly **1 inch on all sides**.

---

## 🔎 What Is Happening?

* `geometry` package controls page layout
* `a4paper` sets paper size
* `margin=1in` sets uniform margins

---

## Custom Example

```latex
\usepackage[a4paper, left=1.5in, right=1in, top=1in, bottom=1in]{geometry}
```

Useful for thesis formatting.

---

# 🔹 9.2 Page Numbering Styles

---

## ✅ Code

```latex
\pagenumbering{roman}
```

---

## 🖨 Output

Page numbers appear as:

```
i, ii, iii, iv
```

---

Other options:

```latex
\pagenumbering{arabic}   % 1, 2, 3
\pagenumbering{alph}     % a, b, c
\pagenumbering{Roman}    % I, II, III
```

---

## Example (Thesis Style)

```latex
\pagenumbering{roman}
\tableofcontents
\newpage
\pagenumbering{arabic}
```

Front matter → roman
Main content → arabic

---

# 🔹 9.3 Headers & Footers (Very Important)

Use package:

```latex
\usepackage{fancyhdr}
```

---

## ✅ Basic Header Example

```latex
\documentclass{article}
\usepackage{fancyhdr}
\pagestyle{fancy}

\fancyhead[L]{Operating Systems}
\fancyhead[R]{Bhupathi Tejavath}
\fancyfoot[C]{\thepage}

\begin{document}

Hello World

\end{document}
```

---

## 🖨 Output

Header:

```
Operating Systems        Bhupathi Tejavath
```

Footer (center):

```
1
```

---

## 🔎 What Is Happening?

* `\pagestyle{fancy}` activates fancy layout
* `\fancyhead[L]` → left header
* `\fancyhead[R]` → right header
* `\fancyfoot[C]` → center footer
* `\thepage` prints page number

---

# 🔹 9.4 Removing Header Line

```latex
\renewcommand{\headrulewidth}{0pt}
```

Removes horizontal line in header.

---

# 🔹 9.5 Line Spacing

Use:

```latex
\usepackage{setspace}
```

---

## Double Spacing Example

```latex
\doublespacing
```

---

## 1.5 Spacing

```latex
\onehalfspacing
```

---

## Custom Spacing

```latex
\setstretch{1.3}
```

---

# 🔹 9.6 Custom Title Page (Professional)

---

## ✅ Code

```latex
\begin{titlepage}
\centering
{\Huge PROJECT REPORT \par}
\vspace{1cm}
{\Large Submitted By \par}
\vspace{0.5cm}
{\Large Bhupathi Tejavath \par}
\vfill
{\large Department of Computer Science \par}
{\large 2026}
\end{titlepage}
```

---

## 🖨 Output

Large centered professional title page with spacing.

---

# 🔹 9.7 Page Breaks

---

## Manual Page Break

```latex
\newpage
```

---

## Force All Floating Objects to Print

```latex
\clearpage
```

---

# 🔹 9.8 Complete Professional Report Example

---

## ✅ Code

```latex
\documentclass{report}
\usepackage[a4paper, margin=1in]{geometry}
\usepackage{fancyhdr}
\usepackage{setspace}

\pagestyle{fancy}
\fancyhead[L]{Data Structures Project}
\fancyhead[R]{Bhupathi Tejavath}
\fancyfoot[C]{\thepage}

\begin{document}

\begin{titlepage}
\centering
{\Huge Data Structures Project \par}
\vspace{1cm}
{\Large Submitted by Bhupathi Tejavath \par}
\vfill
{\large 2026}
\end{titlepage}

\pagenumbering{roman}
\tableofcontents
\newpage

\pagenumbering{arabic}

\chapter{Introduction}
This project explains data structures.

\chapter{Implementation}
Details of implementation.

\end{document}
```

---

## 🖨 Output Structure

* Custom title page
* Roman numbering for TOC
* Arabic numbering for chapters
* Header with project name
* Page numbers centered
* Clean margins

---

# 🔹 9.9 Common Beginner Mistakes

| Problem               | Solution                    |
| --------------------- | --------------------------- |
| Header not appearing  | Add `\pagestyle{fancy}`     |
| Margin not changing   | Load geometry package       |
| Page numbers missing  | Check `\pagenumbering`      |
| Title page has number | Add `\thispagestyle{empty}` |

---

# 🎯 After Module 9 You Can

✔ Control margins
✔ Design thesis layout
✔ Add custom headers & footers
✔ Change page numbering style
✔ Create professional title page
✔ Format reports properly
