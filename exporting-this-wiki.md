---
title: Exporting this wiki
description: How to manage flat markdown files
published: true
date: 2020-07-17T03:04:59.993Z
tags: 
editor: undefined
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