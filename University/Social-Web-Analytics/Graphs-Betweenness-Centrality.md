---
title: Graphs-Betweenness-Centrality
created: '2020-06-15T00:23:19.144Z'
modified: '2020-06-15T00:23:19.144Z'
---

# Graphs-Betweenness-Centrality
author: Ryan Greenup
title: Scratch Buffer 05 PCA and MDS Visualisation

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

