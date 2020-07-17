---
title: Ryans WikiJS
description: 
published: true
date: 2020-07-17T03:56:32.728Z
tags: public
editor: markdown
---

# Math and Data Sci Wiki

> New Accounts must be made using [*Auth0*](https://manage.auth0.com/)!
{.is-warning}

* [Thinking About Data](./University/Thinking-About-Data.md)
* [Randomness](./University/Thinking-About-Data/01Randomness.md)
* [01Randomness](/University/Thinking-About-Data/01Randomness)
* [Confidence Intervals](./University/Thinking-About-Data/Confidence-Intervals.md)

## Data Sci

* [Applications of Big Data](./University/DataSci/Applications-of-Big-Data/Applications-of-big-data-home.md)
* [Predictive Modelling](./University/DataSci/Predictive-Modelling/Predictive-Modelling-home.md)
* [Social Web Analytics](./University/DataSci/Social-Web-Analytics/Social-Web-Analytics-home.md)
* [Discovery Project](./University/DataSci/Discovery-Project/Discovery-Project-home.md)

## Math

* [Quantitative Project](./University/MathSci/Capstone/Quantitative-Project-home.md)
* [Analysis](./University/MathSci/Analysis/Analysis-home.md)
* [Mathematical Modelling](./University/MathSci/MathModelling/Math-Modelling-home.md)




## Misc

* [Installing Arch](linux/installArch)
    * Look at *XFCE* and `i3`
    * Test Recoll in Pop-Shell
    * Fix Snapper
        * Quota Groups
        * Make more subvolumes to remove fluff
        * Review number of backups
* Review Project and Document Management things for [self hosted server](/home/Self-Hosted-ideas)
* ~~See [here](http://ryansnotes.org/mediawiki/index.php/Things_I_want_to_look_into) to check out different apps listed (live notetaking and also document managers)~~
  * Any alternatives to `i3` and *Pop-Shell*?
  * Check out Wiki Alternatives (see [Self Hosted](/home/Self-Hosted-ideas))
  
  
  
 
 
 
 
 
 
 
 
 
 
 
 



## Features

There are all the expected features in *WikiJS* (except admonitions which are represented by quotes with [CSS](https://en.wikipedia.org/wiki/Cascading_Style_Sheets))
> <kbd>Ctrl</kbd> + <kbd>s</kbd> works which is nice
{.is-info}

### KaTeX

You can produce math:


$$
\begin{aligned}
f\left( a \right) &= \frac{1}{2 \pi i} &= \oint_\gamma \frac{f\left( z \right)}{z- a} \mathrm{d}z
\end{aligned}
$$

with:

    $$
    \begin{aligned}
    f\left( a \right) &= \frac{1}{2 \pi i} &= \oint_\gamma \frac{f\left( z \right)}{z- a} \mathrm{d}z
    \end{aligned}
    $$

### Links

Use relative markdown links of the form `[name](./file.md)` see [standards for the wiki](./standards-for-the-wiki.md)

> Wiki-links are not supported (unfourtunately)
> [[blah]]
{.is-warning}

#### Bug
This version fixes [./relative-links.md](./relative-links.md) but you can't delete home, you can only move it, edge-case though tbh

### Exporting or Forking

See [exporting this wiki](./exporting-this-wiki.md)

### Pictures

Pictures are also supported:

![8bf032d2-a742-4d46-bc48-040d78ea137e.jpeg](/8bf032d2-a742-4d46-bc48-040d78ea137e.jpeg)

> * Tag export for git sync still omits square brackets [See this *GitHub* issue](https://github.com/Requarks/wiki/issues/1997)
>   * Still though I could just use `rg` and some thinking to pass these tags to *TMSU* anyway so this might not be as big an issue as I made it out to be.
>   
>     ```bash
>      rg --pcre2 '(?<=[---\n[\s\S]ags:).*[,\s|:\s][a-z]+' -t markdown -o | sd -s ':' ' ' | sd -s ',' ' ' | sed s/^/tmsu\ tag\ /
>      ```
{.is-warning}


## Admin TODO

[Self hosted ideas](./Self-Hosted-ideas.md)

[Integrating With Notable Etc.](./Notes/integrating-wikijs.md)

Consider joplin vs wikiJS on light of org roam server and even other options like leanote


[wikis and note taking](/home/wikis-and-note-taking)

[Managing Guests](managing-guests-in-wikijs)
