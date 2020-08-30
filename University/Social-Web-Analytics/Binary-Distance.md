---
title: Binary-Distance
description: 
published: true
date: 2020-08-30T11:47:35.109Z
tags: 
editor: undefined
---

# Binary-Distance
author: Ryan Greenup
title: Scratch Buffer 05 PCA and MDS Visualisation

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

