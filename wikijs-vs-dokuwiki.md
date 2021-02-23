---
title: WikiJS vs Dokuwiki
description: Differences between WikiJS and why/when to choose one over the other
published: true
date: 2021-02-23T23:30:01.431Z
tags: 
editor: markdown
dateCreated: 2021-02-23T12:48:07.848Z
---

# WikiJS vs Dokuwiki

> see also:
>  [Installing WikiJS for Local Use](./installing-wikijs-for-local-use.md)
{.is-info}

## General thoughts {.tabset}


### WikiJS

#### Advantages

Wikijs lays pages out in a way that is consistent with how people would take notes on a topic generally, i.e. structured directories and text files.

It's also really nice how any pre-existing markdown-tool like [zettlr](https://github.com/Zettlr/Zettlr), [marktext](https://github.com/marktext/marktext) or pandoc can easily be used to work with pages.

#### Disadvantages

Unfourtunately it's slower, clunkier, does not support per-section editing and linking to files isn't implemented very well.

### Dokuwiki

#### Advantages
Dokuwiki works out of the box, batteries included, does not have a database, is dead easy to set up, looks great and works very well with math.

#### Disadvantages

Dokuwiki does not [^1] really display the flat file structure, but more importantly, there isn't a non-trivial way to convert the corpus of text files into markdown/org, easily, the complexities being (when using [pandoc](https://github.com/jgm/pandoc):

- Mathjax becomes KaTeX which often breaks
- Pandoc doesn't convert the images
- Pandoc does not support Math when converting dokuwiki files [^2]
  - Although using `dokuwiki/bin/render.php < file.txt > file.html` does work if the mathjax plugin is installed
    - However this does not change images into HTML, the `{{:image:path.png}}` **does not** become `<img src="./image/path.png">` which is really a problem for things like plots.


#### Plugins
Dokuwiki also relies on a lot of plugins, which is good in terms of feature accessibility and community contribution, but a lot of features that should be really core features are handed off to plugins, which is not particularly idea.

#### Markdown
I'm going to experiment with the [mdpage](https://www.dokuwiki.org/plugin:mdpage) plugin, if that works and all the features work then that's probably a good compromise, for the moment I'll leave a dokuwiki and wikiJS up until we can settle on something.

[^2]: [Dokuwiki math support [enhancement] Â· Issue #5319 Â· jgm/pandoc Â· GitHub](https://github.com/jgm/pandoc/issues/5319)



[^1]: Without some admittedly good plugins)

### Gollum

It's good, but, a little slow and fiddly but this could be an option

### WikiDocs

I don't know much about [WikiDocs](https://www.wikidocs.it/demo), it does however look promising, very much a `#TODO`.

#### Mathematics

Mathematics still hasn't bee implemented [see this issue](https://github.com/Zavy86/WikiDocs/issues/16)

## KaTeX is only a minor disadvantage

Basically use `aligned` but:

1. Always put the `tag{}` outside
  
2. Only one `tag{}` per set of `$$`, it's not ideal but it's usable.m
  
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