---
title: WikiJS vs Dokuwiki
description: Differences between WikiJS and why/when to choose one over the other
published: 1
date: 2021-02-23T06:28:59.623Z
tags: 
editor: markdown
dateCreated: 2021-02-22T13:06:04.284Z
---

# WikiJS vs Dokuwiki

> see also:
>  - [Installing WikiJS for Local Use](./installing-wikijs-for-local-use.md)
{.is-info}

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

| DokuWiki | WikiJS |
| --- | --- |
| Backlinks |     |
| Edit per Section |     |
| MathJax |     |
|     | Modern Aesthetic |
|     | Import Export a directory of Markdown Files |
|     | Compatible with Markdown Formatting [see points](#compatible) |

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
  
  

## Next Steps

- Set up a local version of dokuwiki, tied together with syncthing
  
- write up a note on how you set that up
  
- Import all Markdown Notes into WikiJS and evaluate a way that they can work together sanely.
  
  - Fortunately `git` should make this kind of easy-ish
    

If all of those work well enough, an argument can be made for using WikiJS in place of Dokuwiki, even though it's less featurefull, it does mean that there is only one format to worry about and assuming that it's as easy to run locally as it is, that might not be an issue.

### Looking Forward

WikiJS 3.0 will drop Sqlite, it will be necessary to use an entire postgreSql installation, this is unfourtunate, but it may not matter, in that time (a couple years) alternative options may present themselves (watch bookstack and outline).

Worst case scenario dokuWiki easy to migrate into.