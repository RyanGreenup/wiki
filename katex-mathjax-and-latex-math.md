---
title: Katex, Mathjax and LaTeX; Notation and Compatability
description: How to write mathematics in markdown in a way that is compatible across different tools
published: true
date: 2021-02-23T00:04:58.574Z
tags: 
editor: markdown
dateCreated: 2021-02-23T00:04:58.574Z
---

# equation number across latex katex and mathjax

So in $\LaTeX $ the correct way to manage equation numbering is:

```latex
\documentclass{article}
\usepackage{amsmath}
\begin{document
    \begin{align}
	        2x         &= 4 \notag \\
		\implies x &= 2 \label{eq:blah} \tag{**3**}
    \end{align*}      
    I can now reference \eqref{eq:blah} which is good.
\end{document}
```

See the below image:

![](./latex_eq_numbering.png)

This should also work with MathJax, the issue is that the `align` environment is simply not supported by KaTeX, alternatively the following is an option:

```latex
\begin{equation}
       \begin{aligned}
	    2x &= 4 \notag \\
	    \implies x &= 2 \label{eq:blah} 
	\end{aligned}\tag{**4**} \]
\end{equation}
```

When using the `amsmath` package in $\LaTeX$ the delimiters `\[ \]` are shorthand for the `{equation}` environment [^1]


```latex
\[
  \begin{aligned}
      2x &= 4 \notag \\
      \implies x &= 2 \label{eq:blah} 
  \end{aligned}\tag{**5**} \]
\]
```

---
---

$$
\begin{aligned}
            2x &= 4 \\
    \implies x &= 2 
\end{aligned}\tag{**4**}
$$
---
---


In Markdown when using KaTeX only `$$\n` are typically parsed, `pandoc -f markdown -t latex` will convert `$$\n` into `\[` so it's not a super big deal [^2]


[^1]: CITATION? check the manual
[^2]: One of the things that I'm trying to get across here is that $\LaTeX$ will not parse `$$\n` that have an `{aligned}` environment and `\tag{}` command.
