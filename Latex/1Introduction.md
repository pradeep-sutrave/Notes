# 🟢 MODULE 1: Introduction to LaTeX (Detailed)

---

# 1.1 What is LaTeX?

## 📌 Definition

**LaTeX** is a high-quality **document preparation system** used for:

* Research papers
* Project reports
* Theses
* Mathematical documents
* Technical books

It is built on top of **TeX**, created by Donald Knuth.

---

## 📌 Why Not MS Word?

| MS Word                  | LaTeX                |
| ------------------------ | -------------------- |
| WYSIWYG editor           | Code-based           |
| Manual formatting        | Automatic formatting |
| Weak for complex math    | Excellent for math   |
| Formatting breaks easily | Very stable          |

---

## 📌 How LaTeX Works

You write code → LaTeX compiles → Generates PDF

Example:

```latex
\documentclass{article}

\begin{document}

Hello, this is my first LaTeX document.

\end{document}
```

Output → Professionally formatted PDF.

---

# 1.2 Installation & Setup

---

## Option 1: Online (Recommended)

### 🌐 Use **Overleaf**

![Image](https://www.filepicker.io/api/file/JTF5Sp7zQUC4JbER127A)

![Image](https://docs.overleaf.com/~gitbook/image?dpr=3\&quality=100\&sign=15a49440\&sv=2\&url=https%3A%2F%2F3502988919-files.gitbook.io%2F~%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FVetOkhFZmAC8QCQK0Pi7%252Fuploads%252FPSS7pUr6d77Seao7bUyN%252FLayoutDefault-Light-NewEditor.png%3Falt%3Dmedia%26token%3De2aecfb9-2cd0-4eb2-ac1a-88c3a104a783\&width=768)

### Steps:

1. Create account
2. Click "New Project"
3. Start typing
4. PDF auto generates

✔ No installation
✔ Auto save
✔ Easy for beginners

---

## Option 2: Offline Installation

### Windows

Install → **MiKTeX**

### Linux / Mac

Install → **TeX Live**

Then install editor:

* TeXstudio
* VS Code (LaTeX Workshop extension)

---

# 1.3 First Complete Example (With Explanation)

Let’s write a proper structured document.

```latex
\documentclass{article}

\title{My First LaTeX Document}
\author{Your Name}
\date{\today}

\begin{document}

\maketitle

\section{Introduction}

This is my first document created using LaTeX.

\section{Mathematics Example}

Inline math: $a^2 + b^2 = c^2$

Display math:
\[
\int_0^1 x^2 dx
\]

\end{document}
```

---

## Explanation Line by Line

### 1️⃣ Document Class

```latex
\documentclass{article}
```

Defines type of document.

Other classes:

* report
* book
* beamer (for presentations)

---

### 2️⃣ Title Section

```latex
\title{}
\author{}
\date{}
```

`\maketitle` prints it.

---

### 3️⃣ Sections

```latex
\section{Introduction}
```

Automatically:

* Numbered
* Proper spacing
* Added to table of contents

---

### 4️⃣ Math Mode

Inline math:

```latex
$ a^2 + b^2 = c^2 $
```

Display math:

```latex
\[
a^2 + b^2 = c^2
\]
```

---

# 1.4 Basic Syntax Rules

## 🔹 Commands start with backslash

```
\section
\textbf
\frac
```

## 🔹 Curly braces `{}` hold arguments

```
\section{Introduction}
```

## 🔹 Percentage `%` is comment

```latex
% This is a comment
```

---

# 1.5 Common Errors Beginners Make

| Error                    | Reason                 |
| ------------------------ | ---------------------- |
| Missing `\end{document}` | Document won’t compile |
| Forgetting `{}`          | Syntax error           |
| Extra `$` in math        | Compilation error      |

---

# 1.6 Mini Practice Exercise

Try writing a document that contains:

* Title
* Your name
* 2 sections
* 1 equation
* 1 paragraph
* Today's date

---

# 🎯 Module 1 Learning Outcome

After completing Module 1, you should:

✔ Understand what LaTeX is
✔ Install/setup environment
✔ Create basic document
✔ Use sections
✔ Write simple math

---
