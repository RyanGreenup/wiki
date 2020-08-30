---
title: Adjacency-Matrices
created: '2020-06-15T00:23:19.152Z'
modified: '2020-06-15T00:23:19.156Z'
---

# Adjacency-Matrices
## Interpreting an Adjacency Matrix
Take a row name, look across the matrix left-to-right, marked cells indicate nodes to which travel is permitted.

* rows are observed nodes in the graph
* colums are features of the graph, i.e. possitble destinations from an observation

## Writing

* Write the nodes vertically down a table
* Mark accross the rows, left-to-right, indicating to which destination travel is permitted.

## Example
```R
library(igraph)
gd1 = graph.formula(1-+2, 2-+3, 3-+1)
plot(gd1)
get.adjacency(gd1)
```
![3ndgraphexample](_v_images/20200608121730317_1198392795.png)

|     |  1  |  2  |  3  |
| --- | --- | --- | --- |
| 1   | 0   | 1   | 0   |
| 2   | 0   | 0   | 1   |
| 3   | 1   | 0   | 0   |
