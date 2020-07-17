---
title: Differential Equations
description: An Export from Wikipedia
published: true
date: 2020-07-17T03:03:05.657Z
tags: 
editor: undefined
---

```{=mediawiki}
{{Calculus/Top Nav|Differential Equations|Partial differential equations}}
```
**Ordinary differential equations** involve equations containing:

-   variables
-   functions
-   their derivatives

and their solutions.

In studying integration, you *already* have considered solutions to very
simple differential equations. For example, when you look to solving

:   $\int f(x) \,dx=g(x)$

for g(x), you are really solving the differential equation

:   $g'(x) = f(x) \,$

Notations and terminology {#notations_and_terminology}
-------------------------

The notations we use for solving differential equations will be crucial
in the ease of solubility for these equations.

This document will be using **three** notations primarily:

-   f\' to denote the derivative of f
-   D *f* to denote the derivative of *f*
-   ${df \over dx}$ to denote the derivative of *f* (for separable
    equations).

### Terminology

Consider the differential equation

:   $3 f^{\prime \prime}(x)+5xf(x)=11$

Since the equation\'s highest derivative is 2, we say that the
differential equation is of *order* 2.

Some simple differential equations {#some_simple_differential_equations}
----------------------------------

A key idea in solving differential equations will be that of
[integration](Calculus/Definite_integral "wikilink").

Let us consider the second order differential equation (remember that a
function acts on a value).

$$f''(x)=2 \,$$

How would we go about solving this? It tells us that on differentiating
twice, we obtain the constant 2 so, if we integrate twice, we should
obtain our result.

Integrating once first of all:

$$\int f''(x) \,dx = \int 2 \,dx$$

$$f'(x)=2x+C_1 \,$$

We have transformed the apparently difficult second order differential
equation into a rather simpler one, viz.

$$f'(x)=2x+C_1 \,$$

This equation tells us that if we differentiate a function once, we get
$2x+C_1$. If we integrate once more, we should find the solution.

$$\int f'(x) \,dx = \int 2x+C_1 \,dx$$

$$f(x)=x^2+C_1x+C_2 \,$$

This is the *solution* to the differential equation. We will get
$f''=2 \,$ for *all* values of $C_1$ and $C_2$.

The values $C_1$ and $C_2$ are related to quantities known as *initial
conditions*.

Why are initial conditions useful? ODEs (ordinary differential
equations) are useful in modeling physical conditions. We may wish to
model a certain physical system which is initially at rest (so one
initial condition may be zero), or wound up to some point (so an initial
condition may be nonzero, say 5 for instance) and we may wish to see how
the system reacts under such an initial condition.

When we solve a system with given initial conditions, we substitute them
after our process of integration.

### Example

When we solved $f''(x)=2 \,$ say we had the initial conditions
$f'(0)=3 \,$ and $f(0)=2 \,$. (Note, initial conditions need not occur
at f(0)).

After we integrate we make substitutions:

$$f'(0)=2(0)+C_1 \,$$

$$3=C_1 \,$$

$$\int f'(x) \,dx = \int 2x+3 \,dx$$

$$f(x)=x^2+3x+C_2 \,$$

$$f(0)=0^2+3(0)+C_2 \,$$

$$2=C_2 \,$$

$$f(x)=x^2+3x+2 \,$$

Without initial conditions, the answer we obtain is known as the
*general solution* or the solution to the *family of equations*. With
them, our solution is known as a *specific solution*.

Basic first order DEs {#basic_first_order_des}
---------------------

In this section we will consider *four* main types of differential
equations:

-   separable
-   homogeneous
-   linear
-   exact

There are many other forms of differential equation, however, and these
will be dealt with in the next section

### Separable equations {#separable_equations}

A *separable* equation is in the form (using dy/dx notation which will
serve us greatly here)

$${dy \over dx} = f(x)/g(y)$$

Previously we have only dealt with simple differential equations with
g(*y*)=1. How do we solve such a separable equation as above?

We group *x* and *dx* terms together, and *y* and *dy* terms together as
well.

$$g(y)\ dy = f(x)\ dx$$ Integrating both sides with respect to y on the
left hand side and x on the right hand side:

$$\int g(y)\,dy=\int f(x)\,dx+C$$

we will obtain the solution.

#### Worked example {#worked_example}

Here is a worked example illustrating the process.

We are asked to solve

$${dy \over dx} = 3x^2y$$

Separating

$${dy \over y} = (3x^2)\,dx$$ Integrating

$$\int {dy \over y} = \int 3x^2\,dx$$

$$\ln{y}=x^3+C \,\!$$

$$y=e^{x^3+C}$$ Letting $k = e^C$ where k is a constant we obtain

$$y=ke^{x^3}$$ which is the general solution.

#### Verification

This step does not need to be part of your work, but if you want to
check your solution, you can verify your answer by differentiation.

We obtained

$$y=ke^{x^3}$$ as the solution to

$${dy \over dx} = 3x^2y$$

Differentiating our solution with respect to x,

$${dy \over dx} = 3kx^2e^{x^3}$$

And since $y=ke^{x^3}$, we can write

$${dy \over dx} = 3x^2y$$ We see that we obtain our original
differential equation, thus our work must be correct.

### Homogeneous equations {#homogeneous_equations}

A *homogeneous* equation is in the form

$${dy \over dx} = f(y/x)$$

This looks difficult as it stands, however we can utilize the
substitution

$$v = {y \over x}$$ so that we are now dealing with F(v) rather than
F(y/x).

Now we can express y in terms of v, as *y*=*xv* and use the product
rule.

The equation above then becomes, using the product rule

$${dy \over dx} = v+x{dv \over dx}$$

Then

$$v+x{dv \over dx} = f(v)$$

$$x{dv \over dx} = f(v)-v$$

$${dv \over dx} = {f(v)-v \over x}$$ which is a separable equation and
can be solved as above.

However let\'s look at a worked equation to see how homogeneous
equations are solved.

#### Worked example {#worked_example_1}

We have the equation

$${dy \over dx} = {y^2 + x^2 \over yx}$$

This does not appear to be immediately separable, but let us expand to
get

$${dy \over dx} = {y^2 \over yx} + {x^2 \over yx}$$

$${dy \over dx} = {x \over y} + {y \over x}$$

Substituting *y*=*xv* which is the same as substituting *v*=*y*/*x*:

$${dy \over dx} = 1/v + v$$

Now

$$v+x{dv \over dx} = 1/v + v$$ Canceling *v* from both sides

$$x{dv \over dx} = 1/v$$ Separating

$$v\, dv = dx/x$$ Integrating both sides

$${1 \over 2}v^2+C= \ln(x) \,$$

$${1 \over 2}\left({y \over x}\right)^2= \ln(x)-C$$

$$y^2 = 2x^2 \ln(x) - 2Cx^2 \,$$

$$y = x\sqrt{2 \ln(x) - 2C}$$

which is our desired solution.

### Linear equations {#linear_equations}

A linear first order differential equation is a differential equation in
the form

$$a(x){dy \over dx} + b(x)y=c(x)$$

Multiplying or dividing this equation by any non-zero function of *x*
makes no difference to its solutions so we could always divide by
*a*(*x*) to make the coefficient of the differential 1, but writing the
equation in this more general form may offer insights.

At first glance, it is not possible to integrate the left hand side, but
there is one special case. If *b* happens to be the differential of *a*
then we can write

$$a(x){dy \over dx} + b(x)y = a(x){dy \over dx} + y{da \over dx}
= {d \over dx}a(x)y$$

and integration is now straightforward.

Since we can freely multiply by any function, lets see if we can use
this freedom to write the left hand side in this special form.

We multiply the entire equation by an arbitrary, *I*(*x*), getting

$$aI{dy \over dx} + bIy=cI$$

then impose the condition

$$\frac{d}{dx}aI = bI$$

If this is satisfied the new left hand side will have the special form.
Note that multiplying *I* by any constant will leave this condition
still satisfied.

Rearranging this condition gives

$$\frac{1}{I}\frac{dI}{dx} = \frac{b-\frac{da}{dx}}{a}$$

We can integrate this to get

$$\ln I(x) = \int \frac{b(z)}{a(z)}dz - \ln a(x) + c \quad
I(x)=\frac{k}{a(x)}e^{\int \frac{b(z)}{a(z)}dz}$$

We can set the constant *k* to be 1, since this makes no difference.

Next we use *I* on the original differential equation, getting

$$e^{\int \frac{b(z)}{a(z)}dz}{dy \over dx} + 
e^{\int \frac{b(z)}{a(z)}dz} \frac{b(x)}{a(x)}y
=e^{\int \frac{b(z)}{a(z)}dz}\frac{c(x)}{a(x)}$$

Because we\'ve chosen *I* to put the left hand side in the special form
we can rewrite this as

$${d \over dx}(ye^{\int \frac{b(z)}{a(z)}dz}) = 
e^{\int \frac{b(z)}{a(z)}dz}\frac{c(x)}{a(x)}$$

Integrating both sides and dividing by $e^I$ we obtain the final result

$$y = e^{-\int \frac{b(z)}{a(z)}dz}
\left(\int e^{\int \frac{b(z)}{a(z)}dz}\frac{c(x)}{a(x)}dx + C\right)$$

We call *I* an *integrating factor*. Similar techniques can be used on
some other calculus problems.

#### Example {#example_1}

Consider

$$\frac{dy}{dx} + y \tan x = 1 \quad y(0)=0$$

First we calculate the integrating factor.

$$I=e^{\int \tan x dx} = e^ {\ln \sec x} = \sec x$$

Multiplying the equation by this gives

$$\sec x \frac{dy}{dx} + y \sec x \tan x = \sec x$$

or

$$\frac{d}{dx} y\sec x = \sec x$$

We can now integrate

$$y = \cos x \int_0^x \sec z \, dz = \cos x \ln (\sec x + \tan x)$$

### Exact equations {#exact_equations}

An exact equation is in the form

:   f(*x*, *y*) d*x* + g(*x*, *y*) d*y* = 0

and, has the property that

:   D~x~ f = D~y~ g

(If the differential equation does not have this property then we can\'t
proceed any further).

As a result of this, if we have an exact equation then there exists a
function h(*x*, *y*) such that

:   D~y~ h = f and D~x~ h = g

So then the solutions are in the form

:   h(*x*, *y*) = c

by using the fact of the total differential. We can find then h(*x*,
*y*) by integration

Basic second and higher order ODE\'s {#basic_second_and_higher_order_odes}
------------------------------------

The generic solution of a *n*^th^ order ODE will contain *n* constants
of integration. To calculate them we need *n* more equations. Most
often, we have either

:   boundary conditions, the values of *y* and its derivatives take for
    two different values of *x*

or

:   initial conditions, the values of *y* and its first *n-1*
    derivatives take for one particular value of *x*.

### Reducible ODE\'s {#reducible_odes}

1\. If the independent variable, *x*, does not occur in the differential
equation then its order can be lowered by one. This will reduce a second
order ODE to first order.

Consider the equation:

$$F\left(y,\frac{dy}{dx},\frac{d^2y}{dx^2}\right)=0$$ Define

$$u=\frac{dy}{dx}$$ Then

$$\frac{d^2y}{dx^2}=\frac{du}{dx}=\frac{du}{dy}\cdot\frac{dy}{dx}=\frac{du}{dy}\cdot u$$
Substitute these two expression into the equation and we get

$$F\left(y,u,\frac{du}{dy}\cdot u\right)$$=0 which is a first order ODE

#### Example {#example_2}

Solve

$$1+2y^2\operatorname{D}^2y=0$$ if at *x*=0,  *y*=D*y*=1

First, we make the substitution, getting

$$1+2y^2 u \frac{du}{dy}=0$$ This is a first order ODE. By rearranging
terms we can separate the variables

$$udu=-\frac{dy}{2y^2}$$ Integrating this gives

$$u^2/2=c+1/2y$$ We know the values of *y* and *u* when *x*=0 so we can
find *c*

$$c=u^2/2-1/2y=1^2/2-1/(2\cdot 1)=1/2-1/2=0$$ Next, we reverse the
substitution

$$\frac{dy}{dx}^2=u^2=\frac{1}{y}$$ and take the square root

$$\frac{dy}{dx}=\pm \frac{1}{\sqrt{y}}$$ To find out which sign of the
square root to keep, we use the initial condition, D*y*=1 at *x*=0,
again, and rule out the negative square root. We now have another
separable first order ODE,

$$\frac{dy}{dx}=\frac{1}{\sqrt{y}}$$ Its solution is

$$\frac{2}{3}y^\frac{3}{2}= x+d$$ Since *y*=1 when *x*=0, *d*=2/3, and

$$y=\left(1 + \frac{3x}{2} \right)^\frac{2}{3}$$

2\. If the dependent variable, *y*, does not occur in the differential
equation then it may also be reduced to a first order equation.

Consider the equation:

$$F\left(x,\frac{dy}{dx},\frac{d^2y}{dx^2}\right)=0$$ Define

$$u=\frac{dy}{dx}$$ Then

$$\frac{d^2y}{dx^2}=\frac{du}{dx}$$ Substitute these two expressions
into the first equation and we get

$$F\left(x,u,\frac{du}{dx}\right)$$=0 which is a first order ODE

### Linear ODEs {#linear_odes}

An ODE of the form

$$\frac{d^ny}{dx^n}+a_1(x)\frac{d^{n-1}y}{dx^{n-1}}+ ... +a_n y=F(x)$$
is called **linear**. Such equations are much simpler to solve than
typical non-linear ODEs. Though only a few special cases can be solved
exactly in terms of elementary functions, there is much that can be said
about the solution of a generic linear ODE. A full account would be
beyond the scope of this book

If *F(x)=0* for all *x* the ODE is called **homogeneous**

Two useful properties of generic linear equations are

1.  Any linear combination of solutions of an homogeneous linear
    equation is also a solution.
2.  If we have a solution of a nonhomogeneous linear equation and we add
    any solution of the corresponding homogenous linear equation we get
    another solution of the nonhomogeneous linear equation

#### Variation of constants {#variation_of_constants}

Suppose we have a linear ODE,

$$\frac{d^ny}{dx^n}+a_1(x)\frac{d^{n-1}y}{dx^{n-1}}+ ... +a_n y=0$$ and
we know one solution, *y=w(x)*

The other solutions can always be written as *y=wz*. This substitution
in the ODE will give us terms involving every differential of *z* upto
the *n*^th^, no higher, so we\'ll end up with an *n*^th^ order linear
ODE for *z*.

We know that *z* is constant is one solution, so the ODE for *z* must
not contain a *z* term, which means it will effectively be an *n-1*^th^
order linear ODE. We will have reduced the order by one.

Lets see how this works in practice.

##### Example {#example_3}

Consider

$$\frac{d^2y}{dx^2}+\frac{2}{x}\frac{dy}{dx}-\frac{6}{x^2}y=0$$

One solution of this is *y=x^2^*, so substitute *y=zx^2^* into this
equation.

$$\left( x^2\frac{d^2z}{dx^2}+4x\frac{dz}{dx}+2z\right) 
+\frac{2}{x} \left( x^2\frac{dz}{dx}+2xz \right) -\frac{6}{x^2}x^2 z=0$$

Rearrange and simplify.

$$x^2 D^2 z + 6xD z=0$$ This is first order for D*z*. We can solve it to
get

$$z=A x^{-5} \quad y=A x^{-3}$$

Since the equation is linear we can add this to any multiple of the
other solution to get the general solution,

$$y=A x^{-3} + B x^2$$

#### Linear homogeneous ODE\'s with constant coefficients {#linear_homogeneous_odes_with_constant_coefficients}

Suppose we have a ODE

$$(D^n+a_1 D^{n-1}+ ... + a_{n-1}D+a_0)y=0$$ we can take an inspired
guess at a solution (motivate this)

$$y=e^{px}$$ For this function D^n^*y*=p^n^y so the ODE becomes

$$(p^n+a_1 p^{n-1}+ ... + a_{n-1}p+a_0)y=0$$

*y=0* is a trivial solution of the ODE so we can discard it. We are then
left with the equation

$$p^n+a_1 p^{n-1}+ ... + a_{n-1}p+a_0)=0$$ This is called the
*characteristic* equation of the ODE.

It can have up to *n* roots, p~1~, p~2~ ... p~n~, each root giving us a
different solution of the ODE.

Because the ODE is linear, we can add all those solution together in any
linear combination to get a general solution

$$y=A_1 e^{p_1 x} +A_2 e^{p_2 x} + ... + A_n e^{p_n x}$$

To see how this works in practice we will look at the second order case.
Solving equations like this of higher order uses exactly the same
principles; only the algebra is more complex.

##### Second order {#second_order}

If the ODE is second order,

$$D^2 y + bDy+cy=0$$ then the characteristic equation is a quadratic,

$$p^2+bp+c=0$$ with roots

$$p_{\pm}=\frac{-b \pm \sqrt{b^2-4c}}{2}$$

What these roots are like depends on the sign of *b*^2^-4*c*, so we have
three cases to consider.

*1) b^2^ \> 4c*

In this case we have two different real roots, so we can write down the
solution straight away.

$$y=A_{+}e^{p_{+}}+A_{-}e^{p_{-}}$$

*2) b^2^ \< 4c*

In this case, both roots are imaginary. We could just put them directly
in the formula, but if we are interested in real solutions it is more
useful to write them another way.

Defining k^2^=4c-b^2^, then the solution is

$$y=A_{+}e^{ikx-\frac{bx}{2}}+A_{-}e^{-ikx-\frac{bx}{2}}$$

For this to be real, the *A*\'s must be complex conjugates

$$A_{\pm}=A e^{\pm ia}$$

Make this substitution and we can write,

$$y=A e^{-bx/2}\cos (kx+a)$$

If *b* is positive, this is a damped oscillation.

*3) b^2^ = 4c*

In this case the characteristic equation only gives us one root,
*p=-b/2*. We must use another method to find the other solution.

We\'ll use the method of variation of constants. The ODE we need to
solve is,

$$D^2 y -2pDy+p^2y=0$$ rewriting *b* and *c* in terms of the root. From
the characteristic equation we know one solution is $y=e^{px}$ so we
make the substitution $y=ze^{px}$, giving

$$(e^{px}D^2z+2pe^{px}Dz+p^2e^{px}z)-2p(e^{px}Dz+pe^{px}z)+p^2e^{px}z=0$$
This simplifies to D^2^*z*=0, which is easily solved. We get

$$z=Ax+B \quad y=(Ax+B)e^{px}$$ so the second solution is the first
multiplied by *x*.

Higher order linear constant coefficient ODE\'s behave similarly: an
exponential for every real root of the characteristic and a exponent
multiplied by a trig factor for every complex conjugate pair, both being
multiplied by a polynomial if the root is repeated.

E.g., if the characteristic equation factors to

$$(p-1)^4(p-3)(p^2+1)^2=0$$ the general solution of the ODE will be

$$y=(A+Bx+Cx^2+Dx^3)e^x + Ee^{3x}+ F \cos (x+a) +Gx \cos(x+b)$$

The most difficult part is finding the roots of the characteristic
equation.

#### Linear nonhomogeneous ODEs with constant coefficients {#linear_nonhomogeneous_odes_with_constant_coefficients}

First, let\'s consider the ODE

$$Dy-y=x$$ a nonhomogeneous first order ODE which we know how to solve.

Using the integrating factor *e^-x^* we find

$$y=c e^{-x} +1 -x$$

This is the sum of a solution of the corresponding homogeneous equation,
and a polynomial.

Nonhomogeneous ODE\'s of higher order behave similarly.

If we have a single solution, *y~p~* of the nonhomogeneous ODE, called a
*particular* solution,

$$(D^n+a_1 D^{n-1} + \cdots + a_n)y=F(x)$$ then the general solution is
*y=y~p~+y~h~*, where *y~h~* is the general solution of the homogeneous
ODE.

Find *y~p~* for an arbitrary *F(x)* requires methods beyond the scope of
this chapter, but there are some special cases where finding *y~p~* is
straightforward.

Remember that in the first order problem *y~p~* for a polynomial *F(x)*
was itself a polynomial of the same order. We can extend this to higher
orders.

*Example:*

$$D^2y+y=x^3-x+1$$ Consider a particular solution

$$y_p=b_0+b_1 x+b_2 x^2 + x^3$$ Substitute for *y* and collect
coefficients

$$x^3 + b_2 x^2 +(6+b_1)x +(2b_2+b_0)=x^3-x+1$$ So *b~2~=0*, *b~1~=-7*,
*b~0~=1*, and the general solution is

$$y=a \sin x + b \cos x + 1 -7x + x^3$$

This works because all the derivatives of a polynomial are themselves
polynomials.

Two other special cases are

$$F(x)=P_n e^{kx} \quad y_p(x)=Q_n e^{kx}$$

$$F(x)=A_n \sin kx +B_n \cos kx \quad 
y_p(x)=P_n \sin kx +Q_n \cos kx$$ where *P~n~*,*Q~n~*,*A~n~*, and *B~n~*
are all polynomials of degree *n*.

Making these substitutions will give a set of simultaneous linear
equations for the coefficients of the polynomials.

```{=mediawiki}
{{Calculus/TOC}}
```
```{=mediawiki}
{{BookCat}}
```
