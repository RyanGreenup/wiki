---
title: 00_PracExam_1
tags: [Social Web Analytics]
created: '2020-06-15T00:23:19.184Z'
modified: '2020-06-29T01:03:07.888Z'
---

author: Ryan Greenup
category: Exemplar
csl_style: /home/ryan/Templates/CSL/nature.csl
header-includes:
`\usepackage{/home/ryan/Dropbox/profiles/Templates/LaTeX/ScreenStyle}`{=latex}
html_head_extra: \<link rel="stylesheet" type="text/css"
  href="/home/ryan/Templates/CSS/Org-CSS/bigblow.css"\>
infojs_opt: view:showall toc:3
property: header-args:R :session Final :dir ./ :cache yes :eval never-export
  :exports both :results output
title: Practice Exam 05 PCA and MDS Visualisation

`\usepackage{/home/ryan/Dropbox/profiles/Templates/LaTeX/ScreenStyle}`{=latex}

2015 Q2 Cosine Similarity
=========================

Given the Following Document Term Matrix:

|     | T1  | T2  | T3  |
|-----|-----|-----|-----|
| D1  | 1   | 1   | 2   |
| D2  | 0   | 2   | 1   |
| D3  | 3   | 1   | 0   |

What are Reasons for and against the removal of Stop words
----------------------------------------------------------

Removing stop words can make the search more efficient, noise that
doesn't add information will be removed. However, care needs to be taken
to ensure that the amount of available information is not reduced, or at
least reduced signific.ntly relative to the amount of clarity provided
by stop word removal.

Compute the Cosine Similarity
-----------------------------

> Compute the cosine similarity score of each document to the query
> `T1 T3` by using term frequencies

### What is the Cosine

The cosine similarity is the cosine of the angle between two vectors,
this can be expressed as:

$$\begin{aligned}
      \cos\left( \theta \right)&= \cos\left( \vec{u}\cdot  \vec{v} \right)\\
      &= \frac{\vec{u}\cdot  \vec{v}}{\left| \left| \vec{u} \right|
      \right|\cdot  \left| \left| \vec{v} \right| \right|}
\end{aligned}$$

> The Cosine Similarity is the equivalent to the dot product of the unit
> vecots

### What is the vector value of the query.

If the query is `T1 T3` then it only contains:

-   `T1` once
-   `T2` once

And hence can be represented by the frequency vector $q$:

``` r
q <- c(1, 0, 1)
```

The Cosine Distance is $1- \cos\left( \theta \right)$ so that the a
smaller value indicates a smaller distance.

``` r
d1 <- c(1, 1, 2)
d2 <- c(0, 2, 1)
d3 <- c(3, 1, 0)
```

First scale the documents to size 1, this can be acheived by dividing
through by the euclidean distance:

``` example
[1] 0.4082483 0.4082483 0.8164966

[1] 0.0000000 0.8944272 0.4472136

[1] 0.9486833 0.3162278 0.0000000

[1] 0.7071068 0.0000000 0.7071068
```

and then taking the dot products, obviously I won't use the built in
function, but I'll write my own to save repetition:

> The dot product of two vectors is the sum of the multiple of each
> corresponding term of two vectors.

``` r
## By default R multiplies the terms pairwise.

print(sum(d1_u * q_u))
print(sum(d2_u * q_u))
print(sum(d3_u * q_u))
```

``` example

[1] 0.8660254

[1] 0.3162278

[1] 0.6708204
```

Hence:

-   The distance from D1 to the qury is 0.87
-   The distance from D2 to the qury is 0.32
-   The distance from D3 to the qury is 0.67

(c) Which tweet is more similar to the Query
--------------------------------------------

The first tweet is the most similar to the query because the large
cosine value indicates a smaller angle between the two vectors and
implies that the two vectors are more similar.

(d) Multiple Terms
------------------

Including multiple repetitions of the terms wouldn't matter if they were
included in the same proportions because the cosine similarity is a
function of the angle between the two vectors not the magnitude of
either vector.

As a matter of fact, presuming that the proportions were preserved the
cosine similarity would remain consistent.

> granted however, if the proportions were changed, then the cosine
> similarity would also change, for better or for worse.

2014 Q1 Graphs
==============

`````` example

              `````
             ` C
             `    ```````      `` ``
            ``   `           `.  A  `
          ``                  `  `  `
        ``                        `
   `` ``                           `
 ` F  `                            `
`` `  `                             `
 `````                              `
     `                               `
     `                             `` ` ``
      `                            `  B  `
      ``                           ``   `
       `                         ``
      `` ```                   ``
     `  E  `                 ``
      ``  `` ````       `````
                     ``` `D  `
                       `    `
``````

(a) Construct the adjacency Matrix
----------------------------------

> the adjacency matrix tells you where a row can travel to.
>
> From row to column.
>
> So for example A -\>

(a) Construct Adgacency Matrix
------------------------------

1.  Write the nodes down vertically as observations

2.  Fill the rows out left to write describing Destinations

    |     |     |     |     |     |     |     |
    |-----|-----|-----|-----|-----|-----|-----|
    |     | A   | B   | C   | D   | E   | F   |
    | A   | 0   | 1   | 1   | 0   | 0   | 0   |
    | B   | 1   | 0   | 0   | 1   | 0   | 0   |
    | C   | 1   | 0   | 0   | 0   | 0   | 1   |
    | D   | 0   | 1   | 0   | 0   | 1   | 0   |
    | E   | 0   | 0   | 0   | 1   | 0   | 1   |
    | F   | 0   | 0   | 1   | 0   | 1   | 0   |

(b) Tabluate the Degree Distribution
------------------------------------

### Degrees

The degree of a vertex is measured as the number of edges that connect
to the vertex.

### Degree Distribution

The Degree distribution is a tabulation of the frequency at which a
given degree occurs.

In this case all 6 vertices are degree 2 and so:

|           |     |     |     |     |     |     |     |
|-----------|-----|-----|-----|-----|-----|-----|-----|
| Degree    | 0   | 1   | 2   | 3   | 4   | 5   | 6   |
| Frequency | 0   | 0   | 6   | 0   | 0   | 0   | 0   |

(c) Calculate the graph density
-------------------------------

Graph Density is:

``` r
g-dens = num_edges / possible_edges
       = 2*abs(e) / (abs(v) * (abs(v) - 1) )
```

So to calculate the graph density:

``` r
g_dens <- function(e,v) {
    2*abs(e) / (abs(v) * (abs(v) - 1))
}
g_dens(6, 6)
```

``` example

[1] 0.4
```

So in this case the graph density is 0.4

(d) Calculate the betweenness centrality for each vertex
--------------------------------------------------------

> To calculate betweenness centrality, you take every pair of the
> network and count how many times a node can interrupt the shortest
> paths

The betweenness centrality is the sum of the ratios between:

1.  the number of shortest paths between two vertices
2.  the number of shortest paths between two vertices that passes
    through the vertex of interest

So first you have to list every possible combination of pairs:

|     |     |     |     |     |     |     |
|-----|-----|-----|-----|-----|-----|-----|
|     | A   | B   | C   | D   | E   | F   |
| A   | x   | x   | x   | x   | x   | x   |
| B   |     | x   | x   | x   | x   | x   |
| C   |     |     | x   | x   | x   | x   |
| D   |     |     |     | x   | x   | x   |
| E   |     |     |     |     | x   | x   |
| F   |     |     |     |     |     | x   |

Which can be translated as:

    AA, AB, AC, AD, AE, AF
            BC, BD, BE, BF
                CD, CE, CF
                    DE, DF
                        EF

So first write down each pairing as an observation, the features will be
the *interupting node*, we write the number of times the shortest path
could be interupted by this node.

So for instance with regard to A

AB, AC, … AF
:   are omitted because they will always contain A and don't contribute
    to centrality

`BC`

:   is interrupted by `A` so 1/1:

    -   1 shortest path (denominator)
    -   1 time A is involved in the shortest path (numerator)

`BD`

:   is not interrupted by `A` so 0:

    -   1 shortest path (denominator)
    -   0 times A is involved (numerator)

`BE`

:   is not interrupted by `A` so 0:

    -   1 shortest path (denominator)
    -   0 times A is involved (numerator)

`BF`

:   is interrupted `A` 1/2 times:

    -   2 shortest paths (denominator)
    -   1 of which is interupted by `A` (denominator)

Our betweenness centrality score is the sum of the columns.

|     |     |     |     |     |     |     |
|-----|-----|-----|-----|-----|-----|-----|
|     | A   | B   | C   | D   | E   | F   |
| AB  | x   | x   |     |     |     |     |
| AC  | x   |     | x   |     |     |     |
| AD  | x   |     |     | x   |     |     |
| AE  | x   |     |     |     | x   |     |
| AF  | x   |     |     |     |     | x   |
| BC  | 1/1 | x   | x   |     |     |     |
| BD  | 0/1 |     |     | x   |     |     |
| BE  | 0/1 |     |     |     | x   |     |
| BF  | 1/2 |     |     |     |     | x   |
| CD  | 1/2 |     | x   | x   |     |     |
| CE  | 0/1 |     | x   |     | x   |     |
| CF  | 0/1 |     | x   |     |     | x   |
| DE  | 0/1 |     |     | x   | x   |     |
| DF  | 0/1 |     |     | x   | x   | x   |
| EF  | 0/1 |     |     |     |     | x   |

No you'll notice I haven't bothered to fill out the whole table, that's
because the centrality of any node in the graph does not change
regardless of how the labels are bijected among the vertices.

So for all Vertices, the between centrality score is 2.

PCA 2013, Q3
============

In conducting a principal component analysis ***R*** produces the
following summary output:

|                    |       |       |       |       |       |       |       |
|--------------------|-------|-------|-------|-------|-------|-------|-------|
|                    | PC1   | PC2   | PC3   | PC4   | PC5   | PC6   | PC7   |
| Standard Deviation | 3.923 | 3.069 | 2.867 | 2.579 | 2.038 | 1.887 | 1.125 |
| Prop of Var        | 0.316 | 0.194 | 0.169 | 0.137 | 0.085 | 0.073 | 0.026 |
| Cumulative Prop    | \*\*  | 0.510 | 0.679 | \*\*  | 0.901 | 0.974 | 1     |

(a) Compute the Missing entries
-------------------------------

The Cummulative Proportion of Variance is the running total for the
amount of variation explained by the principal components.

|                  |     |
|------------------|-----|
|                  | PC1 |
| Cumulative Prop. |     |
|                  |     |
|                  |     |

-   Cumulative Proprtion

    PC1
    :   0.316 + PC4

    PC4
    :   0.679 + 0.137 = 0.816

Compute the Binary Metric between the following tweets
------------------------------------------------------

> tweet 1
> :   assault assistance disadvantaged university students begins
>
> tweet 2
> :   believe more students doing university better

The unique words are:

|               |         |         |       |
|---------------|---------|---------|-------|
| Word          | Tweet 1 | tweet 2 | Total |
| assault       | 1       | 0       | 1     |
| assistance    | 1       | 0       | 1     |
| disadvantaged | 1       | 0       | 1     |
| university    | 1       | 1       | 2     |
| students      | 1       | 1       | 2     |
| begins        | 1       | 0       | 1     |
| believe       | 0       | 1       | 1     |
| more          | 0       | 1       | 1     |
| doing         | 0       | 1       | 1     |
| better        | 0       | 1       | 1     |

The words that are shared in common are:

|            |         |         |       |
|------------|---------|---------|-------|
| Word       | Tweet 1 | tweet 2 | Total |
| university | 1       | 1       | 2     |
| students   | 1       | 1       | 2     |

So there are 10 unique words of which 2 are shared in common and so the
binary distance is 1 - 2/10 = 0.80

Graphs Transition Matrix 2013, Q5
=================================

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

Trends 2014 Q8
==============

Take the Following Data:

|       |          |          |          |
|-------|----------|----------|----------|
|       | Period 1 | Period 2 | Period 3 |
| Day 1 | 66       | 97       | 69       |
| Day 2 | 68       | 111      | 87       |
| Day 3 | 103      | 112      | 87       |

In order to examine the fluctuation for each day, break the data into
its trend and periodic components, after a square root transformation:

``` r
data <- rbind(
  c(66,  97,  69),
  c(68,  111, 87),
  c(103, 112, 87)
)
sqrt(data)
```

``` example

          [,1]      [,2]     [,3]
[1,]  8.124038  9.848858 8.306624
[2,]  8.246211 10.535654 9.327379
[3,] 10.148892 10.583005 9.327379
```

In this case the period is a time of day, so for example Morning, Lunch,
Evening, so a seasonal trend would be expected.

Taking a moving average over the period of that trend however will
remove the influence of that seasonality:

$$\begin{aligned}
Y  = T + S + Ɛ               \\
  &= T + 0 + 0               \\
  &= T
\end{aligned}$$

(a) Calculate the Trend
-----------------------

Remember that the moving average the window expands evenly in both
directions, so for example day2, period2 would be calculated as:

``` r
library(tidyverse)
c(68, 11, 87)  %>%
  sqrt()  %>%
  sum() / 3
```

``` example

[1] 6.963405
```

(b) Calculate the Periodic Component
------------------------------------

The periodic component is S and can be calculated:

$$\begin{aligned}
Y  = T + S + Ɛ               \\
  &= T + 0 + 0               \\
  &= T
\end{aligned}$$
