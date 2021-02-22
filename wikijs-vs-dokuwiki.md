---
title: WikiJS vs Dokuwiki
description: Differences between WikiJS and why/when to choose one over the other
published: 1
date: 2021-02-22T13:06:04.284Z
tags: 
editor: markdown
dateCreated: 2021-02-22T13:06:04.284Z
---

# WikiJS vs Dokuwiki



## KaTeX is only a minor disadvantage
Basically use `aligned` but:

1. Always put the `tag{}` outside
2. Only one `tag{}` per set of `$$`, it's not ideal but it's usable.
$$
\begin{aligned}
y = f(x)
\end{aligned} \tag{$\triangleleft$}
$$
$$
\begin{aligned}
\implies 4x &= 9 \\
 x &=\frac{9}{4}
\end{aligned} \tag{$\star$}
$$

Refer to equation $(\star)$

### Why KaTeX


<a name="why-katex"></a>
Atleast with respect to markdown, it works on:

- VsCode
- Zettlr
- Marktext

So we've just kinda gotta accept it.

| DokuWiki         | WikiJS                                                        |
| ---------------- | ------------------------------------------------------------- |
| Backlinks        |                                                               |
| Edit per Section |                                                               |
| MathJax          |                                                               |
|                  | Modern Aesthetic                                              |
|                  | Import Export a directory of Markdown Files                   |
|                  | Compatible with Markdown Formatting [see points](#compatible) |

### Compatible with Markdown Formatting... Who cares

<a name="compatible"></a>

This means that:

- Easy to import new documents
  
  - Just move them into the Git Repo
  
  - No fighting `pandoc` like with dokuwiki
    
    - although the math problem has simply been sidestepped
  
  - Car Write with Pre-existing tools:
    
    - See [above](#why-katex)
  
  ### Thoughts
  
  Can be used portably with a Sqlite Database and cross integrated with other tools by using a `git` repo with `basic` `http` authentication.
