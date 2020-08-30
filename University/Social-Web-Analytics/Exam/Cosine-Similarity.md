---
title: Cosine-Similarity
description: 
published: true
date: 2020-08-30T11:47:39.861Z
tags: 
editor: undefined
---

# Cosine-Similarity
author: Ryan Greenup
title: SWA Prac Exam

2015 Q2
=======

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
least reduced significantly relative to the amount of clarity provided
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
