---
title: Ryans WikiJS
description: 
published: true
date: 2020-07-03T10:08:14.703Z
tags: 
editor: markdown
---

Now as I write in here
It just works

# New Version (Beta)

$$
\begin{aligned}
f\left( a \right) &= \frac{1}{2 \pi i} &= \oint_\gamma \frac{f\left( z \right)}{z- a} \mathrm{d}z
\end{aligned}
$$




[test](./this-is-simpler.md)

## Bug
This version fixes [./relative-links.md](./relative-links.md) but you can't delete home, you can only move it, edge-case though tb.


I have since added the tags in, are they no longer added to the YAML, this is an ongoing issue.

### Formatting Test

$$
\begin{aligned}
f\left( a \right) &= \frac{1}{2 \pi i} &= \oint_\gamma \frac{f\left( z \right)}{z- a} \mathrm{d}z
\end{aligned}
$$ 

In view of this equation then:

$$\begin{aligned}
\left| \int_C \frac{f\left( z \right)}{z- z_0} \mathrm{d}z - 2 \pi i f\left( z_0 \right)  \right|<2 \pi \varepsilon
\end{aligned}$$ 


## New Features
* Kroki
* MathJax
* Mobile Editing is now bearable
  * In saying that editing straight to the wiki is actually a lot nicer, I much prefer it because theres no fucking around with sync
  * the  comparability If wikiJS with  markdown  and GitHub means it is the clear   choice compared to  mediawiki
* links work
* Tag export for git sync still omits square brackets
  * Still though I could just use `rg` and some thinking to pass these tags to *TMSU* anyway so this might not be as big an issue as I made it out to be.
  
    ```bash
     rg --pcre2 '(?<=[---\n[\s\S]ags:).*[,\s|:\s][a-z]+' -t markdown -o | sd -s ':' ' ' | sd -s ',' ' ' | sed s/^/tmsu\ tag\ /
     ```

# Home
Made after the git reset


[Thinking About Data](./University/Thinking-About-Data.md)
[Randomness](/University/Thinking-About-Data/01Randomness.md)
[Confidence Intervals](/University/Thinking-About-Data/Confidence-Intervals.md)

[Managing Guests](managing-guests-in-wikijs)
<kbd>Ctrl</kbd> + <kbd>s</kbd> works which is nice


[Self hosted ideas](./Self-Hosted-ideas.md)

[Integrating With Notable Etc.](./Notes/integrating-wikijs.md)

Consider joplin vs wikiJS on light of org roam server and even other options like leanote  

also whats the risk of http if im just going to use mobile data  

[wikis and note taking](/home/wikis-and-note-taking)

## Note to Self

> This should really be in my to do list app, I mean, whats the point otherwise, Im paying for it I may as well use it.
{.is-warning}

* [Install Arch](linux/installArch)
    * Look at *XFCE* and `i3`
    * Test Recoll in Pop-Shell
    * Fix Snapper
        * Quota Groups
        * Make more subvolumes to remove fluff
        * Review number of backups
* Review Project and Document Management things for [self hosted server](/home/Self-Hosted-ideas)
* See [here](http://ryansnotes.org/mediawiki/index.php/Things_I_want_to_look_into) to check out different apps listed (live notetaking and also document managers)
  * Any alternatives to `i3` and *Pop-Shell*?
  * Check out Wiki Alternatives (see [Self Hosted](/home/Self-Hosted-ideas))
* Test out Pop-Shell with Recoll and a sensible default markdown editor (something WYSIWYG like marktext).
  
  
  
  ## Documentation
*  [Tikz](/University/Documentation/Tikz)
    * [upmath](/University/Documentation/Tikz/upmath)
    
* [Comparing-Wikis](/Notes/Comparing-Wikis)
 ## Wiki Stuff
 * [Using Elastic Search in WikJS](./Notes/Using-Elastic-Search.md)
 * [Kroki](./wikijs/kroki.md)
 
 ### Markdown Editors
I just lost some work when the laptop crashed, the markdown editors I was considering where listed on the arche wiki, the one I was interested in was moeeditor. 

With regards to notetaking and wikis, O need to consider how clumsy it is to get material in and out and frankly the most painless tool is WikiJS, I’m not super happy with its mobile interface though. 

I may play with Moin moin simply because it doesn’t require a dB. 

 ideally Id use editors with interlinking support, recoll for searching (fzf ns script is perfect) and tmsu for tagging  
 
 I like notable but because ots not FOSS I dont want to get to wrapped up in it (I should keep an eye on zim and boostnote though)  
 
 
 
 $$
 \int 1+6
 $$
 
 ![8bf032d2-a742-4d46-bc48-040d78ea137e.jpeg](/8bf032d2-a742-4d46-bc48-040d78ea137e.jpeg)
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 

