---
title: Nearest-Neighbour
description: 
published: true
date: 2020-08-30T11:47:42.045Z
tags: 
editor: undefined
---

# Nearest-Neighbour


author: Ryan Greenup
title: Practice Exam 05 PCA and MDS Visualisation

K Nearest Neighbours, 2015, Q8
==============================

(a)
---

The smallest distance for 5 is:

-   5-2 with a distance of:
    -   0.1168

This means the nearest neighbour is positive and so 5 is classified as
positive

-   \\\#6
    -   Is closest to 4 which is Negative
        -   Concluse 6 is negative
-   \\\#7
    -   Is closest to 3 which is positive
        -   Conclude 6 is positive
-   \\\#8
    -   Is closest to 1 which is positive
        -   Conclude 6 is positive

(b) use k = 3
-------------

-   \\\#5
    -   Is closest to 1,2,3 which is PPP
        -   Concluse 6 is Positive
-   \\\#6
    -   Is closest to 4,3,1 which is NPP
        -   Concluse 6 is Positive
-   \\\#7
    -   Is closest to 3,2,1 which is PPP
        -   Conclude 6 is positive
-   \\\#8
    -   Is closest to 1,2,3 which is PPP
        -   Conclude 6 is positive

(c) ROC Curve
-------------

The ROC Curve is the plot of the TPR \~ FPR (i.e. the sensitivity on the
y-axis and the fall out (which 1-tpr)).

so our performance was:

|       |     |     |
|-------|-----|-----|
|       | k=1 | k=3 |
| \#\\5 | FP  | FP  |
| \#\\6 | TN  | FP  |
| \#\\7 | TP  | TP  |
| \#\\8 | FP  | FP  |

So the FPR is FP/N which is:

-   k=1
    -   TPR = TP/P = 1/1
    -   FPR = FP/N = 2/3
        -   Remember that a FP is really an N
-   k = 2
    -   TPR = TP/P = 1/1
    -   FPR = FP/N = 3/3

So we would plot:

k = 1
:   (2/3, 1)

k = 3
:   (3/3, 1) = (1,1)

(d) ROC
-------

k = 1 is higher on a ROC curve so that is better, k = 3 is on the line
so as good as chance

