---
title: Confidence Intervals
description: 
published: true
date: 2020-05-31T03:29:08.624Z
tags: 
---

# The Confidence Interval is not the probability
---
$\Im$nline Math is $\Re$endered by $\mathcal{D}$efault. [^1]

> [introdatasci Notes pdf](/introdatasci.pdf)

[^1]: See the setting [here](http://121.210.19.69:81/a/rendering)

> adapted from:
>
> 
>   
>
> [PDF Version](Attachments/Thinking_About_Data/ConfIntNotes.pdf)

I assume that the motivation for this question is that most statistics
books emphasize the fact that, once you have taken a sample and
constructed the confidence interval (CI), there is no longer any
"randomness" left in a CI statement (except for the Bayesian point of
view which thinks of $\mu$ as being a random variable).

That is, when reporting a CI: "I am 95% confident that the mean is
between 25.1 and 32.6" is correct. "There is a 95% probability that the
mean is between 25.1 and 32.6" is WRONG. Either μ is in that interval or
not; there is no probability associated with it.

### The Reasoning

Suppose that somewhere on the wall is an "invisible bullseye" --- a
special point (call it " μ ") which only I can see. I'm going to throw a
dart at μ . Based on long observation, you know that when I throw a dart
at something, 95% of the time, my dart will hit within 6 inches of what
I was aiming at. (The other 5% of the time, I miss by more than 6
inches.) When you see where that dart lands, you will draw a circle
around it with a radius of 6 inches.

It is correct to say:

> The probability that μ will be in that circle is 95%.

The reason that is correct is, I have not yet thrown the dart, so the
location of the circle is random, and in 95% of repetitions of this
dart-throwing, circle-drawing routine, μ will be in the resulting
circle. Now if I actually take aim, throw my dart, and it hits ...

$$
\text{right here }\implies  \cdot
$$

It is no longer correct to talk about probabilities. You can be pretty
sure that μ is within that circle. To be specific, "pretty sure" = "95%
confident." But you cannot say that the probability that μ is in that
circle is 95%, because μ is not random.This throw might have been one of
the 5% of throws that miss μ by more than 6 inches.

Let's assume we want a 95% CI for μ from a normal population with a
known standard deviation σ , so the margin of error is:

$$
M=1.96\frac\sigma{\sqrt n}
$$

Then $\overline{X}$ is the "dart" we are throwing at μ.

Before you take the sample and compute the mean, you have:

$$
P(\overline
X-M<\mu<\overline X+M)=95\%\tag*{}
$$

This is correct because $\overline X$ is a random variable. However,
once you compute the mean $\overline x$ (lowercase x meaning it is now
just a number, not a random quantity), the inequality:

$$
\overline x-M<\mu<\overline x+M
$$

is either true or false; the "dart" has landed at $\overline x$ , and we
don't know if this was one of the throws that is within M of μ.

This was converted from =org= to =md= using =pandoc -t gfm= at time: 
2020-05-10T06-52-15

