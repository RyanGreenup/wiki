---
title: Graphs Problem Question Example
description: An example of a problem involving graphs from Social Web Analytics
published: true
date: 2020-08-30T23:25:57.257Z
tags: 
editor: undefined
---


# Table of Contents

1.  [2014 Q1 Graphs](#org7446cb7)
    1.  [(a) Construct the adjacency Matrix](#orgdb9cb71)
    2.  [(a) Construct Adgacency Matrix](#org623fac6)
    3.  [(b) Tabluate the Degree Distribution](#orgba24345)
        1.  [Degrees](#orgcc6e7d2)
        2.  [Degree Distribution](#org9023aa4)
    4.  [(c) Calculate the graph density](#orgdd6b030)
    5.  [(d) Calculate the betweenness centrality for each vertex](#org4e13faa)


<a id="org7446cb7"></a>

# 2014 Q1 Graphs

    
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


<a id="orgdb9cb71"></a>

## (a) Construct the adjacency Matrix

> -   The **adjacency matrix** tells you where a row can travel to, from row, to column.
>     -   (atleast in this example, it is common to see it written the other way as well, which is arguably more convenient because it obviates any need to transpose the adjacency matrix in order to get a *probability transition matrix*)


<a id="org623fac6"></a>

## (a) Construct Adgacency Matrix

1.  Write the nodes down vertically as observations
2.  Fill the rows out left to write describing Destinations
    
    <table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
    
    
    <colgroup>
    <col  class="org-left" />
    
    <col  class="org-right" />
    
    <col  class="org-right" />
    
    <col  class="org-right" />
    
    <col  class="org-right" />
    
    <col  class="org-right" />
    
    <col  class="org-right" />
    </colgroup>
    <tbody>
    <tr>
    <td class="org-left">&#xa0;</td>
    <td class="org-right">A</td>
    <td class="org-right">B</td>
    <td class="org-right">C</td>
    <td class="org-right">D</td>
    <td class="org-right">E</td>
    <td class="org-right">F</td>
    </tr>
    
    
    <tr>
    <td class="org-left">A</td>
    <td class="org-right">0</td>
    <td class="org-right">1</td>
    <td class="org-right">1</td>
    <td class="org-right">0</td>
    <td class="org-right">0</td>
    <td class="org-right">0</td>
    </tr>
    
    
    <tr>
    <td class="org-left">B</td>
    <td class="org-right">1</td>
    <td class="org-right">0</td>
    <td class="org-right">0</td>
    <td class="org-right">1</td>
    <td class="org-right">0</td>
    <td class="org-right">0</td>
    </tr>
    
    
    <tr>
    <td class="org-left">C</td>
    <td class="org-right">1</td>
    <td class="org-right">0</td>
    <td class="org-right">0</td>
    <td class="org-right">0</td>
    <td class="org-right">0</td>
    <td class="org-right">1</td>
    </tr>
    
    
    <tr>
    <td class="org-left">D</td>
    <td class="org-right">0</td>
    <td class="org-right">1</td>
    <td class="org-right">0</td>
    <td class="org-right">0</td>
    <td class="org-right">1</td>
    <td class="org-right">0</td>
    </tr>
    
    
    <tr>
    <td class="org-left">E</td>
    <td class="org-right">0</td>
    <td class="org-right">0</td>
    <td class="org-right">0</td>
    <td class="org-right">1</td>
    <td class="org-right">0</td>
    <td class="org-right">1</td>
    </tr>
    
    
    <tr>
    <td class="org-left">F</td>
    <td class="org-right">0</td>
    <td class="org-right">0</td>
    <td class="org-right">1</td>
    <td class="org-right">0</td>
    <td class="org-right">1</td>
    <td class="org-right">0</td>
    </tr>
    </tbody>
    </table>


<a id="orgba24345"></a>

## (b) Tabluate the Degree Distribution


<a id="orgcc6e7d2"></a>

### Degrees

The degree of a vertex is measured as the number of edges that connect to the vertex.


<a id="org9023aa4"></a>

### Degree Distribution

The Degree distribution is a tabulation of the frequency at which a given degree occurs.

In this case all 6 vertices are degree 2 and so:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-right" />

<col  class="org-right" />

<col  class="org-right" />

<col  class="org-right" />

<col  class="org-right" />

<col  class="org-right" />

<col  class="org-right" />
</colgroup>
<tbody>
<tr>
<td class="org-left">Degree</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-right">2</td>
<td class="org-right">3</td>
<td class="org-right">4</td>
<td class="org-right">5</td>
<td class="org-right">6</td>
</tr>


<tr>
<td class="org-left">Frequency</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-right">6</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
</tr>
</tbody>
</table>


<a id="orgdd6b030"></a>

## (c) Calculate the graph density

Graph Density is:

    g-dens = num_edges / possible_edges
           = 2*abs(e) / (abs(v) * (abs(v) - 1) )

So to calculate the graph density:

    g_dens <- function(e,v) {
        2*abs(e) / (abs(v) * (abs(v) - 1))
    }
    g_dens(6, 6)

So in this case the graph density is 0.4


<a id="org4e13faa"></a>

## (d) Calculate the betweenness centrality for each vertex

> To calculate betweenness centrality, you take every pair of the network and count how many times a node can interrupt the shortest paths

The betweenness centrality is the sum of the ratios between:

1.  the number of shortest paths between two vertices
2.  the number of shortest paths between two vertices that passes through the vertex of interest

So first you have to list every possible combination of pairs:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<tbody>
<tr>
<td class="org-left">&#xa0;</td>
<td class="org-left">A</td>
<td class="org-left">B</td>
<td class="org-left">C</td>
<td class="org-left">D</td>
<td class="org-left">E</td>
<td class="org-left">F</td>
</tr>


<tr>
<td class="org-left">A</td>
<td class="org-left">x</td>
<td class="org-left">x</td>
<td class="org-left">x</td>
<td class="org-left">x</td>
<td class="org-left">x</td>
<td class="org-left">x</td>
</tr>


<tr>
<td class="org-left">B</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">x</td>
<td class="org-left">x</td>
<td class="org-left">x</td>
<td class="org-left">x</td>
<td class="org-left">x</td>
</tr>


<tr>
<td class="org-left">C</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">x</td>
<td class="org-left">x</td>
<td class="org-left">x</td>
<td class="org-left">x</td>
</tr>


<tr>
<td class="org-left">D</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">x</td>
<td class="org-left">x</td>
<td class="org-left">x</td>
</tr>


<tr>
<td class="org-left">E</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">x</td>
<td class="org-left">x</td>
</tr>


<tr>
<td class="org-left">F</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">x</td>
</tr>
</tbody>
</table>

Which can be translated as:

    AA, AB, AC, AD, AE, AF
            BC, BD, BE, BF
                CD, CE, CF
                    DE, DF
                        EF

So first write down each pairing as an observation, the features will be the *interupting node*, we write the number of times the shortest path could be interupted by this node.

So for instance with regard to A

-   **AB, AC, &#x2026; AF:** are omitted because they will always contain A and don&rsquo;t contribute to centrality
-   **`BC`:** is interrupted by `A` so 1/1:
    -   1 shortest path (denominator)
    -   1 time A is involved in the shortest path (numerator)
-   **`BD`:** is not interrupted by `A` so 0:
    -   1 shortest path (denominator)
    -   0 times A is involved (numerator)
-   **`BE`:** is not interrupted by `A` so 0:
    -   1 shortest path (denominator)
    -   0 times A is involved (numerator)
-   **`BF`:** is interrupted `A` 1/2 times:
    -   2 shortest paths (denominator)
    -   1 of which is interupted by `A` (denominator)

Our betweenness centrality score is the sum of the columns.

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<tbody>
<tr>
<td class="org-left">&#xa0;</td>
<td class="org-left">A</td>
<td class="org-left">B</td>
<td class="org-left">C</td>
<td class="org-left">D</td>
<td class="org-left">E</td>
<td class="org-left">F</td>
</tr>


<tr>
<td class="org-left">AB</td>
<td class="org-left">x</td>
<td class="org-left">x</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">AC</td>
<td class="org-left">x</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">x</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">AD</td>
<td class="org-left">x</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">x</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">AE</td>
<td class="org-left">x</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">x</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">AF</td>
<td class="org-left">x</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">x</td>
</tr>


<tr>
<td class="org-left">BC</td>
<td class="org-left">1/1</td>
<td class="org-left">x</td>
<td class="org-left">x</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">BD</td>
<td class="org-left">0/1</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">x</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">BE</td>
<td class="org-left">0/1</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">x</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">BF</td>
<td class="org-left">1/2</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">x</td>
</tr>


<tr>
<td class="org-left">CD</td>
<td class="org-left">1/2</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">x</td>
<td class="org-left">x</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">CE</td>
<td class="org-left">0/1</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">x</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">x</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">CF</td>
<td class="org-left">0/1</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">x</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">x</td>
</tr>


<tr>
<td class="org-left">DE</td>
<td class="org-left">0/1</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">x</td>
<td class="org-left">x</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">DF</td>
<td class="org-left">0/1</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">x</td>
<td class="org-left">x</td>
<td class="org-left">x</td>
</tr>


<tr>
<td class="org-left">EF</td>
<td class="org-left">0/1</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">x</td>
</tr>
</tbody>
</table>

No you&rsquo;ll notice I haven&rsquo;t bothered to fill out the whole table, that&rsquo;s because
the centrality of any node in the graph does not change regardless of how the
labels are bijected among the vertices.

So for all Vertices, the between centrality score is 2.

