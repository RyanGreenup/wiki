---
title: Template
description: 
published: true
date: 2020-08-30T11:47:44.170Z
tags: 
editor: undefined
---

# Template

Use this for an RMD Template:

```

---
title: "Sample Exam 1"
tags: ["Notebooks/Thinking About Data"]
output: 
  html_document: 
    keep_md: yes
    toc: yes
  html_notebook: 
    toc: yes
---
```
# Question 6 2014

## Preamble


```r
  if(require("pacman")){
    library(pacman)
  }else{
    install.packages("pacman")
    library(pacman)
  }
```

```
## Loading required package: pacman
```

```r
    pacman::p_load(xts, sp, gstat, ggplot2, rmarkdown, reshape2, ggmap,
                 parallel, dplyr, plotly, tidyverse, reticulate, UsingR, Rmpfr,
                 swirl, corrplot, gridExtra, mise, latex2exp, tree, rpart, lattice,
                 coin, primes, epitools, maps, clipr, ggmap, twitteR, ROAuth,
                 tm, rtweet, base64enc, httpuv, SnowballC, RColorBrewer, wordcloud, ggwordcloud)

  
  
   mise()
```
