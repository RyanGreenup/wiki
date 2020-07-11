---
title: Standards for the Wiki
description: The Markdown Style to adhere to for fortability sake
published: true
date: 2020-07-11T01:24:07.684Z
tags: markdown
editor: markdown
---

# Standards for Markdown

* [Note Taking Requirements](./Note-Taking-Requirements.md)



## Links

Use `[normal linksj](./path.md)` prefixed with a `./` rather than `[[wiki-links]]` because they have greater cross compatability, unless you can figure out how to:

* Have `wiki-links` work in *MkDocs* and/or *MarkServ*
    * I need some way to export everything as a static site with the links preserved.
* Have `wiki-links` work in VSCode Preview


Wiki links have the advantage of *Peek Definition* in VSCode which I really like, as well as promoting interlinking.

## Indenting

Use 4-spaces not two because python-markdown (and hence mkdocs but also iaWriter) considers anything else a bug.

## Math

### Display Math

If you use Display math be mindful that:


* This is compatible with everything period
    ```tex
    $\begin{aligned}
    4x
    \end{aligned}%$
    ```

* This is compatible with everything $\neg$ *MarkText*
    ```tex
    $$\begin{aligned}
    4x
    \end{aligned}$$
    ```
* This is compatible with everything $\neg$ *iaWriter*
    ```tex
    $$
    \begin{aligned}
    4x
    \end{aligned}
    $$
    ```

### Left Aligned Inline Full Size Equation

> This is hacky but highly compatible.

If possible use inline math with the aligned environment, because this odd behaviour is supported in LaTeX, MathJax and KaTeX.

It is necessary to have a trailing `%` like this:

```tex
$\begin{aligned}
ax^2 + bx + c = 0
\end{aligned}%$
```
which will produce math like this:

$\begin{aligned}
\ \\
\vec{u}&= \begin{bmatrix} u_{11} \\ u_{21} \end{bmatrix} \\
\vec{v}^\mathrm{T}&= \begin{bmatrix} v_{11} & v_{12} & v_{13} \end{bmatrix} \\
\ \\
\vec{u} \cdot  \vec{v}^\mathrm{T} &= \begin{bmatrix} u_{11} \\ u_{21} \end{bmatrix} \cdot  \begin{bmatrix} v_{11} & v_{12} & v_{13} \end{bmatrix} \\
&= \begin{bmatrix} u_{11}\cdot  v_{11} & v_{12} & v_{13}\\
u_{12} & \ldots & &\end{bmatrix} \\
&= \begin{bmatrix} u_{11}\cdot  v_{11} & u_{11}\cdot  v_{12} & u_{11}\cdot  v_{13} \\
u_{21} \cdot  v_{11} & u_{21}\cdot  v_{12}& u_{21}\cdot  v_{13}& \end{bmatrix}
\ \\
\end{aligned}%$



## Headings

Unlike `org-mode` `# Headings` **must** be surrounded by white space characters to work everywhere.

`# Heading1` Should be considered at the heading level, because:

1. Not all Makrdown Parsers respect [YAML] Fontmatter [^frontmatter-tools]
2. This will make it easier to dump a bunch of notes into a signle document
    * and take that document into LaTeX for a sort of [*Wiki Books*] style export.
  
 

[*Wiki Books*]: https://en.wikibooks.org/wiki/Main_Page
[YAML]: https://github.com/jekyll/jekyll/wiki/yaml-front-matter
[rmarkdown]: https://cran.r-project.org/web/packages/rmarkdown/index.html
[js-yaml]: https://github.com/nodeca/js-yaml
[Python-FrontMatter]: https://pypi.org/project/python-frontmatter/
[^frontmatter-tools]: See also [Python-FrontMatter], [rmarkdown] and [js-yaml] for some tools to manage frontmatter

## List Spacing

Use four spaces in order to be compatible with [*MkDocs*] and consistent with [*Google's Python Style Guide*] and [*Julia's Style Guide]

[*MkDocs*]: https://www.mkdocs.org/user-guide/writing-your-docs/#file-layout
[*Google's Python Style Guide*]: https://juliapackages.com/p/style
[*Julia's Style Guide]: https://juliapackages.com/p/style

## Tags

Although WikiJS doesn't support `#tags`, feel free to use them because they are very easy to parse out with `grep` and so widely supported in other editors such as [*iaWriter*], [*Obsidian*], [*Zettlr*] and ~~[*VimWiki*]~~ [^vwtg].

 <p style = "font-family:Courier New,Courier, monospace,serif;font-size:12px;font-style:italic; " align="right"  color=blue>
   <b>
      #Markdown<br>
      #stardise<br>
      </b>
      </p>
      
[*iaWriter*]: https://ia.net/writer
[*Obsidian*]: https://obsidian.md/
[*Zettlr*]: https://www.zettlr.com/
[*VimWiki*]: https://github.com/vimwiki/vimwiki
[*Org Mode*]: https://orgmode.org/manual/

[^vwtg]: No I forgot [*VimWiki*] uses [*Org Mode*] style `:tags:`, I was thinking of `[[wiki-links]]`.

      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      