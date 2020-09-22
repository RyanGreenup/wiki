---
title: Exporting this wiki
description: How to manage flat markdown files
published: true
date: 2020-09-22T06:50:00.444Z
tags: 
editor: markdown
---

#  export this wiki

If you export this wiki into a folder structure of text files this page is intented to explain how to interact with them using FOSS tools to get find, search, tags, export etc.

Basically just use [my shell Scripts](https://github.com/RyanGreenup/cadmus), I intend to write up the logic I used for each command here, that way people can edit this page to make it more robust and make PR's and stuff.

> The tags aren't correctly implemented yet, I need to fix those by doing something like this:
> ```bash
> rg --pcre2 '(?<=[---\n[\s\S]ags:).*[,\s|:\s][a-z]+' -t markdown -o | sd -s ':' ' ' | sd -s ',' ' ' | sed s/^/tmsu\ tag\ /
> ```
{.is-warning}

> Maybe somebody with more *Windows* expertise could make this compatible with WSL?
{.is-info}

## Search
```bash
sk --ansi -m -c 'rg -l -t markdown --ignore-case "{}"'    \
    --preview "mdcat {} 2> /dev/null                             |\
            rg --pretty --colors  --context 20 {cq}                \
                --no-line-number --ignore-case                     \
                --colors 'match:fg:21,39,200'                      \
                --colors 'line:style:nobold'                       \
                --colors 'match:style:bold'                        \
                --colors 'match:bg:30,200,30'"                     \
     --bind 'ctrl-f:interactive,pgup:preview-page-up,pgdn:preview-page-down'    \
     --bind 'ctrl-w:execute-silent(echo {}    |\
         xargs realpath                       |\
         xclip -selection clipboard)'                                           \
     --bind 'alt-w:execute-silent(echo {} | xclip -selection clipboard)'        \
     --bind 'alt-v:execute-silent(code -a {}),alt-e:execute-silent(emacs {})'   \
     --bind 'ctrl-o:execute-silent(xdg-open {})'                                \
     --bind 'alt-y:execute-silent(cat {} | xclip -selection clipboard)'         \
     --bind 'alt-o:execute-silent(cat {}      |\
         pandoc -f markdown -t html --mathml  |\
         xclip -selection clipboard)' \
     --bind 'alt-f:execute-silent(echo {}        |\
         xargs dirname                           |\
         xargs cd; cat {}                        |\
         pandoc -f markdown -t dokuwiki --mathml |\
         xclip -selection clipboard)'            \
     --color=fg:#f8f8f2,bg:-1,matched:#6272a4,current_fg:#50fa7b,current_bg:#381070,border:#ff79c6,prompt:#bd93f9,query:#bd93f9,marker:#f1fa8c,header:#f1fa8c

```


## Tags

## Links

### back links

## Preview

- markserv
- mkdocs
- vscode
- atom markdown Preview enhanced

don't bothers with mdwiki  it crashed,  same fir pervane  
 ###  static  site
 
 ###  export
 
 * marktext
 * vscode
 * vnote??

## Wditors

- vim
- emacs

## other relevant  tools

###  markdown

* Joplin
* Vnote

### wikis

- dokuwiki
- pepperminty
-  wikitten ;see my notes in this)

i  found media Wiki to complex

##  Mobile

* Markor
* Mweb