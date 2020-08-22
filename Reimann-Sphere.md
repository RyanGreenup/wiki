---
title: Reimann Sphere
description: Wikipedia Export of Reimann Sphere
published: true
date: 2020-08-22T13:18:25.058Z
tags: 
editor: markdown
---

![The Riemann sphere can be visualized as the complex number plane
wrapped around a sphere (by some form of [stereographic
projection](stereographic_projection "wikilink") -- details are given
below).](RiemannKugel.svg "The Riemann sphere can be visualized as the complex number plane wrapped around a sphere (by some form of stereographic projection – details are given below).")

In [mathematics](mathematics "wikilink"), the **Riemann sphere**, named
after [Bernhard Riemann](Bernhard_Riemann "wikilink"),[^1] is a
[model](Mathematical_model "wikilink") of the **extended complex
plane**, the [complex plane](complex_plane "wikilink") plus a [point at
infinity](point_at_infinity "wikilink"). This extended plane represents
the **extended complex numbers**, that is, the [complex
numbers](complex_number "wikilink") plus a value ∞ for
[infinity](infinity "wikilink"). With the Riemann model, the point \"∞\"
is near to very large numbers, just as the point \"0\" is near to very
small numbers.

The extended complex numbers are useful in [complex
analysis](complex_analysis "wikilink") because they allow for [division
by zero](division_by_zero "wikilink") in some circumstances, in a way
that makes expressions such as $\tfrac{1}{0}=\infty$
[well-behaved](well-behaved "wikilink"). For example, any [rational
function](rational_function "wikilink") on the complex plane can be
extended to a [holomorphic function](holomorphic_function "wikilink") on
the Riemann sphere, with the [poles](Pole_(complex_analysis) "wikilink")
of the rational function mapping to infinity. More generally, any
[meromorphic function](meromorphic_function "wikilink") can be thought
of as a holomorphic function whose [codomain](codomain "wikilink") is
the Riemann sphere.

In [geometry](geometry "wikilink"), the Riemann sphere is the
prototypical example of a [Riemann surface](Riemann_surface "wikilink"),
and is one of the simplest [complex
manifolds](complex_manifold "wikilink"). In [projective
geometry](projective_geometry "wikilink"), the sphere can be thought of
as the **complex [projective line](projective_line "wikilink")**
**P**^1^(**C**), the [projective space](projective_space "wikilink") of
all [complex lines](complex_line "wikilink") in **C**^2^. As with any
[compact](compact_space "wikilink") Riemann surface, the sphere may also
be viewed as a projective [algebraic curve](algebraic_curve "wikilink"),
making it a fundamental example in [algebraic
geometry](algebraic_geometry "wikilink"). It also finds utility in other
disciplines that depend on analysis and geometry, such as the [Bloch
sphere](Bloch_sphere "wikilink") of [quantum
mechanics](quantum_mechanics "wikilink") and in other [branches of
physics](branches_of_physics "wikilink").

The extended complex plane is also called **closed complex plane**.

Extended complex numbers {#extended_complex_numbers}
------------------------

The **extended complex numbers** consist of the complex numbers **C**
together with ∞. The set of extended complex numbers may be written as
**C** ∪ {∞}, and is often denoted by adding some decoration to the
letter **C**, such as

$$\hat{\mathbb{C}},\quad\overline{\mathbb{C}},\quad\text{or}\quad\mathbb{C}_\infty.$$
Geometrically, the set of extended complex numbers is referred to as the
**Riemann sphere** (or **extended complex plane**).

### Arithmetic operations {#arithmetic_operations}

[Addition](Addition "wikilink") of complex numbers may be extended by
defining, for *z* ∈ **C**,

$$z + \infty = \infty$$

for any complex number *z*, and
[multiplication](multiplication "wikilink") may be defined by

$$z \times \infty = \infty$$

for all nonzero complex numbers *z*, with ∞ × ∞ = ∞. Note that ∞ -- ∞
and 0 × ∞ are left undefined. Unlike the complex numbers, the extended
complex numbers do not form a [field](field_(mathematics) "wikilink"),
since ∞ does not have a [multiplicative
inverse](multiplicative_inverse "wikilink"). Nonetheless, it is
customary to define [division](division_(mathematics) "wikilink") on
**C** ∪ {∞} by

$$\frac{z}{0} = \infty\quad\text{and}\quad \frac{z}{\infty} = 0$$

for all nonzero complex numbers *z*, with `{{sfrac|∞|0}}`{=mediawiki}
= ∞ and `{{sfrac|0|∞}}`{=mediawiki} = 0. The quotients
`{{sfrac|0|0}}`{=mediawiki} and `{{sfrac|∞|∞}}`{=mediawiki} are left
undefined.

### Rational functions {#rational_functions}

Any [rational function](rational_function "wikilink")
`{{nowrap|1=''f''(''z'') = {{sfrac|''g''(''z'')|''h''(''z'')}}}}`{=mediawiki}
(in other words, *f*(*z*) is the ratio of polynomial functions *g*(*z*)
and *h*(*z*) of *z* with complex coefficients, such that *g*(*z*) and
*h*(*z*) have no common factor) can be extended to a [continuous
function](continuous_function "wikilink") on the Riemann sphere.
Specifically, if *z*~0~ is a complex number such that the denominator
*h*(*z*~0~) is zero but the numerator *g*(*z*~0~) is nonzero, then
*f*(*z*~0~) can be defined as ∞. Moreover, *f*(∞) can be defined as the
[limit](Limit_of_a_function "wikilink") of *f*(*z*) as
`{{nowrap|''z'' → ∞}}`{=mediawiki}, which may be finite or infinite.

The set of complex rational functions --- whose mathematical symbol is
**C**(*z*) --- form all possible [holomorphic
functions](holomorphic_function "wikilink") from the Riemann sphere to
itself, when it is viewed as a [Riemann
surface](Riemann_surface "wikilink"), except for the constant function
taking the value ∞ everywhere. The functions of **C**(*z*) form an
algebraic field, known as *the field of rational functions on the
sphere*.

For example, given the function

$$f(z) = \frac{6z^2 + 1}{2z^2 - 50}$$ we may define
`{{nowrap|1=''f''(±5) = ∞}}`{=mediawiki}, since the denominator is zero
at `{{nowrap|1=''z'' = ±5}}`{=mediawiki}, and
`{{nowrap|1=''f''(∞) = 3}}`{=mediawiki} since
`{{nowrap|''f''(''z'') → 3}}`{=mediawiki} as
`{{nowrap|''z'' → ∞}}`{=mediawiki}. Using these definitions, *f* becomes
a continuous function from the Riemann sphere to itself.

As a complex manifold {#as_a_complex_manifold}
---------------------

As a one-dimensional complex manifold, the Riemann sphere can be
described by two charts, both with domain equal to the complex number
plane **C**. Let *ζ* be a complex number in one copy of **C**, and let
*ξ* be a complex number in another copy of **C**. Identify each nonzero
complex number *ζ* of the first **C** with the nonzero complex number
`{{sfrac|1|''ξ''}}`{=mediawiki} of the second **C**. Then the map

$$f(z) = \frac{1}{z}$$

is called the [transition map](transition_map "wikilink") between the
two copies of **C** --- the so-called
[charts](Chart_(topology) "wikilink") --- glueing them together. Since
the transition maps are [holomorphic](holomorphic_function "wikilink"),
they define a complex manifold, called the **Riemann sphere**. As a
complex manifold of 1 complex dimension (i.e., 2 real dimensions), this
is also called a **Riemann surface**.

Intuitively, the transition maps indicate how to glue two planes
together to form the Riemann sphere. The planes are glued in an
\"inside-out\" manner, so that they overlap almost everywhere, with each
plane contributing just one point (its origin) missing from the other
plane. In other words, (almost) every point in the Riemann sphere has
both a *ζ* value and a *ξ* value, and the two values are related by
`{{nowrap|1=''ζ'' = {{sfrac|1|''ξ''}}}}`{=mediawiki}. The point where
`{{nowrap|1=''ξ'' = 0}}`{=mediawiki} should then have *ζ*-value
\"`{{sfrac|1|0}}`{=mediawiki}\"; in this sense, the origin of the
*ξ*-chart plays the role of \"∞\" in the *ζ*-chart. Symmetrically, the
origin of the *ζ*-chart plays the role of ∞ in the *ξ*-chart.

[Topologically](Topology "wikilink"), the resulting space is the
[one-point compactification](Compactification_(mathematics) "wikilink")
of a plane into the sphere. However, the Riemann sphere is not merely a
topological sphere. It is a sphere with a well-defined [complex
structure](Complex_manifold "wikilink"), so that around every point on
the sphere there is a neighborhood that can be
[biholomorphically](Biholomorphism "wikilink") identified with **C**.

On the other hand, the [uniformization
theorem](uniformization_theorem "wikilink"), a central result in the
classification of Riemann surfaces, states that every
[simply-connected](simply-connected "wikilink") Riemann surface is
biholomorphic to the complex plane, the [hyperbolic
plane](Hyperbolic_space "wikilink"), or the Riemann sphere. Of these,
the Riemann sphere is the only one that is a [closed
surface](Closed_manifold "wikilink") (a
[compact](compact_space "wikilink") surface without
[boundary](Manifold_with_boundary "wikilink")). Hence the
two-dimensional sphere admits a unique complex structure turning it into
a one-dimensional complex manifold.

As the complex projective line {#as_the_complex_projective_line}
------------------------------

The Riemann sphere can also be defined as the **complex projective
line**. The points of the complex projective line are [equivalence
classes](equivalence_class "wikilink") established by the following
relation on points from C^2^ \\ {(0,0)}:

:   If for some λ ≠ 0, *w* = λ*u* and *z* = λ*v*, then
    $(w,z) \thicksim (u,v).$

In this case the equivalence class is written \[*w, z*\] using
[projective coordinates](projective_coordinates "wikilink"). Given any
point \[*w, z*\] in the complex projective line, one of *w* and *z* must
be non-zero, say *w* ≠ 0. Then by the equivalence relation,

$$[w, z] \thicksim \left[1, \tfrac{z}{w} \right]$$ which is in a chart
for the Riemann sphere manifold.[^2]

This treatment of the Riemann sphere connects most readily to projective
geometry. For example, any line (or smooth conic) in the [complex
projective plane](complex_projective_plane "wikilink") is biholomorphic
to the complex projective line. It is also convenient for studying the
sphere\'s [automorphisms](automorphism "wikilink"), later in this
article.

As a sphere {#as_a_sphere}
-----------

![Stereographic projection of a complex number *A* onto a point α of the
Riemann
sphere](RiemannSphere.png "Stereographic projection of a complex number A onto a point α of the Riemann sphere"){width="300"}

The Riemann sphere can be visualized as the unit sphere
*x*^2^ + *y*^2^ + *z*^2^ = 1 in the three-dimensional real space
**R**^3^. To this end, consider the [stereographic
projection](stereographic_projection "wikilink") from the unit sphere
minus the point (0, 0, 1) onto the plane *z* = 0, which we identify with
the complex plane by `{{nowrap|1=''ζ'' = ''x'' + ''iy''}}`{=mediawiki}.
In [Cartesian coordinates](Cartesian_coordinates "wikilink")
`{{nowrap|(''x'', ''y'', ''z'')}}`{=mediawiki} and [spherical
coordinates](spherical_coordinates "wikilink")
`{{nowrap|(''θ'', ''φ'')}}`{=mediawiki} on the sphere (with *θ* the
[zenith](zenith "wikilink") and *φ* the [azimuth](azimuth "wikilink")),
the projection is

$$\zeta = \frac{x + i y}{1 - z} = \cot\left(\tfrac{1}{2} \theta\right) \; e^{i \phi}.$$
Similarly, stereographic projection from
`{{nowrap|(0, 0, −1)}}`{=mediawiki} onto the plane
`{{nowrap|1=''z'' = 0}}`{=mediawiki}, identified with another copy of
the complex plane by `{{nowrap|1=''ξ'' = ''x'' − ''iy''}}`{=mediawiki},
is written

$$\xi = \frac{x - i y}{1 + z} = \tan\left(\tfrac{1}{2} \theta\right) \; e^{-i \phi}.$$
In order to cover the unit sphere, one needs the two stereographic
projections: the first will cover the whole sphere except the point
`{{nowrap|(0, 0, 1)}}`{=mediawiki} and the second except the
point `{{nowrap|(0, 0, −1)}}`{=mediawiki}. Hence, one needs two complex
planes, one for each projection, which can be intuitively seen as glued
back-to-back at `{{nowrap|1=''z'' = 0}}`{=mediawiki}. Note that the two
complex planes are identified differently with the plane
`{{nowrap|1=''z'' = 0}}`{=mediawiki}. An
[orientation](Orientation_(mathematics) "wikilink")-reversal is
necessary to maintain consistent orientation on the sphere, and in
particular complex conjugation causes the transition maps to be
holomorphic.

The transition maps between *ζ*-coordinates and *ξ*-coordinates are
obtained by composing one projection with the inverse of the other. They
turn out to be `{{nowrap|1=''ζ'' = {{sfrac|1|''ξ''}}}}`{=mediawiki} and
`{{nowrap|1=''ξ'' = {{sfrac|1|''ζ''}}}}`{=mediawiki}, as described
above. Thus the unit sphere is
[diffeomorphic](Diffeomorphism "wikilink") to the Riemann sphere.

Under this diffeomorphism, the unit circle in the *ζ*-chart, the unit
circle in the *ξ*-chart, and the equator of the unit sphere are all
identified. The unit disk `{{nowrap|{{abs|''ζ''}} < 1}}`{=mediawiki} is
identified with the southern hemisphere
`{{nowrap|''z'' < 0}}`{=mediawiki}, while the unit disk
`{{nowrap|{{abs|''ξ''}} < 1}}`{=mediawiki} is identified with the
northern hemisphere `{{nowrap|''z'' > 0}}`{=mediawiki}.

Metric
------

A Riemann surface does not come equipped with any particular [Riemannian
metric](Riemannian_metric "wikilink"). The Riemann surface\'s conformal
structure does, however, determine a class of metrics: all those whose
subordinate conformal structure is the given one. In more detail: The
complex structure of the Riemann surface does uniquely determine a
metric up to [conformal equivalence](conformal_equivalence "wikilink").
(Two metrics are said to be conformally equivalent if they differ by
multiplication by a positive [smooth
function](smooth_function "wikilink").) Conversely, any metric on an
[oriented surface](oriented_surface "wikilink") uniquely determines a
complex structure, which depends on the metric only up to conformal
equivalence. Complex structures on an oriented surface are therefore in
one-to-one correspondence with conformal classes of metrics on that
surface.

Within a given conformal class, one can use conformal symmetry to find a
representative metric with convenient properties. In particular, there
is always a complete metric with [constant
curvature](constant_curvature "wikilink") in any given conformal class.

In the case of the Riemann sphere, the [Gauss--Bonnet
theorem](Gauss–Bonnet_theorem "wikilink") implies that a
constant-curvature metric must have positive
[curvature](Gaussian_curvature "wikilink") *K*. It follows that the
metric must be [isometric](Isometry_(Riemannian_geometry) "wikilink") to
the sphere of radius `{{sfrac|1|{{sqrt|''K''}}}}`{=mediawiki} in
**R**^3^ via stereographic projection. In the *ζ*-chart on the Riemann
sphere, the metric with `{{nowrap|1=''K'' = 1}}`{=mediawiki} is given by

$$ds^2 = \left(\frac{2}{1+|\zeta|^2}\right)^2\,|d\zeta|^2 = \frac{4}{\left(1 + \zeta \bar \zeta\right)^2}\,d\zeta \,d\bar \zeta.$$

In real coordinates `{{nowrap|1=''ζ'' = ''u'' + ''iv''}}`{=mediawiki},
the formula is

$$ds^2 = \frac{4}{\left(1 + u^2 + v^2\right)^2} \left(du^2 + dv^2\right).$$

Up to a constant factor, this metric agrees with the standard
[Fubini--Study metric](Fubini–Study_metric "wikilink") on complex
projective space (of which the Riemann sphere is an example).

Up to scaling, this is the *only* metric on the sphere whose group of
orientation-preserving isometries is 3-dimensional (and none is more
than 3-dimensional); that group is called [SO(3)](SO(3) "wikilink"). In
this sense, this is by far the most symmetric metric on the sphere. (The
group of all isometries, known as [O(3)](O(3) "wikilink"), is also
3-dimensional, but unlike SO(3) is not a connected space.)

Conversely, let *S* denote the sphere (as an abstract
[smooth](Differentiable_manifold "wikilink") or [topological
manifold](topological_manifold "wikilink")). By the uniformization
theorem there exists a unique complex structure on *S*, up to conformal
equivalence. It follows that any metric on *S* is conformally equivalent
to the [round
metric](Metric_tensor#The_round_metric_on_a_sphere "wikilink"). All such
metrics determine the same conformal geometry. The round metric is
therefore not intrinsic to the Riemann sphere, since \"roundness\" is
not an invariant of conformal geometry. The Riemann sphere is only a
[conformal manifold](conformal_manifold "wikilink"), not a [Riemannian
manifold](Riemannian_manifold "wikilink"). However, if one needs to do
Riemannian geometry on the Riemann sphere, the round metric is a natural
choice (with any fixed radius, though radius = 1 is the simplest and
most common choice). That is because only a round metric on the Riemann
sphere has its isometry group be a 3-dimensional group. (Namely, the
group known as [SO(3)](rotation_group_SO(3) "wikilink"), a continuous
(\"Lie\") group that is topologically the 3-dimensional [projective
space](projective_space "wikilink") **P**^3^.)

Automorphisms
-------------

![A [Möbius transformation](Möbius_transformation "wikilink") acting on
the sphere, and on the plane by [stereographic
projection](stereographic_projection "wikilink")](Mob3d-elip-opp-200.png "fig:A Möbius transformation acting on the sphere, and on the plane by stereographic projection")
`{{Main article|Möbius transformation}}`{=mediawiki}

The study of any mathematical object is aided by an understanding of its
[group](Group_(mathematics) "wikilink") of automorphisms, meaning the
maps from the object to itself that preserve the essential structure of
the object. In the case of the Riemann sphere, an automorphism is an
invertible biholomorphic map from the Riemann sphere to itself. It turns
out that the only such maps are the [Möbius
transformations](Möbius_transformation "wikilink"). These are functions
of the form

$$f(\zeta) = \frac{a \zeta + b}{c \zeta + d},$$ where *a*, *b*, *c*, and
*d* are complex numbers such that
`{{nowrap|''ad'' − ''bc'' ≠ 0}}`{=mediawiki}. Examples of Möbius
transformations include [dilations](Scaling_(geometry) "wikilink"),
[rotations](rotation "wikilink"),
[translations](translation_(mathematics) "wikilink"), and complex
inversion. In fact, any Möbius transformation can be written as a
composition of these.

The Möbius transformations are [homographies](homography "wikilink") on
the complex projective line. In [projective
coordinates](projective_coordinates "wikilink"), the transformation *f*
can be written

$$[\zeta,\ 1] \begin{pmatrix} a & c \\ b & d \end{pmatrix} \ = \ [a\zeta + b,\ c\zeta + d] \ = \ \left[ \tfrac{a\zeta + b}{c\zeta + d},\ 1 \right] \ = \ [f(\zeta),\ 1].$$

Thus the Möbius transformations can be described as
`{{nowrap|2 × 2}}`{=mediawiki} complex matrices with nonzero
[determinant](determinant "wikilink"). Since they act on projective
coordinates, two matrices yield the same Möbius transformation if and
only if they differ by a nonzero factor. The
[group](group_(mathematics) "wikilink") of Möbius transformations is the
[projective linear group](projective_linear_group "wikilink")
`{{nowrap|PGL(2, '''C''')}}`{=mediawiki}.

If one endows the Riemann sphere with the [Fubini--Study
metric](Fubini–Study_metric "wikilink"), then not all Möbius
transformations are isometries; for example, the dilations and
translations are not. The isometries form a proper subgroup of
`{{nowrap|PGL(2, '''C''')}}`{=mediawiki}, namely PSU(2). This subgroup
is isomorphic to the [rotation group
SO(3)](rotation_group_SO(3) "wikilink"), which is the group of
symmetries of the unit sphere in **R**^3^ (which, when restricted to the
sphere, become the isometries of the sphere).

Applications
------------

In complex analysis, a meromorphic function on the complex plane (or on
any Riemann surface, for that matter) is a ratio
`{{sfrac|''f''|''g''}}`{=mediawiki} of two holomorphic functions *f* and
*g*. As a map to the complex numbers, it is undefined wherever *g* is
zero. However, it induces a holomorphic map
`{{nowrap|(''f'', ''g'')}}`{=mediawiki} to the complex projective line
that is well-defined even where `{{nowrap|1=''g'' = 0}}`{=mediawiki}.
This construction is helpful in the study of holomorphic and meromorphic
functions. For example, on a compact Riemann surface there are no
non-constant holomorphic maps to the complex numbers, but holomorphic
maps to the complex projective line are abundant.

The Riemann sphere has many uses in physics. In quantum mechanics,
points on the complex projective line are natural values for
[photon](photon "wikilink")
[polarization](photon_polarization "wikilink") states,
[spin](spin_(physics) "wikilink") states of [massive](mass "wikilink")
[particles](Subatomic_particle "wikilink") of spin
`{{sfrac|1|2}}`{=mediawiki}, and 2-state particles in general (see also
[Quantum bit](Quantum_bit "wikilink") and [Bloch
sphere](Bloch_sphere "wikilink")). The Riemann sphere has been suggested
as a [relativistic](General_relativity "wikilink") model for the
[celestial sphere](celestial_sphere "wikilink").[^3] In [string
theory](string_theory "wikilink"), the
[worldsheets](worldsheet "wikilink") of strings are Riemann surfaces,
and the Riemann sphere, being the simplest Riemann surface, plays a
significant role. It is also important in [twistor
theory](twistor_theory "wikilink").

See also {#see_also}
--------

-   [Conformal geometry](Conformal_geometry "wikilink")
-   [Cross-ratio](Cross-ratio "wikilink")
-   [Dessin d\'enfant](Dessin_d'enfant "wikilink")
-   [Directed infinity](Directed_infinity "wikilink")
-   [Hopf bundle](Hopf_bundle "wikilink")
-   [Möbius plane](Möbius_plane "wikilink")
-   [Projectively extended real
    line](Projectively_extended_real_line "wikilink")

References
----------

```{=mediawiki}
{{More footnotes|date=August 2010}}
```
```{=mediawiki}
{{Page numbers needed|date=September 2010}}
```
```{=mediawiki}
{{reflist}}
```
-   ```{=mediawiki}
    {{Cite book|author1=Brown, James  |author2=Churchill, Ruel |lastauthoramp=yes |title=Complex Variables and Applications|location=New York | publisher=McGraw-Hill|year=1989 |isbn=0-07-010905-2}}
    ```

-   ```{=mediawiki}
    {{Cite book|author1=Griffiths, Phillip  |author2=Harris, Joseph |lastauthoramp=yes |title=Principles of Algebraic Geometry|publisher=John Wiley & Sons|year=1978|isbn=0-471-32792-1}}
    ```

-   ```{=mediawiki}
    {{Cite book|authorlink=Roger Penrose|author=Penrose, Roger|title=The Road to Reality|location=New York|publisher=Knopf|year=2005|isbn=0-679-45443-8|url-access=registration|url=https://archive.org/details/roadtorealitycom00penr_0}}
    ```

-   ```{=mediawiki}
    {{Cite book|author=Rudin, Walter|title=Real and Complex Analysis|location=New York | publisher=McGraw–Hill|year=1987|isbn=0-07-100276-6}}
    ```

External links {#external_links}
--------------

```{=mediawiki}
{{commons category}}
```
-   ```{=mediawiki}
    {{springer|title=Riemann sphere|id=p/r082010}}
    ```

-   [Moebius Transformations
    Revealed](http://www.ima.umn.edu/~arnold/moebius/), by [Douglas N.
    Arnold](Douglas_N._Arnold "wikilink") and Jonathan Rogness (a video
    by two University of Minnesota professors explaining and
    illustrating Möbius transformations using stereographic projection
    from a sphere)

```{=mediawiki}
{{Algebraic curves navbox}}
```
```{=mediawiki}
{{DEFAULTSORT:Riemann Sphere}}
```
[Category:Riemann surfaces](Category:Riemann_surfaces "wikilink")
[Category:Projective geometry](Category:Projective_geometry "wikilink")
[Category:Spheres](Category:Spheres "wikilink") [Category:Bernhard
Riemann](Category:Bernhard_Riemann "wikilink")

[^1]: B. Riemann: Theorie der Abel\'sche Funktionen, J. Math. (Crelle)
    1857; Werke 88-144. The name is due to Neumann C :Vorlesungen über
    Riemanns Theorie der Abelsche Integrale, Leipzig 1865 (Teubner)

[^2]: [William Mark Goldman](William_Goldman_(mathematician) "wikilink")
    (1999) *Complex Hyperbolic Geometry*, page 1, [Clarendon
    Press](Clarendon_Press "wikilink")
    `{{ISBN|0-19-853793-X}}`{=mediawiki}

[^3]: `{{cite book |author=R. Penrose| title=[[The Road to Reality]]| publisher= Vintage books| year=2007 | pages=428–430 (§18.5) | isbn=0-679-77631-1}}`{=mediawiki}
