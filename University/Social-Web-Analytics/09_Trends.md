---
title: 09_Trends
tags: [Notebooks/Social Web Analytics, R]
created: '2020-06-15T00:23:19.152Z'
modified: '2020-06-16T04:28:17.181Z'
---

# Trends

## Question
> Out of five hundred tweets, 17 mention topic “grand final” in a past period, and 27 in the current. Calculate Twitter's $\chi^2$ score.

The Score Can be calculated by using the identity:

$$\begin{aligned}
\chi^2= \frac{\left( Y- X \right) ^2}{X} +  \frac{\left( X- Y \right) ^2}{N- X} 
\end{aligned}$$

First identify the number of tweets, in this case:

* $N=  500$
* $X =  17$ 
* $Y =  27$


so we have:

$$\begin{aligned}
    \chi^2&= \frac{\left( 27- 17 \right) ^2}{17} +  \frac{\left( 17 -  27 \right) ^2}{500- 17} \\
&= 6.09
\end{aligned}$$

## Chi

This is basically an ordinary chi test, refer to these:

* [Thinking About Data Chi Square](~/Dropbox/Notes/DataSci/ThinkingAboutData/02_Chi_Distrubition.md)

* [Simple Exposure Analysis](~/Dropbox/Notes/DataSci/Social_Web_Analytics/03_Simple_Exposure_Analysis.md) 
* [Applied Stats Notes](~/Dropbox/Studies/PDFNotes/Applied Statistics/AppliedStatsNotes.pdf)

## Simple Linear Regression
This is just ordinary least squared regression See the following:



* [Time Series Analysis / Simple Linear Regression](/home/ryan/Dropbox/Studies/Old/Studies(ONote)/Statistics/Data Science/Env. Info/weekly material/4_Linear Regression (Wk 4)/Notes/Notes.pdf)
  * [Time Series Analysis / Simple Linear Regression (doc x)](/home/ryan/Dropbox/Studies/Old/Studies(ONote)/Statistics/Data Science/Env. Info/weekly material/4_Linear Regression (Wk 4)/Notes/Notes.docx)
* [Time Series Analysis / Multiple Linear Regression](~/Dropbox/Studies/Old/Studies(ONote)/Statistics/Data Science/Env. Info/Course Content/Weekly Material/5_Multiple Linear Regression (Wk 5)/Notes/Wk. 5 - Multipl Regression Notes.Analysis)
  * [I started Converting this](~/Notes/Org/TimeSeries-MultipleLinearRegression.org) 

### Log Transforms
To normalise the residulas, we take a log or root transform before fitting a linear model.


## Moving Averages for Trend Estimation
The idea here is that we are trying to estimate the trend of a Seasonal Time series.

A Time Series can be moddelled as:

$$
\begin{aligned}
Y_t &= T_t +  S_t +  \varepsilon_t
\end{aligned}
$$

That is a combination of the Actual Trend, the seasonal Trend and Noise.


### Seasonal Trend Sums to Zero
A seasonal trend repeats and time is continuous [^1], we expect the seasonality
to be centred about our trend and this means that seasonality should sum to 0
overall.

So consider the sum of all seasonal observations, presume they are evenly spaced and assume that the values have a seasonality of $m$ units of time, then we would have:

$$
\sum^m_{i=1} \left[ S_i \right] = 0  \tag{9.1}
$$

> Think of temperature, say we are modelling the trend over time for rising
> temperatures due to $\mathrm{CO}_2$ emissions, the amount that the temperature
> drops in winter will be the same as it goes up in summer because we define the
> point in between those as the trend in absence of the seasonal effect


[^1]: or atleast we model time to be continuous

### Moving Average
The advantage of taking a moving average is that with the right window the seasonality will cancel to zero, given that $\varepsilon_t \approx 0$, this will give us an estimation for the value of the trend on its own.

> e.g. imagine we took the average temperature of each year, seasons wouldn't matter, winter would cancel out summer and the trend would be exposed.

The Moving Average is given by:

$$\begin{aligned}
z_t &= \frac{1}{k}\sum^j_{i= - j} \left[ Y_{t+i} \right] \qquad \forall j < t\leq\left( n- j \right)
\end{aligned}$$

> Essentially the average of the terms before and the term thereafter

>> If you have an even window though you have to stuff around a little:
>> $$
>> Z_t = \frac{1}{k}\left( \frac{1}{2}Y_{t- j} +  \sum^{j- 1}_{i= - j+  1} \left[ T_{t+  i} \right] +  \frac{1}{2}Y_{t+ j}  \right) \qquad \forall n < t \leq \left( n- j \right) \tag{9.2}
>$$

This means that if the moving average was taken with a window of size $m$ we would have (assuming $m$ is odd):

$$\begin{aligned}
Z_t &= \frac{1}{m} \sum^j_{i= - j} \left[ Y_{t+  i} \right] \\
&= \frac{1}{m}\left( \sum^{j}_{i= - j}\left[ T_{t+ i}  \right] +  \sum^{j}_{i= - j}\left[ S_{t+ i}  \right] +  \sum^{j}_{i= - j}\left[ \varepsilon_{t+ i}  \right]   \right) \\
&= \frac{1}{m}\left( \sum^{j}_{i= - j}\left[ T_{t+ i}  \right] +  0 +  0 \right) \\
&=\frac{1}{m}\sum^{j}_{i= - j}\left[ T_{t+ i}  \right] 
\end{aligned}$$

And so then $Z_t$ is taken as a good *estimate* of $T_t$, because it is essentially the average of the trend values over that moving average.


```r
​```r
library(zoo)
library(tidyverse)
vals  <- c(7, 6, 5, 4, 8, 7, 5, 4, 6, 6, 4, 3)
zoo::rollmean(vals, k = 6)  %>% round(2)

## [1] 6.17 5.83 5.50 5.67 6.00 5.33 4.67
```

So say for exampleple we wanted to compute the trend component for the fifth position in the following sequence and we assume that it repeats every six months: 

$$\begin{aligned}
    \begin{bmatrix} 7& 6 & 5 & 4 & 8 & 7 & 5 & 4 & 6 & 6 & 4 & 3 \end{bmatrix} 
\end{aligned}$$

First we break that 6 in half and take 3 from either side of the fifth term, this makes our window 7 long including the centre term so we halve the end two terms so that the *weights* add up to 7:

$$\begin{aligned}
    \begin{bmatrix}  & |6 & 5 & 4| & 8 & |7 & 5 & 4 |&   &   &   &   \end{bmatrix} 
\end{aligned}$$

Now calculating the rolling average is simply a matter of taking the average:

$$
\frac{\frac{6}{3} +  5 +  4 +  8 +  7 +  5 +  \frac{4}{2}}{6}
$$

If we had to do a cycle of length 7 we would do this:


$$
\frac{6 +  5 +  4 +  8 +  7 +  5 + 4}{7}
$$

## Seasonal Component
So now we have an estimate for the data in absense of the seasonal component, how do we calculate the seasonal component?

Basically just take all the data, subtract the trend and take the average:

$$\begin{aligned}
\tilde{S} = \frac{1}{n_t}\sum_{j}   \left[ Y_{t+  jm} - T_{t+  jm} \right] \qquad \forall t= 1,\ldots,m
\end{aligned}$$

This value however will not sum to 0, so we just do a typical $z= (x - \overline{x})$ to adjust it across:

$$
S_t = \tilde{S}_t - \frac{1}{m} \times \sum^{m}_{j= 1}   \left[ \tilde{S}_j \right] \qquad \forall t = 1, \ldots , m \tag{9.3}
$$

### Problem Question
Given the following data with seasonal cycle of length 4:

$$\begin{aligned}
    \begin{bmatrix} 7 & 6 & 5 & 4 & 8 & 7 & 5 & 4 & 6 & 6 & 4 & 3 \end{bmatrix} 
\end{aligned}$$

with seasonal components:

$$\begin{aligned}
\begin{matrix}
 1.39 & 1.02 & \star & -1.67
\end{matrix}
\end{aligned}$$

Calculate the third seasonal component.

So what we would do is calculate all the trends and then subtract the trend from the value, average that and then subtract the average of those values, but in this case we don't need to because we know that the seasonality must equal zero by (9.3).

$$\begin{aligned}
    \sum^{m}_{1}   S_t = 0  &\implies  x +  1.39 +  1.02 +  (- 1.67) = 0\\
    x& = 1.67 - 1.32 - 1.02\\
    &= -  0.73
\end{aligned}$$
