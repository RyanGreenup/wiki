---
title: Transition-Matrix-Graphs2
description: 
published: true
date: 2020-08-30T11:47:46.296Z
tags: 
editor: undefined
---

# Transition-Matrix-Graphs2
- author: Ryan Greenup
- title: Practice Exam 05 PCA and MDS Visualisation
> See Also:
> - [Graphs-Betweenness-Centrality](./../Graphs-Betweenness-Centrality.md)
> -[Transition-Probability-Matrix](./../../../Mathematics/Linear-Algebra/Transition-Probability-Matrix.md)

> PCA 2013, Q5

Consider the following graph:

``` example
  +-----+            +------+
  | C   +--------->>>+  B   |
  +-+---+            +---+--+
    |                    ^
    |                    ^
    |                    |
    |                    |
    V                    V
    V                    V
    +--->>+-------+<<----+
          |   A   |
          +---+---+
              ^
              ^
              |
              |
    +---------+------------+
    |                      |
    |                      |
    |                  +---+----+
+---+--+               |        |
|  D   +<<----------->>+   E    |
+------+               +--------+
```


(a) Construct Prob Trans Mat
----------------------------

The probability transition matrix is *the transpose of the adjacency
matrix* with all columns scaled to one.

It represents the probability having left a given vertex during a random
walk.

### Adjacency Matrix

An element of the adjacency matrix describes how many edges connect the
row-vertex to the column-vertex.

|     |     |     |     |     |     |
|-----|-----|-----|-----|-----|-----|
|     | A   | B   | C   | D   | E   |
| A   | 0   | 0   | 0   | 0   | 0   |
| B   | 1   | 0   | 0   | 0   | 0   |
| C   | 1   | 1   | 0   | 0   | 0   |
| D   | 1   | 0   | 0   | 0   | 1   |
| E   | 1   | 0   | 0   | 1   | 0   |

### Transpose to get the state distribution

use `M-x org-transpose-table-at-point`

|     |     |     |     |     |     |
|-----|-----|-----|-----|-----|-----|
|     | A   | B   | C   | D   | E   |
| A   | 0   | 1   | 1   | 1   | 1   |
| B   | 0   | 0   | 1   | 0   | 0   |
| C   | 0   | 0   | 0   | 0   | 0   |
| D   | 0   | 0   | 0   | 0   | 1   |
| E   | 0   | 0   | 0   | 1   | 0   |

### Scale Columns to 1 - Probability Transition Matrix

The Probability transition matrix is such that each column of the
transposed adjacency matrix is scaled to 1 in order to represent the
probability during a random walk:

|     |     |     |     |     |     |
|-----|-----|-----|-----|-----|-----|
|     | A   | B   | C   | D   | E   |
| A   | 0   | 1   | 1/2 | 1/2 | 1/2 |
| B   | 0   | 0   | 1/2 | 0   | 0   |
| C   | 0   | 0   | 0   | 0   | 0   |
| D   | 0   | 0   | 0   | 0   | 1/2 |
| E   | 0   | 0   | 0   | 1/2 | 0   |

(b) State if it's ergodic
-------------------------

A graph is ergodic if we can find a finite path between all pairs of
vertices.

Essentially, a graph is ergodic if any row of the probability transition
matrix is 0.

(c) Construct random surfer Prob Mat
------------------------------------

### Theory

The Random Surfer Probability Transition Matrix is given by:

λT + (1-λ)B

Where B is defined as:

|     |     |     |     |     |
|-----|-----|-----|-----|-----|
| 1/N | 1/N | 1/N | 1/N | 1/N |
| 1/N | 1/N | 1/N | 1/N | 1/N |
| 1/N | 1/N | 1/N | 1/N | 1/N |
| 1/N | 1/N | 1/N | 1/N | 1/N |
| 1/N | 1/N | 1/N | 1/N | 1/N |

Where:

N=\|\|V\|\|
:   is the number of vertices

### Working

At this point this will be easier to do in ***R***:

``` r
T <- rbind(
    c(0, 1, 1/2, 1/2, 1/2),
    c(0, 0, 1/2, 0, 0),
    c(0, 0, 0, 0, 0),
    c(0, 0, 0, 0, 1/2),
    c(0, 0, 0, 1/2, 0)
)

B  <- matrix(data = 1, ncol = 5, nrow = 5)/5

λ <-  0.8

λ*T + (1-λ)*B
```

``` example

     [,1] [,2] [,3] [,4] [,5]
[1,] 0.04 0.84 0.44 0.44 0.44
[2,] 0.04 0.04 0.44 0.04 0.04
[3,] 0.04 0.04 0.04 0.04 0.04
[4,] 0.04 0.04 0.04 0.04 0.44
[5,] 0.04 0.04 0.04 0.44 0.04
```

(d) Is it stationary
--------------------

If the distribution is stationary then the recurrence relation will not
change, so for example:

``` r
(S <- λ*T + (1-λ)*B)
(p <- c(0.49, 0.34, 0.10, 0.04, 0.03)) %>% as.matrix()
S %*% p
```

``` example
     [,1] [,2] [,3] [,4] [,5]
[1,] 0.04 0.84 0.44 0.44 0.44
[2,] 0.04 0.04 0.44 0.04 0.04
[3,] 0.04 0.04 0.04 0.04 0.04
[4,] 0.04 0.04 0.04 0.04 0.44
[5,] 0.04 0.04 0.04 0.44 0.04

     [,1]
[1,] 0.49
[2,] 0.34
[3,] 0.10
[4,] 0.04
[5,] 0.03

      [,1]
[1,] 0.380
[2,] 0.080
[3,] 0.040
[4,] 0.052
[5,] 0.056
```

In this case the probability transition matrix changed after an
iteration of the recurrence relation and so this is not a stationary
point.
