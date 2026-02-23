

# 🟢 MODULE 8: Bibliography & Citations (Detailed)

We will cover:

1. Manual Bibliography
2. BibTeX (Professional Method)
3. Referencing Styles
4. Common Errors
5. Full Working Example

---

# 🔹 8.1 Why Citations Are Important?

In research writing, you must:

* Cite books
* Cite research papers
* Cite websites
* Avoid plagiarism

LaTeX handles citations automatically.

---

# 🔹 8.2 Method 1: Manual Bibliography (Basic Method)

---

## ✅ Code

```latex
\documentclass{article}

\begin{document}

Research in AI is growing rapidly \cite{ai_book}.

\begin{thebibliography}{9}

\bibitem{ai_book}
Stuart Russell and Peter Norvig,
\textit{Artificial Intelligence: A Modern Approach},
Pearson, 2010.

\end{thebibliography}

\end{document}
```

---

## 🖨 Output

In text:

```
Research in AI is growing rapidly [1].
```

At bottom:

```
References

[1] Stuart Russell and Peter Norvig,
Artificial Intelligence: A Modern Approach,
Pearson, 2010.
```

---

## 🔎 What Is Happening?

* `\cite{ai_book}` → prints [1]
* `\bibitem{ai_book}` → defines reference
* Numbers assigned automatically

---

# 🔹 8.3 Method 2: BibTeX (Professional Method)

This is used in:

* IEEE papers
* ACM papers
* Research journals

---

## Step 1: Create `.bib` file

Example: `references.bib`

---

## ✅ Content of references.bib

```bibtex
@book{ai_book,
  author    = {Stuart Russell and Peter Norvig},
  title     = {Artificial Intelligence: A Modern Approach},
  publisher = {Pearson},
  year      = {2010}
}

@article{ml_paper,
  author  = {Andrew Ng},
  title   = {Machine Learning Trends},
  journal = {AI Journal},
  year    = {2020}
}
```

---

## Step 2: Use BibTeX in Main File

---

## ✅ Code

```latex
\documentclass{article}

\begin{document}

AI is evolving \cite{ai_book}.
Machine Learning is growing \cite{ml_paper}.

\bibliographystyle{plain}
\bibliography{references}

\end{document}
```

---

## 🖨 Output

In text:

```
AI is evolving [1].
Machine Learning is growing [2].
```

References:

```
[1] Stuart Russell and Peter Norvig...
[2] Andrew Ng...
```

---

## 🔎 What Is Happening?

* `\cite{ai_book}` → links to .bib entry
* `\bibliography{references}` → loads references.bib
* `\bibliographystyle{plain}` → defines format style

---

# 🔹 8.4 Common Bibliography Styles

| Style    | Usage             |
| -------- | ----------------- |
| plain    | Default numeric   |
| unsrt    | In citation order |
| alpha    | Author-year style |
| IEEEtran | IEEE papers       |

---

## Example IEEE Style

```latex
\bibliographystyle{IEEEtran}
```

Used for IEEE conference papers.

---

# 🔹 8.5 Using biblatex (Modern Method)

More flexible than BibTeX.

---

## ✅ Code

```latex
\documentclass{article}
\usepackage[backend=biber]{biblatex}
\addbibresource{references.bib}

\begin{document}

AI is important \cite{ai_book}.

\printbibliography

\end{document}
```

---

## 🖨 Output

Clean formatted bibliography with modern formatting.

---

# 🔹 8.6 Citing Multiple References

---

## ✅ Code

```latex
\cite{ai_book, ml_paper}
```

---

## 🖨 Output

```
[1, 2]
```

---

# 🔹 8.7 Citing with Author Name

Using biblatex:

```latex
\textcite{ai_book}
```

Output:

```
Russell and Norvig (2010)
```

---

# 🔹 8.8 Full Professional Example (IEEE Style)

---

## ✅ Code

```latex
\documentclass{article}
\usepackage{cite}

\begin{document}

Deep learning is powerful \cite{ai_book}.

\bibliographystyle{IEEEtran}
\bibliography{references}

\end{document}
```

---

# 🔹 8.9 Important Compilation Steps (Very Important ⚠)

If using BibTeX:

You must compile in this order:

1. LaTeX
2. BibTeX
3. LaTeX
4. LaTeX

If not → references show `??`

---

# 🔹 8.10 Common Beginner Mistakes

| Problem            | Solution                 |
| ------------------ | ------------------------ |
| Reference shows ?? | Compile multiple times   |
| .bib not loading   | Check filename           |
| Citation not found | Check key spelling       |
| Wrong style        | Change bibliographystyle |

---

# 🎯 After Module 8 You Can

✔ Create references manually
✔ Use BibTeX professionally
✔ Use IEEE style
✔ Cite books and papers
✔ Manage large reference lists
✔ Avoid plagiarism
