---
title: Chi-Distribution
tags: [Chi, Exam, Notebooks/Social Web Analytics]
created: '2020-06-15T00:23:19.128Z'
modified: '2020-06-15T00:23:19.128Z'
---

# Chi-Distribution

# Question 6 2014

```r
knitr::opts_chunk$set(fig.path = "./figure/")

##  Tokens can be located [here]
## (~Dropbox/Studies/2020Autumn/Social_Web_Analytics/Practicals/Twitter_Tokens.org)
```

## Part a
Identify one problem with using the chi test.

The Chi test requires all expected counts to be more than 5.

## Part B
Merging Syndey and Newcastle Would allow for 

|           | A   | B   | C   | Total |
| ---       | --- | --- | --- | ---   |
| Melbourne | 9   | 14  | 15  | 38    |
| NSW       | 9   | 11  | 7   | 27    |
| TOTAL     | 18  | 25  | 22  | 65    |


## Find the Expected Counts
The expected counts, under the assumption that Melbourne/NSW would have the same
distribution across A/B/C can be found, in practice, by:

> rowTotal * ColumnTotal / Grand Total

This can be calculated by taking the outer product of the column and row totals divided by the grand total:


```
           --  -- 
           | 38 |
expected = |    |     oxo     [ 18    25    22 ]
           | 27 |   
           --  -- 
```


```r
col <- c(18, 25, 22)
row <- c(38, 27)
total <- 65

row %o% col /total
```

i.e., more clearly:

```r
e <- 
c(
  38,
  27
)       %o% c(18, 25, 22) / 65
```


```
##           [,1]     [,2]      [,3]
## [1,] 10.523077 14.61538 12.861538
## [2,]  7.476923 10.38462  9.138462
```


This provides the expected counts as:

|           | A        | B         | C         |
| ---       | ---      | ---       | ---       |
| Melbourne | 10.52308 | 12.861538 | 10.384615 |
| NewCastle | 14.61538 | 7.476923  | 9.138462  |


## Part d
The Chi Square statistic is given by:


```r
chi <- function(e,o) {

  sum((e-o)^2/e)
  
}
```

where:

 * e is the expected value
 * o is the observed value

so we could use R to calculate this:


```r
(o <- matrix(c(9, 9, 14, 11, 15, 7), nrow = 2))
```

```
##      [,1] [,2] [,3]
## [1,]    9   14   15
## [2,]    9   11    7
```

```r
sum((e-o)^2/e)
```

```
## [1] 1.449052
```

Hence the chi squared statistic is 6.87
