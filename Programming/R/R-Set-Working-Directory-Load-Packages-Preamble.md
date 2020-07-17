---
title: Load Packages in R
description: Standard copy/paste stuff for a new R-Script
published: true
date: 2020-07-17T03:03:28.587Z
tags: 
editor: undefined
---

# Set Working Directory and Load Packages
Pacman is a program that will automatically install and load in various packages.

My preference is to have the working directory inside R as the location of the current script, the following commands will achieve that.


## RMarkdown 
RMarkdown Files automatically set the working directory as the location of the `*.rmd` file,

in order to load necessary packages:

```r
load.pac <- function() {
  if (require("pacman")) {
    library(pacman)
  }else{
    install.packages("pacman")
    library(pacman)
  }
  pacman::p_load(xts, sp, gstat, ggplot2, rmarkdown, reshape2, ggmap,
                 parallel, dplyr, plotly, tidyverse, reticulate, UsingR, Rmpfr,
                 swirl, corrplot, gridExtra, mise, latex2exp)
}

load.pac()
mise()
select <- dplyr::select
knitr::opts_chunk$set(fig.path = "./figure/07-Description-of-File")


set.seed(9823)
```


## R Script :memo: and   RMarkdown

```r

##############
###Preamble###
##############

# Set Working Directory and Load Packages ---------------------------------


setwd.loadpac <- function() {
  
  #Remove Latent Variables (except for the preamble trigger)
  rm(list = setdiff(ls(), "load.pac.switch"))
  
  #Test and install pacman package
  if (require('pacman')) {
    library('pacman')
  } else{
    install.packages('pacman')
    library('pacman')
  }
  
  #Use Pacman to install other useful packages
  pacman::p_load(ggplot2, rmarkdown, dplyr, plotly, rstudioapi, installr, reshape2)
  
  
  #Use the Rstudio API to get the working directory
  current_path <- getActiveDocumentContext()$path
  
  # Test if the document is saved and it's not an rmd
  if (length(current_path) > 1 && !grepl(".rmd", current_path)) {
    setwd(dirname(current_path)) # change the working directory to the curret folder
    print(getwd()) #Print what that working directory is
  } else if(length(current_path) > 1) {
    print(# if the file path is way to short tell the user to save the file
      "Could not set working directory to current directory, perhaps save the script or if in RMD disregard"
    )
  }
  
  #  updateR() #Uncomment if you want to update R
  
  
}

# Only Run Once
if (exists("load.pac.switch")) {
  # Only run this once, per session per script
  setwd.loadpac()
  load.pac.switch <- 0
}



##############
###Script#####
##############


```




# If Using RStudio
# Any R Script
This will only work if the whole script is executed, but it should set the working directory to the scriptlocation

This is a real pain in the ass though because it interferes with document knitting, so if inside R studio where knitting is desirable avoid this method


```r
# Set Working Directory
this.dir <- dirname(parent.frame(2)$ofile)
setwd(this.dir)
rm(this.dir)

# Load Packages
if(require('pacman')){
  library('pacman')
}else{
  install.packages('pacman')
  library('pacman')
}

pacman::p_load(xts, sp, gstat, ggplot2, rmarkdown, reshape2, ggmap,
               parallel, dplyr, plotly, tidyverse)
```

```r
library(rstudioapi)
current_path <- getActiveDocumentContext()$path
    setwd(dirname(current_path)) # change the working directory to the curret folder

```

## Set up Vim


When you first start up **_R_** you're going to want to use:

```
imap jj <Esc> | imap fd <Esc> | map <Space> <Leader>| map <Leader>w :w<CR>
```

So just copy paste the following, press `:` in **_R_** *Studio* and then press [[Shift]]-[[F10]] [[p]] [[Enter]] in order to send the command to the vim emulator

```
imap jj <Esc> 
```

```
imap fd <Esc> 
```

```
map <Space> <Leader>
```
```
map <Leader>w :w<CR>
```

## Blah

In order to load files use the following:

```r
# Print the name of what's loaded
(load("datafile.RData"))

# Do it silently
load("datafile.RData")

```

### Print Assignment

The following code blocks return the same output

```r
n <- 3; n
```
and 

```r
(n <- 3)
```






