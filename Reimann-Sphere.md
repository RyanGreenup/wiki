---
title: Reimann Sphere
description: Wikipedia Export of Reimann Sphere
published: true
date: 2020-08-30T23:12:40.707Z
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



# Org Mode Export


# Table of Contents

<a id="org9a88457"></a>

# Spacemacs is slow test

If you do decide to switch to *Doom* [Read the Section Below.](#org9382eb8)


<a id="orgd1ee52e"></a>

## Current Speed up workflow

1.  Put everything in memory
    
        vmtouch -vt ~/.emacs.d/
        vmtouch -vt ~/Notes
2.  load all agenda files as buffers.
    
        (defun open-all-org-agenda-files ()
          (interactive) (let (
            (files (org-agenda-files))) 
              (mapcar (lambda (x) (find-file x)) files)))
        (open-all-org-agenda-files)


<a id="org8db8a0f"></a>

## Other tips

So if this does become a deal breaker switch to *Doom* and fix the following

-   map `Spc Spc` to `Helm-M-x`
-   Figure out how to fold source blocks
-   Map / install Helm-Rifle to keybindings
-   Often when `helm-org-rifle` stops before dispatching
    it is generating LaTeX fragments .
    So don&rsquo;t delete the fragments and tolerate them until
    you can actually figure out how to fix them.
    (so `rm ./ltximg/*` is bad).
    -   Just for a note `, T e` to preview pretty symbols
        is quite good.


<a id="org42c766f"></a>

## Throw it in RAM (alksdjf)

OK so I&rsquo;m not sure if it&rsquo;s my imagination or not, but throwing emacs in ram
seems to make it feel smoother, regardless, emacs and all my org notes are 2.5 %
of my total system memory and this is like my main tool so I don&rsquo;t see why I
wouldn&rsquo;t use memory I paid so much for.

I got this hint from [this blog](http://blog.binchen.org/posts/emacs-speed-up-1000.html) and the idea is to use [vmtouch](https://github.com/hoytech/vmtouch) to load everything
into memory, so at startup, have the following run:

    # -v is verbose
    # -t is *T*ouch into memory
    # How much is currently in memory?
    vmtouch ~/.emacs.d/
    # Put it in memory
    vmtouch -vt ~/.emacs.d/ 
    vmtouch -vt ~/Notes/Org
    
    # Now how much is in memory??
    vmtouch ~/.emacs.d

make sure that you throw it into an


<a id="org279de53"></a>

## Potential Fixes

1.  Use new frames when opening a document simultaneously
2.  Use a standalone frame for a given document
    1.  Especially long documents
3.  Just Restart it
    1.  `killall emacs`, `systemctl --user stop emacs`
4.  Delete the directory and reinstall it.
    1.  This sometimes makes a whopping! difference for me
        1.  But I have to do it far to regularly on Spacemacs and it makes me
            want to switch to doom for good.


<a id="org9382eb8"></a>

# Doom Config


<a id="org3bc6981"></a>

## Transient state

Spacemacs has an awesome transient state, let&rsquo;s implement that in Doom for the agenda.

Refer to [the manual](https://magit.vc/manual/transient.html) following this comment from discord:

> @Eisenvig#4862 I have 0 experience with `transient.el`, but from what I
> understand, you need to gather those key bindings together by your own (using
> help tools like `which-key-show-top-level` or looking at config files where they
> are defined.) It is not done automatically like `which-key` does. There [is
> manual for transient](https://magit.vc/manual/transient.html) and in #protips is example of how to use it. Sory I can&rsquo;t
> be more help right now. @AloisJanicek#3492


<a id="org8850b7f"></a>

## Evil Bindings

Some things, for example `magit`, don&rsquo;t work properly because the keybindings
are overwritten by evil, press `C-z` to disable evil to use them.


<a id="org00bd1ec"></a>

## Differences

Links are autosuggested when hitting `C-x C-f` in insert mode just like in
*Vim*, in normal mode this does the ordinary `find-files`.

`, D/s/d` bindings are gone and are now `C-c C-x C-d` and `SPC m s/d`
respectively, this is alright because `,` is `evil-snipe` which is quite handy

You might want to consider adding doom to your `~/.bashrc` / `~/.zshrc` / `~/.config/fish/config.fish`.

-   Install Outshine as shown in sectino [16.1](#org61d254b)

Use `spc spc` to open new files and then `C-o j` to open that in a vertical split.

Helm is `C-z` to delete bookmarks etc, ivy is `C-o`

In ***R*** press `ESC S-k SPC` and you&rsquo;ll get the help docs up which is nice

The `counsel` package uses `M-x M-p` for the last search, so use that instead of using `helm-swoop`


<a id="org1e71fa4"></a>

# Code Folding

in vim to fold code you use the following syntax:

    ## vim:fdm=expr:fdl=0
    ## vim:fde=getline(v\:lnum)=~'^##'?'>'.(matchend(getline(v\:lnum),'##*')-2)\:'='


<a id="org414e18d"></a>

# Source Code Blocks

There&rsquo;s a lot you can do with these, basically the two things you&rsquo;ll want to do are:

1.  [Disable evaluation of blocks on export](https://orgmode.org/manual/Using-Header-Arguments.html)
    1.  For the Whole File
        
            #+PROPERTY: header-args:R  :session *R*
            #+PROPERTY: header-args    :results silent
    2.  For only that headline
        
            * sample header
            :PROPERTIES:
            :header-args:    :cache yes
            :END:
    3.  For only that Code Block test
        
            #+NAME: factorial
            #+BEGIN_SRC haskell :results silent :exports code :var n=0
            fac 0 = 1
            fac n = n * fac (n-1)

2.  [Set System Wide Settings](https://orgmode.org/manual/Using-Header-Arguments.html)
3.  [Change what&rsquo;s exported](https://orgmode.org/manual/Exporting-Code-Blocks.html)


<a id="orgf486c9a"></a>

# Relative Links in Markdown

-   `SPC f F` will search for a file under the current
    directory.

-   `C-o x` from ivy will open it with `xdg-open=/=open`.
-   `C-o P` will insert its absolute path into the current buffer.
    
    This will add `C-o y` to yank the path to clipboard
    
        (after! ivy
          (ivy-add-actions
           'counsel-find-file
           '(("y" (lambda (path) (with-ivy-window (kill-new (expand-file-name path default-directory))))
              "yank file to clipboard"))))


<a id="org88813f5"></a>

# Emacs Application Framework

<a id="org765e116"></a>


<a id="org9b6de68"></a>

## Install the dependencies

    python3 -m pip install PyQt5 pyqtwebengine qrcode feedparser  wheel pyinotify markdown fitz
    sudo apt install nodejs aria2 libreoffice filebrowser
    ## This one won't install :shrug:
    python3 -m pip install dbus


<a id="org133f7d5"></a>

# To install it

    cd ~/.emacs.d/site-lisp
    git clone https://github.com/manateelazycat/emacs-application-framework.git --depth=1


<a id="org5c439da"></a>

# DONE Making a Schedule in Emacs

I think just make a couple todo items, add them to the agenda and give them times?
should I learn more formally or work on it as I go along?
Maybe both, play with it for a few days then read the manual on spacemacs and org-mode.org


<a id="org8b4a086"></a>

## TODO Is there a way to get a better to do list?

Like by which I mean when I hit `C-c a t` the list I get is awfully unorganised,
Can I get something that&rsquo;s nested or am I better off using the agenda or what?

Or maybe I&rsquo;m supposed to use sparse trees?


<a id="org9fcb104"></a>

# DONE Seperate out LaTeX template components

Actually, no, just set up LaTeX folding in *Emacs* and make
 nice pretty templatex, because, when you need to use a template in `org-mode`
it&rsquo;s nice being able to call a single package and a package can&rsquo;t call relative
 directories.

Well actually I&rsquo;m supposed to be able to set up relative directories with STY files.


<a id="orgbb62da6"></a>

# DONE How do I have text flow across windows?

The appropriate width of text is taken to be 50 characters ([“Choose a Comfortable Measure | the Elements of Typographic Style Applied to the Web,” n.d.](#org464d161)),
however some research has shown limited difference between 35-95 ([Chaparro and Shaikh, n.d.](#orgcfe9aa9)).

There is some evidence to suggest a two column full justified layout may be
better for reading digital material ([Munro’s, n.d.](#org336f229)) and research shows that 8 cm
(roughly two columns) text width is more readable in print ([Tinker and Paterson, n.d.](#org5520ca3)), it also
stands to reason that this would give me the opportunity to use smaller margins,
perhaps this is something I should put in my default LaTeX templates?

The preferred font size in digital media tends to be taken as quite large at 16
points ([Chen, Others, and 1996](#orgfb56fd3)),

And there is a general, albeit slight tendency to prefer Sans Serif *Verdana*
font in digital print ([Ali et al. 2013](#orga71e7b0); [Hojjati and Muniandy, n.d.](#org59efe2b))

Regardless, for code, the *Tidyverse* style guide sets a limit of 80 characters
(NO<sub>ITEM</sub><sub>DATA</sub>:Wic2019)   and for that reason I need to set up columns that flow in emacs, like
`follow-mode`, but, without the horrendous lag.

I figured this out, it wasn&rsquo;t the =follow-mode per se, it was:

1.  use Spacemacs base
2.  Clear out Crap from `~/.emacs.d/init.el`
    
    (NO<sub>ITEM</sub><sub>DATA</sub>:Wor1939b)


<a id="org5f53cbf"></a>

# DONE How do I use LaTeX  snippets     :Snippets:

-   Is there anything built into spacemacs?
    -   there is `yasnippets` but it&rsquo;s going to be a bit of work to implement it
-   Is it close enough to what I&rsquo;ve been using?
    -   it&rsquo;s not but it sounds like the tex mode might be
-   should I just jump back to vim when necessary?
    -   for now yes, but maybe long-term something could be implemented.
    -   for live tex preview you can always open a new vim-buffer with an md extension and then use `<leader>-lv` to watch the TeX form as md while you write it and then paste that back into the `.org` file.

Ok so I could not get company snippets or electric/auto snippets to work
what did work though was using `helm-yas` (`SPC i s`), that&rsquo;s definitely the way to go


<a id="orgb5dd92a"></a>

## Official Snippets

You&rsquo;re probably better off using a package of official snippets to:

1.  save time
2.  stay on a sound platform


<a id="org1abaec2"></a>

## DONE Example LaTeX


<a id="org3a0c193"></a>

### previewing latex

Right, let&rsquo;s take a math problem, in this case I&rsquo;ll use something from *Mathematical Modelling*:

[According to the manual,](https://orgmode.org/manual/Previewing-LaTeX-fragments.html) in order to change the defaults of the image preview, use `M-x customize RET org-format-latex-options`:

-   set foreground to &rsquo;auto&rsquo;
    -   this is single `'`
-   set background to &ldquo;Transparent&rdquo;
    -   this is double `"` because it&rsquo;s expecting a `stringp` [argument](https://emacs.stackexchange.com/questions/22607/background-color-of-latex-fragments-in-org-mode)
-   in order to reset the images use rm `./ltximg/*`
    -   be careful, I deleted everything by putting `*` in the wrong place, don&rsquo;t do that.
    -   Generally this a bad idea, don&rsquo;t do this it slows everything down, instead, make a
        transperant preview with like a vivid blue/green/red color to it, that way it will be
        visible on both.

there appears to be a bug with this however and the foreground colour can only be black, which can&rsquo;t be seen on a black background.

Instead you need to change the variable `org-preview-latex-default-process`

      ; Either this
        (setq org-preview-latex-default-process `dvisvgm)
    ; Or this but not not Both?
        (setq org-preview-latex-default-process `dvipng)

The idea is now that the option in `org-format-latex-options` will be respected for the foreground colour

and then the settings should be such that the foreground and bacground are both set to `default`.

\[
math 4x
\]

\[\begin{aligned}
  \frac{1}{x^2} \times \left[2x \cdot   \frac{\operatorname{d}y
  }{\operatorname{d} x} + x^2 \frac{\operatorname{d} }{\operatorname{d}
x}\left( \frac{\operatorname{d}y }{\operatorname{d} x}  \right) \right]
\end{aligned}\]

This[ answer](https://emacs.stackexchange.com/a/44693) uses xcolor and dvipng to get around it but the svg solution works to.

Now this is also a problem with AuCTeX which doesn&rsquo;t have the luxury of using `dvisvgm` and only works with `dvipng`, so this needs to be sorted out.

by using `customize-variable` to inspect `preview-pdf-adjust-color-method` (which I was linked to by `preview-transparent-color` because they are both in the `preview-apperance` group in the[ Auctex manual](https://www.gnu.org/software/auctex/manual/preview-latex.html#Simple-customization)) it was suggested that I need to be using the next version of ghostscript which jumped from 9.27 to 9.50, Ubuntu is still on 9.50, so I&rsquo;ve installed, from source, 9.50, the default in ubunu is 9.26 located at `/usr/bin/ghostscript`, the newer one, that I compiled from source is located at `/usr/loca/bin/gs` so I moved the old one to `ghostscript.bak` and symlinked the new one in place.

After that AucTeX started working, but I couldn&rsquo;t get dvipng to work for org mode so It&rsquo;s necessary to use dvisvgm for org-mode, as for tikz, you need to be aware that the colours are user defined, so you might want to define the colours like so: `\begin{tikzpicture}[domain = 0:10, scale = (2/3), draw = white, text = white]`

1.  imagemagick failure

    I was getting the error:
    
        File mode specification error: (error File "/tmp/orgtex9SIJrf.png" wasn’t produced.  Please adjust ‘imagemagick’ part of ‘org-preview-latex-process-alist’.)
    
    in order to fix it I needed to:
    
    1.  `sudo vim /etc/ImageMagick-6/policy.xml`
    2.  Change the line `<policy domain`&ldquo;coder&rdquo; rights=&ldquo;none&rdquo; pattern=&ldquo;PDF&rdquo; />= to: `<policy domain="coder" rights="read|write" pattern="PDF" />`
    
    I also found that after fixing this I no longer needed to use `dvisvgm` and so I just commented it out of the init file.
    
    1.  LaTeX Header is important!     :LaTeX:Org:
    
        So I didn&rsquo;t understand at first how this all worked but now I do, the
        process is pretty basic really, when you put your cursor on `$ math $` and
        hit = C-c C-x C-l= :
        
        1.  The contents captured is taken to a seperate buffer
        2.  that buffer is exported in the expected way to LaTeX
            1.  This means that the typical `\usepcackage{}` crap 
                is put in there, but also your header as well.
            2.  so if your LaTeX style doesn&rsquo;t exist or points
                to a bad reference even inline images of math 
                won&rsquo;t render.
        3.  The LaTeX `dvi` / `pdf` is then converted to a 
            `png` or `svg` using `imagemagick` or `dvisvgm`
        
        so if you&rsquo;re having trouble, first comment out the LaTeX header and 
        then retry because that could very well be the issue.
        
        If that does fix it, it&rsquo;s probably a `references.bib` that&rsquo;s become 
        erroneous, that&rsquo;s what it always is.
        
        Also important is that you use a `BibTeX` not a `BibLaTeX` export from
        *Zotero*, there is no support for `@online` in `org-ref` so make sure
        `BibTeX` specifies them as `@misc`


<a id="org2159d3c"></a>

### DONE Using the snippets

Take the equation and open it in `org-edit-special` mode with `C-c '` / `, '` :

\begin{align}
  \frac{1}{x^2} \times \left[2x \cdot   \frac{\operatorname{d}y
  }{\operatorname{d} x} + x^2 \frac{\operatorname{d} }{\operatorname{d}
x}\left( \frac{\operatorname{d}y }{\operatorname{d} x}  \right) \right] \\
x = \frac{- b \pm \sqrt{b^2 - 4ac} }{2a}
\end{align}

\begin{tikzpicture}[domain=0:10, scale = 0.75]
  \draw [->, thick] (0, -2) -- (0, 10) node[right] {$\frac{\operatorname{d}x }{\operatorname{d} t}$} node[left] at (0,6.5) {$\left( \frac{1}{4}N^2+ \frac{1}{2}N \right)k$};
  \draw [dotted] (0,6.3) -- (9, 6.3);
  \draw [dotted] (3.5,0) -- (3.5, 6.3);
  \draw node[below] at (3.5,0) {$\frac{1}{2} N$};
  \draw [->, thick] (-2, 0) -- (10, 0) node[right] {$x$};
  \clip (-1,-1) rectangle (10,10);
  \draw[black, line width = 0.50mm]   plot[smooth,domain=0:10] (\x, {4-(\x-2)^2 + 3*(\x-2)});
  % \draw[black, line width = 0.50mm]   plot[smooth,domain=-2:0] (\x, {4+\x^2});
\end{tikzpicture}

Then just hit `SPC i s` to engage `Spacemacs/helm-yas`.

It&rsquo;s honestly easier to just hit `C-c v` and then use the vim live preview, it
will still work despite the document being an `org-mode` file.

honestly, if you need fast vim with a preview, and/or tikz, this might be the simplest way:

1.  open a new destkop in i3/cinnamon
2.  open a terminal and create a new directory
3.  Either use vim to create a `temp.tex` and have the default template be pulled in (or use the older `texnote` command)
4.  edit in that window leveraging the almost live preview offered by vimtex
5.  use zf to fold and `<Spc> y` to copy relevant things to the clipboard.
6.  paste it back into emacs
    -   if you get better with i3 you could probably have a really elegant way to do this on one desktop, may `mod a` a couple times and `mod enter` works pretty well tbh.

I don&rsquo;t see any much need to re invent the wheel with snippets when vim works well and I can&rsquo;t sync them between so I&rsquo;m just going to leave it.


<a id="org7af43e7"></a>

## DONE Fix `outline-minor-mode` hook for LaTeX


<a id="org8d05be4"></a>

## Preview LaTeX

LaTeX may be previewed from the `LaTeX-mode` by using `SPC m v` or `, m v`, in
order to change the default to `zathura` change the variable
`TeX-view-program-selection`

You definitely want to use `texfrag-mode` in markdown and org mode, then you can
preview the entire document with `C-p C-p C-d`, the advantage to this is that:

-   The previews will generate quicker
-   The previews will regenerate each time making theme changes painless

-   **WARNING:** This will not work with themes prefixed with `doom-`, the
    background won&rsquo;t be transparent, for example try it with the `wombat` and
    `doom-dracula` themes.
    -   Just use Dracula from MELPA though and you&rsquo;re fine.
        -   Leuven and Leuven Dark are quite nice as well


<a id="org280f06b"></a>

# DONE How to troubleshoot lag by looking at cpu times?


<a id="org5925487"></a>

## Spc m is undefined     :Workflow:

Look this happens all the time, I don&rsquo;t think it&rsquo;s really an issue though,
just make sure to execute `M-x toggle-org-custom-inline-style` and then 
just export dispatch with `C-c C-e`


<a id="org873c9d6"></a>

# DONE Emacs for notes

<span class="timestamp-wrapper"><span class="timestamp">&lt;2019-11-13 Wed&gt;</span></span>
You can add a todo tag by calling `org-insert-todo-heading` which is mapped to
`M-Shift-RET`, in *SpaceMacs* it appears to be `SPC m :`

Consider adding extra states to the for todo <sup><a id="fnr.1" class="footref" href="#fn.1">1</a></sup> something like:

    #+TODO: TODO IN-PROGRESS WAITING DONE


<a id="org891c8a9"></a>

### Using Helm

You should read through the Helm Tutorial, it&rsquo;s really helpful <sup><a id="fnr.2" class="footref" href="#fn.2">2</a></sup> 


<a id="org01be942"></a>

## DONE Images     :diagrams:


<a id="org4c5ec04"></a>

### Images may be inserted as links

Look at the following example:

The documentation implies that `[[ ]]` are required but it seems that the export works fine without that and the inline preview is fine without it as well:

![img](/home/ryan/gitpage/ryangreenup.github.io/AbstractAlgebraNotes/1551604985277.png)

This may be inline previewed with `C-c C-x C-v`


<a id="orgdbad3b5"></a>

### Exporting

The [Metadata and TODO (Including Drawers)](https://lists.gnu.org/archive/html/emacs-orgmode/2008-12/msg00078.html) can be excluded from export.


<a id="org62a23de"></a>

### Resizing Images

Images may be resized by first specifying the following in emacs:

    (setq org-image-actual-width nil)
    (setq org-latex-image-default-width "")

and then using the following syntax:

    #+attr_html: :width 400px
    # good for two column
    #+attr_latex: :width 7cm
    [[./Attachments/Statistics/BellCurve.png]]


<a id="org3eb36c0"></a>

## DONE References     :bibliography:


<a id="org0102318"></a>

### DONE BibTeX mode

this is a major mode to edit `.bib` BibTeX files, to use this you need to enable the `(bibtex)` layer in the `~/.spacemacs` file and then set up a basic config. ([Benner, n.d.](#org3431d91))

This works really well because you can tie the reference to a
PDF on the system (Dropbox or Git should make laptop in sync)
and then when you press enter you can open the pdf, search the
citation, email it etc. all from in Emacs.

Inserting references is really good to because you can just
jump straight to the `.bib` file and/or google scholar.

basically the only way I&rsquo;ve found to change the default bib file
 is to run the following inside the file:

For the moment I&rsquo;ve decided not to do that, just to trial having
 only a single bib file, because it is easy to filter a bib file
 using the BibTeX major mode in Emacs, just use `C-c a` and then
 you can filter it by fields etc, it probably makes more sense just
 to have one single BibTeX and if you get really lost use Zotero or Jabref manage it with tags, tho whole idea of a `.bib` file is it&rsquo;s an index so it might not be worth parting it out (or you could comment sections out if you really wanted to, it&rsquo;s better than hunting for files).

To add a citation in an org file use `SPC m i c` from there you can look
something up with google or whatever or go to the bib file and search for the
keyword from there. From the bib file you can use ISBN or DOI to autogenerate an
entry also there is the `org-ref-url-html-to-bibtex` function, which performs
well (even getting the year of publication when *Zotero* didn&rsquo;t) but *Zotero*
links back to a cached version of the HTML which is really nice.

As an example I have cited the NMR paper I was supposed to understand
([Bloom, n.d.](#org5df0712))

It&rsquo;s extremely important is that you remember to NEVER use the `~` character in
LaTeX, relative and absolute paths are both supported but that character is not
supported.

What&rsquo;s extremely important is that you remember to NEVER use the `~` character
in LaTeX, relative and absolute paths are both supported but that character is
not supported.

Also you have to remember that listings will fail if you use use `elisp`, you
MUST use `lisp`, be mindful also that `elisp` will configure emacs but `lisp`
will not.

You will also have to specify, at the very end of the org file, a bibliography
using the following syntax, (it must be at the end, which is frustrating):

Now also really important, all of that code MUST go into the `~/.spacemacs` in
the `user-config` section, that way it will be loaded earlier, atleast I think
it does because it started working for PDF after I did that (but still not HTML,
and the internal link following broke too.)

Now as for comments in a .bib file, these are a nuisance because many
interpreters (including those used by texstudio and texvim will include things
outside the braces.

1.  Managing Citations

    The BibTeX major mode is so good for Emacs I almost don&rsquo;t want to use anything else, but, the Zotero better BibTeX integration is really fucking amazing, and does everything that the emacs integration does, it only syncs one way though so you will have to leave emacs which is a pain if your on i3 but nice generally.
    
    It caches websites which is quite helpful but it might somewhat break helm integration.
    
    Because you can&rsquo;t use comments in a .bib file though, it might be well worth looking at using zotero, there&rsquo;s no fear about it disappearing either because it&rsquo;s free and open source.


<a id="orgf456ea8"></a>

### DONE org-ref

The problem is exporting doesn&rsquo;t work, BibTeX is just a major mode that only manages the creation of citations in the file and the behaviour of Emacs regarding links to entries in BibTeX files, in order to export and leverage citations you need to use the [org-ref package](https://github.com/jkitchin/org-ref).

you definitely want to use the help `org-ref-help`, don&rsquo;t bother with the manual, read the help instead.

That link will show you what to add to the config file as well as how to configure the `org-latex-pdf-process` to use bibtex, basically you need to do the following:

1.  Decide how you are going to manage references
    -   Emacs and the `BibTeX` layer are pretty good and will more or less just work, the only issue is you will need an add on in Firefox to generate bibtex.
    -   Zotero is phenomonal and can be tied to autopush to a BibTeX using the *Better BibTeX* extension, it supports caching websites as well which could be handy. Its free and open source so theres no reason not to use it other than a desire to become more familiar with `.bib` files.
2.  Set a default location for:
    -   the main `.bib`
    -   the `notes.org` corresponding to that `.bib`
    -   the folder containing PDFs linked to that `.bib`
        -   The PDFs MUST match the name of the key.
        -   I think you could probably just link to zotero, or, zotero might do everything on an export?
3.  set the main location for the `reftex` bib
4.  At the top of the `.org` document set the corresponding location for the `.bib` used by that file:

    #+latex_header: \addbibresource{/home/ryan/Dropbox/Studies/Papers/references.bib}

1.  Change the LaTeX build option to tolerate broken links.
2.  Change the LaTeX build option to build the BibTeX
    1.  You will need to remember the `-shel-escape` flag for the `minted` package.
    2.  This method automates the process so I *think* it should work for XeLaTeX and LuaLaTeX as well, but i&rsquo;m not sure.
3.  Pass the bibliography info to LaTeX by placing the following lines at the end of the `.org` file, all the `.bib` references should match, although I remember reading that you may be able to specify multiple with commas, I wouldn&rsquo;t bother.

    <<bibliographystyle link>>
    bibliographystyle:unsrt
    
    <<bibliography link>>
    bibliography:/home/ryan/Dropbox/Studies/Papers/references.bib

So all-up you would need to add the following to you `.emacs.d/init.el`, however I put all of the configuration for BibTeX stuff in the `(defun dotspacemacs/user-config ()` section of the `~.spacemacs`, because intuition suggested to me that the loading order mattered for this:

    ;; ;2. Set Default Location; see org-ref for use of these variables
    (setq org-ref-bibliography-notes "/home/ryan/Dropbox/Studies/Papers/notes.org"
          org-ref-default-bibliography '("/home/ryan/Dropbox/Studies/Papers/references.bib")
          org-ref-pdf-directory "/home/ryan/Dropbox/Studies/Papers/")
    
    ; 3. Set the Reftex Location
    (setq reftex-default-bibliography '("~/Dropbox/bibliography/references.bib"))
    
    
    ; 5. Tolerate broken links
    (require 'org-ref)
    (setq org-export-with-broken-links t)
    ; This finding broken links might be slow in big files, feel fre to set as nil
    (setq org-ref-show-broken-links t)
    
    ; 6. Change the build Process
    ; Build LaTeX with BibTeX option
    (setq org-latex-pdf-process (list "latexmk -shell-escape -bibtex -f -pdf %f"))
    
    (setq org-latex-prefer-user-labels t)
    
    ;;;;; Helpful packages
    (require 'org-id)
    (require 'org-ref-wos)
    (require 'org-ref-scopus)
    (require 'org-ref-pubmed)

Be careful though, don&rsquo;t add everything listed in their GitHub installation instructions, it might break the HELM stuff.

To get the export depends on whether or not you are using bibtex or biblatex, bibtex is slightly simpler, but once it&rsquo;s all working switching to BibLaTeX shouldn&rsquo;t be hard.
Once this is set up be mindful that the LaTeX export will only include references to exports in buffers if you now tie in the appropriate headers and footers etc. That&rsquo;s a little annoying, however I&rsquo;ve just put the BibLaTeX stuff into my template because I&rsquo;ve decided just to use that from now on, BibTeX is only necessary to submitting to journals. ([“Bibtex - Biblatex: Submitting to a Journal,” n.d.](#org078c3a7))

1.  BibTeX

    Those previous instructions set everything up for BibTeX, on order for the citations to be compiled you **must** include a bilbiography link as in those instructions, like, don&rsquo;t change them.
    
    1.  DONE What is a bibliography link
    
        the `org-ref-help` instructions instruct to use a `bibliography link` and a `bibliographystyle link` these lines at the end of an `org-file` that tell `org-ref` what the bibliography files are and where to put them in LaTeX:
        
            <<bibliographystyle link>>
            bibliographystyle:unsrt
            
            <<bibliography link>>
            bibliography:/home/ryan/Dropbox/Studies/Papers/references.bib

2.  BibLaTeX

    The thing is BibTeX is old and doesn&rsquo;t work well with URL&rsquo;s, if you want to
    start referencing everything properly and incorporate referencing in to your
    daily workflow, you&rsquo;re going to have to use BibLaTeX.
    
    before doing anything, because LaTeX is so extremely old you MUST ensure the following:
    
    -   all old `.aux` files are gone
    -   all old `.bbl` files are gone
    -   section names must not contain
        -   footnotes
        -   links
        -   math (this should work but often breaks with `href`)
    -   If you use languages like `markdown`, `emacs-lisp` etc. you switch the
        `minted` package, because otherwise listing will stop the whole thing.
    -   the `hyperref` package is loaded before everything else.
    
    when using `biblatex` follow on from the previous BibTeX set up and modify the following:
    
    1.  Open *TeXStudio*
        1.  Change from `BibTeX` to `biber`
        2.  Make sure to add the `-shell-escape` flag if you&rsquo;re using minted
        3.  open the `.tex` file, `.bib` file and any `.sty` files etc. so that they can be troubleshooted.
    2.  Just leave the `.bib` file as is, you could modify it to include things like `@online` rather than `@misc` but it&rsquo;s going to break exports later on so just leave it. But If you wanted to, you would put the following in your config, but just leave it.
    
        ;Use BibLaTeX not BibTeX
        (setq bibtex-dialect 'biblatex)
    
    3.  Specify the style and bibliography file at the top of the org file like this.
    
        #+latex_header: \usepackage[citestyle=authoryear-icomp, bibstyle=authoryear,hyperref=true,backref=true, maxcitenames=3,url=true,backend=biber,natbib=true]{biblatex}
        #+latex_header: \addbibresource{/home/ryan/Dropbox/Studies/Papers/references.bib}
        #+latex_header: \AtEndDocument{\printbibliography}
    
    -   It&rsquo;s probably better to put all of this in a [style sheet](file:///home/ryan/Dropbox/profiles/Templates/LaTeX/ScreenStyle.sty), then just call  that style sheet as a LaTeX header:
        -   This has the advantage of meaning you will get a bibliography in an `indirect-buffer` just like you do in HTML, that&rsquo;s what i&rsquo;ve done in this document actually.
        -   You&rsquo;re going to want to also use `hyperref` with citatations, so you can load and set up `hyperref`, which must be done first thing, and load the bib stuff in one fell swoop.
    
    4.  Remove the `BibTeX` links at the end
    
        \* References
        
        # ####### Delete these!!!!!
        +<<bibliographystyle link>>
        bibliographystyle:unsrt
        
        <<bibliography link>>
        bibliography:/home/ryan/Dropbox/Studies/Papers/references.bib
        # ####### Delete these!!!!!
    
    -   It seems the `* References \n` heading is necessary, `org-ref` needs that to
        figure out whether or not to include anything beneathe it in the LaTeX
        documents. Despite this, LaTeX will always print a `section{References}` when
        it sees `printbibliography`
        -   For this reason it makes more sense to include the `printbibliography` in
            the `AtEndDocument` macro in the header.
    -   HTML will continue to use `BibTeX2HTML`, which is just `BibTeX`, so it won&rsquo;t
        work at all with BibLaTeX, but the implementation with BibTeX is awful anyway
        and so instead `citeproc` will be used to fix it.
        -   One of the problems is that I really need to be using `biblatex` for half
            descent references, but, I also need those references in HTML.

3.  HTML References

    ***When using HTML Export of Citations in Org-Mode the HTML Citations will ONLY work for those that work for BibTeX so you MUST have a seperate BIBTEX file just for the html Export, the only solution is to not cite online material :shrug:***
    
    When using `org-ref`:
    
    -   BibTeX will give you a half-ass HTML and a half-ass LaTeX
        -   For BibTeX for example requires putting URL&rsquo;s in the `notes` field
    -   BibLaTeX will give you a decent PDF citation style (and I think supports harvard) but no HTML whatsoever at all.
    
    So for HTML we need to set up `citeproc`, `org-ref` includes a function `orcp-citeproc` that can be hooked in before the export function, but it&rsquo;s not very good and I couldn&rsquo;t figure out how to specify custom styles or hyperlinks, the newer package [`citeproc-org`](https://github.com/andras-simonyi/citeproc-org) however supports hyperlinks and custom `.cls`, so it&rsquo;s worth moving to this one even if it is a bit incomplete.
    
    This method does not support the use of reference types like `@online`, and so for this reason a BibLaTeX file is not supported and a BibTeX file must be used. This method does however support the `url` field, so, just have the *Better BibTeX* add-on link to a file where it exports with the `url` field (it is also possible to export URL&rsquo;s to the `notes` field as a fallback). BibLaTex and LaTex will actually use the `url` fields, the only thing that will change is that the type will be set as `@misc`, when you&rsquo;re doing an actual paper and need referencing to match some 100% asanine definition, just re-export the zotero DB as BibLaTeX and change the LaTeX preamble to reflect the new DB location.
    
    -   This might cause a few other styles to fail, the `Nature.csl` style I&rsquo;m using seems to just work so I&rsquo;m going to keep using that, but, I modified the `XML` to use `[]` rather than `()` beccause they&rsquo;re less ambiguous.
    -   It started playing up so what I did was I replaced the `chicago` style file and I moved the `url` field to a `notes` field, I just don&rsquo;t have the time for this to not *just work* so it&rsquo;s better to just leave it like that.
    
    In order to install and set up `citeproc`:
    
    1.  install `citeproc` (use this method otherwise spacemacs removes any installations as as orphans)
        -   add `citeproc` and `citeproc-org` to the `additional-packages` of `~/.spacemacs`
        -   use `spacemacs/paradox-list-packages`
            -   don&rsquo;t use `M-x package-install RET citeproc`
    2.  install [`citeproc-org`](https://github.com/andras-simonyi/citeproc-org) by using `package-install-file` and finding the file downloaded from[ the GitHub repo](https://github.com/andras-simonyi/citeproc-org)
    3.  you need to put the `locales` and `styles` from the repo into the directory, I think it is `~/.emacs.d/elpa/citeproc-org-0.2.2`, so just clone the repo into that directory basically.
        1.  This isn&rsquo;t specified on the github, but otherwise it fails looking for a file in that location so clearly it needs those files.
    4.  Now that it&rsquo;s installed you need to set up the hook, this can be done by defining and running the following function:
        -   the `orcp-citeproc` is one created by Kitchin for `org-ref` it&rsquo;s incompatible and the `citeproc-org` one is much better, just make sure the the `ocrp` hook is removed.
    
        (defun citeproc-org-setup ()
          "Add citeproc-org rendering to the `org-export-before-parsing-hook' hook."
          (interactive)
          (remove-hook 'org-export-before-parsing-hook 'orcp-citeproc)
          (add-hook 'org-export-before-parsing-hook 'citeproc-org-render-references))
        (defun citeproc-off ()
          "remove citeproc-org rendering from the `org-export-before-parsing-hook' hook."
          (interactive)
          (remove-hook 'org-export-before-parsing-hook 'citeproc-org-render-references))
        
        (citeproc-org-setup)
    
    5.  The style is by default Chicago, you need to download another one from [*Zotero*](https://www.zotero.org/styles/nature-no-et-al) and specify at the top with `+#CSL_STYLE`, [This](https://www.zotero.org/styles/institute-of-mathematical-statistics) is a good default.
        1.  This is where problems can occur though because some citation styles don&rsquo;t work with certain fields, like `url` and owing to this citeproc will fail, the Nature one appears to just work so rename the Nature one that I linked above to the Chicago one which acts as a default (i.e. the one used on indirect buffers)
            1.  If you still have problems, just export the URL&rsquo;s from *Zotero* as a `notes` field rather than a `URL` field, which is what I&rsquo;ve done, but the *Nature* style won&rsquo;t then show `notes` but it will show `URL's` so that&rsquo;s confusing.
        2.  It is necessary to use a BibTeX file because things like `@online` will prevent this from working.
    6.  Done, now you should have BibLaTeX and decent HTML referencing, `org-citeproc` overtakes citation rendering for non-LaTeX `org-mode` export backends <sup><a id="fnr.3" class="footref" href="#fn.3">3</a></sup>,
    7.  Now, you need to be a little mindful of the hook though, all the exports with the exception of LaTeX will now all be formatted, no more referencing to the BibTeX, this may be acceptable, it may not be, you may need to disable hook with `citeproc-off` if you don&rsquo;t want it and fall back to a pure `org-ref` in order to allow `org-ref` to export the BibTeX to other formats rather than that formatted by `citeproc`.
        -   `citeproc-org` does not render citations for export backends that are on the list `citeproc-org-ignore-backends`. Citation rendering for these backends is handed over to the active default rendering mechanism (`org-ref`, for example, uses BibTeX or BibLaTeX for LaTeX and `beamer` backends).
    
    The reason for all of this, really, is that I need to practice with BibTeX and referencing so as long as I put anything in it doesn&rsquo;t matter ([Gist, Bavetta, and Stevens, n.d.](#orgd2694ae)) ,  ,it has been shown that study habits, skills and attitude towards learning are as indicative of academic success as past performance ([Credé and Kuncel, n.d.](#org56ff4a5))

4.  Reverting to `org-ref` for export

    If you need to revert to `org-ref` for the citation manager:
    
    -   Put the bibliography link at the end of the org document were deleted at example [delbiblink](#delbiblink)
    -   Remove the hook by using `citeproc-off` as defined in source code [defcitproc](#defcitproc)
        -   you can&rsquo;t toggle a hook so

5.  Using Zotero vs Using BibTeX layer

    As nice as the BibTeX layer is, Zotero will automatically download PDF&rsquo;s as well as the actual html, it also supports taking notes in the actual application, it&rsquo;s going to be too difficult to get BibTeX to download them through the school proxy for me and I am going to need to be able to cite papers.
    
    1.  Considerations of BibTeX vs BibLaTeX
    
        many journals don&rsquo;t support BibLaTex, using zotero might make it easier to jump between in a pinch, however, you could always import into zotero the limited options of BibTeX/BibLaTeX vs *Zotero* may impede it.


<a id="org5de77a7"></a>

### Internal references

I just took this straight from the help  `org-ref-help`

1.  ref links

    <ref>
    
    A ref link refers to a label of some sort. For example, you can refer to a table name, e.g. Table [table-1](#table-1). You have to provide the context before the ref link, e.g. Table, Figure, Equation, Section, and so on.
    
    <table id="orgcabe156" border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
    <caption class="t-above"><span class="table-number">Table 1:</span> A simple table.</caption>
    
    <colgroup>
    <col  class="org-right" />
    </colgroup>
    <tbody>
    <tr>
    <td class="org-right">x</td>
    </tr>
    
    
    <tr>
    <td class="org-right">1</td>
    </tr>
    
    
    <tr>
    <td class="org-right">2</td>
    </tr>
    </tbody>
    </table>
    
    Or you can refer to an org-mode label as in Table [table-3](#table-3).
    
    Note: You may need to set org-latex-prefer-user-labels to t if you refer to times by their &ldquo;name&rdquo; for the export to use the name you create.
    
        (setq org-latex-prefer-user-labels t)
    
    <table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
    <caption class="t-above"><span class="table-number">Table 2:</span> Another simple table. <div id="table-3"></div></caption>
    
    <colgroup>
    <col  class="org-left" />
    
    <col  class="org-left" />
    </colgroup>
    <thead>
    <tr>
    <th scope="col" class="org-left">Command</th>
    <th scope="col" class="org-left">Result</th>
    </tr>
    </thead>
    
    <tbody>
    <tr>
    <td class="org-left"><code>false; echo "yes"</code></td>
    <td class="org-left">prints yes</td>
    </tr>
    
    
    <tr>
    <td class="org-left"><code>true; echo "yes"</code></td>
    <td class="org-left">prints yes</td>
    </tr>
    
    
    <tr>
    <td class="org-left"><code>false &amp;&amp; echo "yes"</code></td>
    <td class="org-left">does nothing</td>
    </tr>
    
    
    <tr>
    <td class="org-left"><code>true &amp;&amp; echo "yes"</code></td>
    <td class="org-left">prints yes</td>
    </tr>
    
    
    <tr>
    <td class="org-left"><code>firefox &amp; disown</code></td>
    <td class="org-left">runs firefox and then disowns</td>
    </tr>
    </tbody>
    </table>
    
    To help you insert ref links, use the &ldquo;Org -> org-ref -> Insert ref&rdquo; menu, or run the command <org-ref-helm-insert-ref-link>. There is no default key-binding for this.
    
    ref links are functional. If you put the cursor on a ref link, you should see a message in the minibuffer with some context of the corresponding label. If you click on the ref link, the cursor will jump to the label.
    
    A brief note about references to a section. You can make a ref link to a CUSTOM<sub>ID</sub>. Section [sec-misc](#sec-misc) has a label link in the headline. That works, but is not too pretty. Section [ref-links](#ref-links) uses the CUSTOM<sub>ID</sub> property. For this to work, you should set `org-latex-prefer-user-labels` to t.
    
    Also note that &ldquo;#+tblname:&rdquo; and &ldquo;#+label:&rdquo; are deprecated in org-mode now, and &ldquo;#+name:&rdquo; is preferred.

2.  Miscellaneous ref links  <a name="sec-misc"></a>

    <ref!pageref> <ref!nameref> <ref!eqref>
    
    org-ref also provides these links:
    
    -   **pageref:** The page a label is on
    -   **nameref:** The name of a section a label is in
    -   **eqref:** Puts the equation number in parentheses
    -   **autoref:** A command from hyperref that automatically prefixes the reference number.
    -   **cref & Cref:** [cleveref – Intelligent cross-referencing](https://www.ctan.org/tex-archive/macros/latex/contrib/cleveref?lang=en) (crefrange is not supported)
    
    Note for eqref, you must use a LaTeX label like this:
    
    \begin{equation}
    e^x = 4 \label{eq:1}
    \end{equation}
    
    Then you can refer to Eq. [eq:1](#eq:1) in your documents.
    
    Autoref works like this: <table-3>, <sec-misc>.
    
    You can specify the default ref link type in \`org-ref-default-ref-type&rsquo;.

3.  Inserting Links

    You can store a link from emacs into org using `SPC a o`, this link can be later pasted with `C-c l`, you will want to adjust the variable `org-link-file-path-type`, it allows relative paths etc. to be toggled.
    
    If the link contains `docview::` it will be exported as absolute, so always take the link to things like PDF files from *Treemacs*, never from the docview buffer, always check the link for `file:` which is what you need.


<a id="org015b937"></a>

### Different bib file for a single document

If you want to change the reference file just for just one project, you can tell BibteX you are using that file somehow and you can just change all the references in the file, I wouldn&rsquo;t bother though, I&rsquo;d just use one massive file because BibLaTeX will only include what&rsquo;s cited and you can use programs to strip the `.bib` file apart when given a LaTeX file with corresponding entries. (or you could use a vim macro to be honest).


<a id="org8ac6c9a"></a>

### How BibLaTeX Works

So if you have org-ref set up properly, and have the lines shown in listing at the top of the `org` mode file running the `org-mode` \(\LaTeX\) export should produce a `.tex` file in the same directory.

Opening the directory in the terminal and running `pdflatex file.tex` will then produce the following output:

-   file.pdf
    -   This will not contain any references
-   file.bcf
    -   This is only produced if the `\usepackage[backend=biber]{biblatex}` line is in the `.tex` file.
    -   This relies upon access to the `references.bib` file

\(\LaTeX\) expects a `.bbl` file to build references with, to create that the `biber` command will be used, so run `biber file.bcf` in the directory and it will produce a `.bbl` file.

-   If using VimTeX this will work automagically
-   If using TeXStudio go to `Options` -> `Configure` -> `Build` and change *Default Bibliography Tool* to `biber`
    -   To Build the bibliography use the `Tools` -> `Bibliography` option (`F8`) and then build the document with `Tools` -> `Compile` (`F5`)

Now that the `.bbl` has been produced, use `pdflatex file.tex` one last time to rebuild the PDF file, this time the `.bbl` will be swept up and included in the PDF (because the `AtEndDocument{\printbibliography}` asked for it.)

I&rsquo;m not sure exactly how to add that to the `org-latex-pdf-process` but it might make sense to just do `SPC o T` and then type `biber bcf TAB Ret` to prevent unnecessary slow down anyway (and to remember the workflow).

Remember that the bottom section, as shown in listing [5](#org2e76291) are only for the HTML Export, `org-ref` looks for the `addbibresource{}` somewhere in the file and uses that `.bib`, unfourtunately the lines below only work for bibtex and the code in listing is necessary to use biblatex (which is desired because bibtex doesn&rsquo;t work with *URLs*)

    * References
    This section is necessary for references to work in /HTML/ export, however it breaks LaTeX export because that relies on BibLaTex NOT BibTex which this is for.
    
    Org-ref hasn't been updated to allow a way to use HTML references with the syntax for biblatex.
    
    The Auto Sync is handled from inside
    
    # ####### Delete these!!!!!
    +<<bibliographystyle link>>
    bibliographystyle:unsrt
    
    <<bibliography link>>
    bibliography:./references.bib
    # ####### Delete these!!!!!

Also Note that the `,#+LATEX_HEADER: \addbibresource{references.bib}` **must** be in the `org` file, because that is what `org-ref` uses to insert citations with the `C-c ]` key binding.

So to summarise, if you&rsquo;re writing a LaTeX paper, put in the `org` file and then open a terminal in the directory and run the code in :

    # Export the Org File
        # If org-ref set up cite:key should export to \cite{key}
    emacs file.org --batch -f org-latex-export-to-latex --kill
    
    # Build the PDF from the .tex
    pdflatex file.tex    # If \usepackage[backend=biber]{biblatex} then .bcf produced
    
    # Use Biber to create a .bbl that pdflatex can use
    biber file.bcf
    
    # Use pdflatex to rebuild the pdf, this time it should use the .bbl to make refs
    pdflatex file.tex    # If \printbibliography is included will make refs

However all of this can be done by using `latexmk` which just runs `pdflatex` and `biber` until the document stops changing:

    # Presuming only one ~tex~ file in there
    latexmk -f -pdfxe -interaction=nonstopmode >&2 /dev/null ; latexmk -c


<a id="orgd40bfcb"></a>

## DONE How do attach external files that I can follow?     :Attachments:

Does the filetype matter? like markdown pdf whatever?
This [Link to the manual](https://orgmode.org/manual/Handling-links.html#Handling-links) suggests that any file can be linked to be using `C-u C-c C-l`[ PDF to this doc, pretend it&rsquo;s a tutorial sheet or a learning guide or something](./1.pdf)

You may also want to consider using the insert menu  `, i a` / `<SPC> i a` to reach the attach menu `org-attach` / `, i a a` `<SPC> i a a` which might do a lot of the work for you:


<a id="org8482fe7"></a>

## Is there a way to include links to locations of  external files?


<a id="org3dfde2b"></a>

## Interlinking

There is a tonne of information in the [manual](https://orgmode.org/manual/External-links.html#External-links) on how to do this, but
The easiest way is to use: (`SPC a o l` followed by `C-c l` is your friend)  fs

-   Org-brain
-   Org-Wiki
    -   when org is exported to HTML, the links are changed to `.html`, so it will correspond to HTML files in that directory, an auto export hook could solve that.
-   Hyperbole

One could also have auto HTML export as well by using this lisp code:

    
    # Local variables:
    # after-save-hook: org-html-export-to-html
    # end:


<a id="org81193da"></a>

## Mathematics     :LaTeX:


<a id="org62fb0e9"></a>

### Inline Preview

When using `C-c C-x C-l` to preview LaTeX fragments, make sure you are using
`dvi2png` because it is way faster, avoid using `imagemagick` because it is slower.


<a id="org80d6a59"></a>

### DONE Mathml     :Mathml:

The doc string for `org-export-with-latex` describes how to select
mathjax, verbatim output, or not to export LaTeX at all, although it
goes further to say:

> If you prefer, you can also request that LaTeX fragments are processed
> into small images that will be inserted into the browser page.

But no value is actually listed for requesting that.

The only way I&rsquo;ve obtained the desired result is with:

-   `#+OPTIONS: tex:dvipng`
-   `#+OPTIONS: tex:dvisvg`

If this is needed globally set the variable specific to the `html`
backend (or preferably the email backend):

    (setq-default org-html-with-latex `dvipng)

1.  Equation References

    org-ref also provides these links:
    
    -   **pageref:** The page a label is on
    -   **nameref:** The name of a section a label is in
    -   **eqref:** Puts the equation number in parentheses
    -   **autoref:** A command from hyperref that automatically prefixes the reference number.
    -   **cref & Cref:** [cleveref – Intelligent cross-referencing](https://www.ctan.org/tex-archive/macros/latex/contrib/cleveref?lang=en) (crefrange is not supported)
    
    Note for eqref, you must use a LaTeX label like this:
    
    \begin{equation}
    e^x = 4 \label{eq:1}
    \end{equation}
    
    <table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
    
    
    <colgroup>
    <col  class="org-left" />
    
    <col  class="org-left" />
    
    <col  class="org-left" />
    
    <col  class="org-left" />
    
    <col  class="org-left" />
    
    <col  class="org-right" />
    
    <col  class="org-left" />
    
    <col  class="org-left" />
    
    <col  class="org-left" />
    
    <col  class="org-left" />
    
    <col  class="org-left" />
    
    <col  class="org-right" />
    
    <col  class="org-left" />
    
    <col  class="org-left" />
    </colgroup>
    <tbody>
    <tr>
    <td class="org-left">:foreground</td>
    <td class="org-left">default</td>
    <td class="org-left">:background</td>
    <td class="org-left">default</td>
    <td class="org-left">:scale</td>
    <td class="org-right">2.0</td>
    <td class="org-left">:html-foreground</td>
    <td class="org-left">Black</td>
    <td class="org-left">:html-background</td>
    <td class="org-left">Transparent</td>
    <td class="org-left">:html-scale</td>
    <td class="org-right">1.0</td>
    <td class="org-left">:matchers</td>
    <td class="org-left">(begin $1 $ $$ \( \[)</td>
    </tr>
    </tbody>
    </table>
    
    Then you can refer to Eq. [eq:1](#eq:1) in your documents.
    
    Autoref works like this: <table-3>, <sec-misc>.
    
    You can specify the default ref link type in \`org-ref-default-ref-type&rsquo;.


<a id="orga039d71"></a>

### LaTeX Export

To export as \LaTeX make sure to put something like this in the org mode header:

    #+OPTIONS: broken-links:auto todo:nil H:9

It is extremely important not to have filenames with whitespace
characters, this WILL break LaTeX exports when using the 
minted package owing (I believe :shrug:) to the `-shell-escape` flag.


<a id="org624543d"></a>

# DONE Tag Filtering     :tagging:


<a id="org932c0ed"></a>

## General Information

-   According to the documentation on [Tag Inheritance](https://orgmode.org/manual/Tag-Inheritance.html#Tag-Inheritance), Tags respect the heirachy
    of the document.
-   you can also put `(setq org-complete-tags-always-offer-all-agenda-tags t)` in
    the `~/.emacs.d/init.el` in order to have autocompletion from all other
    documents in the agenda.

1.  Global Tags

    In order for tags to appear in the agenda buffer they must be added to the
    `org-agenda-files` variable, Files can be added /removed from this variable with
    `C-c [` / `C-c ]` respectively.
    
    use `C-c a` / `<SPC> m a` to get up the agenda view, from there you can open an *agenda-buffer*:
    
    -   `m` will take you to tag matching
        -   `M` will take you to tag matching for items marked `todo`
    -   `t` will take you to all the todo lists
        -   `T` will let you choose `WAITING=/=done` etc.
    
    If I do agenda search with `C-c a` then I can further filter with
    `org-agenda-filter-tags` tied do `\`, but the tags listed aren&rsquo;t pruned which is
    a problem, can I filter based on the tags based on the top first or between?
    
    After the agenda buffer has been generated you can use `\` to filter by tag or
    use `<ALT>-<SPC>` to open the transient state, which will offer many different
    ways to filter the tags.
    
    You can&rsquo;t filter which tags popup when you try and filter by tags, so the best
    method, for now, is to use `\` tag by tag and read-off whats in the list one-by
    one, using nested tags and sensible names will help.
    
    In order to have all the global tags listed, you need to [the following](https://emacs.stackexchange.com/a/29222) in the
    `~/.emacs.d/.init.el`:
    
        (setq org-complete-tags-always-offer-all-agenda-tags t)
    
    1.  Progressive Filtering
    
        I haven&rsquo;t found anyway to do do this, but  `org-global-tags-completion-table` might be a start.

2.  LocalTags

    Local tags are managed by *Sparse Trees* which collapses and flattens the tree but for matching tags, certainly preferable for a local document.
    
    using `, /` allows me to create *Sparse Trees*, I can choose to do that either by todo status or by tag, although this broke in these notes so it may not be reliable?
    
    After creating the sparse tree I don&rsquo;t believe further filtering is possible, however you can use *Boolean Logic* when creating the  tree in order to have it even sparser.
    
    it appears that if I press `<SPC> m a m` (for mode-agenda-match) I can search for all tags, it also implies that tags apply per headline?
    A local sparse tree can be generated by using `c-c / m` or `C-c \`
    First you need to list the org-file in the variable `org-agenda-files`, this could be customised manually but you usually just do `C-c [`.
    
    -   if you press `<SPC> m b` it will take you to a buffer only with what is beneath that headline, this is amazing, just like *Beorg* , really good!
        -   to kill this buffer:  `<SPC> m b` / `C-x k`
        -   it&rsquo;s also possible to jump straight to the buffer list with `C-x C-b` and:
            1.  mark buffers for deletion with `d d=/=C-k`
            2.  eXecute the deletion with `x`

3.  Listing Empty Headlines

    use the [special property](https://orgmode.org/manual/Property-syntax.html) TAGS like so:
    
        TAGS=""

4.  Tag Heirachy

    If you list tags in the preamble or `org-tag-alist` like this:
    
        #+TAGS: [ Control : Context Task ]
        #+TAGS: [ Persp : Vision Goal AOF Project ]
    
    you will get a scheme like this:
    
    -   ‘GTD’
        -   ‘Persp’
            -   ‘Vision’
            -   ‘Goal’
            -   ‘AOF’
            -   ‘Project’
        -   ‘Control’
            -   ‘Context’
            -   ‘Task’
    
    So if you search for &rsquo;GTD&rsquo; you will get back everything beneath that (e.g. &rsquo;persp&rsquo; and &rsquo;Goal&rsquo;), if you search for &rsquo;Control&rsquo; you will only get back matches for &rsquo;context&rsquo; and &rsquo;task&rsquo;)
    
    This is better than using tag inheritance because something tagged as &rsquo;PCA&rsquo; may not necessarily be underneath a heading like &ldquo;Unsupervised&rdquo; Learning.
    
    It&rsquo;s probably better to set these up in the `org-tag-alist` variable in the  [config](file:///home/ryan/.emacs.d/init.el)  but I can&rsquo;t get it to work, so instead list them in the preamble and leverage the fact that all files in the agenda will be listed as valid tags.

5.  DONE Capture Templates

    Say I want to take a math note, can I just use `<SPC a o c>` and open the right template? There is some info in the [Manual](https://orgmode.org/manual/Setting-up-capture.html#Setting-up-capture) and on [This Site](https://sachachua.com/blog/2015/02/learn-take-notes-efficiently-org-mode/).


<a id="orgb9f9176"></a>

## TimeStapms

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">Type</th>
<th scope="col" class="org-left">Description</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">Deadline</td>
<td class="org-left">When a task is due</td>
</tr>
</tbody>

<tbody>
<tr>
<td class="org-left">Scheduled</td>
<td class="org-left">When you intend to start working on that task</td>
</tr>
</tbody>

<tbody>
<tr>
<td class="org-left">Timestamp</td>
<td class="org-left">a specification of a date or a range ofdates.</td>
</tr>
</tbody>
</table>


<a id="org9cb103b"></a>

## Keyboard Shortcuts

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<tbody>
<tr>
<td class="org-left">Shortcut</td>
<td class="org-left">Description</td>
<td class="org-left">command</td>
</tr>


<tr>
<td class="org-left"><code>C-c / m</code>  <code>, /</code> or <code>C-c \</code> or <code>&lt;SPC&gt; m /</code></td>
<td class="org-left">Create a sparse tree with all headlines matching a tags search.</td>
<td class="org-left"><code>(org-match-sparce-tree)</code></td>
</tr>


<tr>
<td class="org-left"><code>C-c [</code></td>
<td class="org-left">Adds the current file to the agenda variable so it is included in agenda searches (the file can be removed with <code>C-c ]</code></td>
<td class="org-left">(org-agenda-file-to-front)</td>
</tr>


<tr>
<td class="org-left"><code>C-’</code></td>
<td class="org-left">cycle through agenda file list</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left"><code>&lt;SPC&gt; a m</code></td>
<td class="org-left">Create a global list oftag matches from all agenda files (files must be listed in the agenda variable)</td>
<td class="org-left">(org-tags-view)</td>
</tr>


<tr>
<td class="org-left"><code>&lt;SPC&gt; a t</code></td>
<td class="org-left">Create a global to do list</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left"><code>\</code></td>
<td class="org-left">Only works in an agenda bugger, filters that buffr by the given tag.</td>
<td class="org-left"><code>(org-agenda-fiter-tags)</code></td>
</tr>


<tr>
<td class="org-left">(<code>*</code> or <code>%</code>) then <code>B</code></td>
<td class="org-left">Bulk Change matches in agenda view</td>
<td class="org-left">??</td>
</tr>


<tr>
<td class="org-left"><code>C-c C-q</code></td>
<td class="org-left">et tag for current heading</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">&rsquo;<del><code>C-u C-c C-q</code></del>&rsquo; / <code>&lt;SPC&gt; u C-c C-q</code></td>
<td class="org-left">realign tag in all heading</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left"><code>C-c C-o</code></td>
<td class="org-left">globally (agenda) match tag at curor</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left"><code>C-c .</code></td>
<td class="org-left">insert SCHEDULE timestamp via prompt</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left"><code>C-c C-d</code></td>
<td class="org-left">insert DEADLINE timestamp</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left"><code>C-c C-</code></td>
<td class="org-left">insert CHEDULED timestamp</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left"><code>C-c / d</code></td>
<td class="org-left">create pare tree with all deadline due</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left"><code>C-c C-x C-i</code></td>
<td class="org-left">start clock on current item</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left"><code>C-c C-x C-o/x</code></td>
<td class="org-left">stop/cancel clock on current item</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left"><code>C-c C-x C-d</code></td>
<td class="org-left">display total subtree times</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left"><code>C-c C-c</code></td>
<td class="org-left">remove displayed times</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left"><code>C-c C-x C-r</code></td>
<td class="org-left">insert/update table with clock report</td>
<td class="org-left">&#xa0;</td>
</tr>
</tbody>
</table>

there are way more more shortcuts inside this drawer <sup><a id="fnr.4" class="footref" href="#fn.4">4</a></sup>



    ================================================================================
    Org-Mode Reference Card (for version 7.8.11)
    ================================================================================
    
    
    
    ================================================================================
    Getting Started
    ================================================================================
    To read the on-line documentation try             M-x org-info
    
    ================================================================================
    Visibility Cycling
    ================================================================================
    
    rotate current subtree between states             TAB
    rotate entire buffer between states               S-TAB
    restore property-dependent startup visibility     C-u C-u TAB
    show the whole file, including drawers            C-u C-u C-u TAB
    reveal context around point                       C-c C-r
    
    ================================================================================
    Motion
    ================================================================================
    
    next/previous heading                             C-c C-n/p
    next/previous heading, same level                 C-c C-f/b
    backward to higher level heading                  C-c C-u
    jump to another place in document                 C-c C-j
    previous/next plain list item                     S-UP/DOWN\notetwo
    
    ================================================================================
    Structure Editing
    ================================================================================
    
    insert new heading/item at current level          M-RET
    insert new heading after subtree                  C-RET
    insert new TODO entry/checkbox item               M-S-RET
    insert TODO entry/ckbx after subtree              C-S-RET
    turn (head)line into item, cycle item type        C-c -
    turn item/line into headline                      C-c *
    promote/demote heading                            M-LEFT/RIGHT
    promote/demote current subtree                    M-S-LEFT/RIGHT
    move subtree/list item up/down                    M-S-UP/DOWN
    sort subtree/region/plain-list                    C-c ^
    clone a subtree                                   C-c C-x c
    copy visible text                                 C-c C-x v
    kill/copy subtree                                 C-c C-x C-w/M-w
    yank subtree                                      C-c C-x C-y or C-y
    narrow buffer to subtree / widen                  C-x n s/w
    
    ================================================================================
    Capture - Refile - Archiving
    ================================================================================
    capture a new item (C-u C-u = goto last)          C-c c \noteone
    refile subtree (C-u C-u = goto last)              C-c C-w
    archive subtree using the default command         C-c C-x C-a
    move subtree to archive file                      C-c C-x C-s
    toggle ARCHIVE tag / to ARCHIVE sibling           C-c C-x a/A
    force cycling of an ARCHIVEd tree                 C-TAB
    
    ================================================================================
    Filtering and Sparse Trees
    ================================================================================
    
    construct a sparse tree by various criteria       C-c /
    view TODO's in sparse tree                        C-c / t/T
    global TODO list in agenda mode                   C-c a t \noteone
    time sorted view of current org file              C-c a L
    
    ================================================================================
    Tables
    ================================================================================
    
    --------------------------------------------------------------------------------
    Creating a table
    --------------------------------------------------------------------------------
    
    just start typing, e.g.                           |Name|Phone|Age RET |- TAB
    convert region to table                           C-c |
    ... separator at least 3 spaces                   C-3 C-c |
    
    --------------------------------------------------------------------------------
    Commands available inside tables
    --------------------------------------------------------------------------------
    
    The following commands work when the cursor is inside a table.
    Outside of tables, the same keys may have other functionality.
    
    --------------------------------------------------------------------------------
    Re-aligning and field motion
    --------------------------------------------------------------------------------
    
    re-align the table without moving the cursor      C-c C-c
    re-align the table, move to next field            TAB
    move to previous field                            S-TAB
    re-align the table, move to next row              RET
    move to beginning/end of field                    M-a/e
    
    --------------------------------------------------------------------------------
    Row and column editing
    --------------------------------------------------------------------------------
    
    move the current column left                      M-LEFT/RIGHT
    kill the current column                           M-S-LEFT
    insert new column to left of cursor position      M-S-RIGHT
    
    move the current row up/down                      M-UP/DOWN
    kill the current row or horizontal line           M-S-UP
    insert new row above the current row              M-S-DOWN
    insert hline below (C-u : above) current row      C-c -
    insert hline and move to line below it            C-c RET
    sort lines in region                              C-c ^
    
    --------------------------------------------------------------------------------
    Regions
    --------------------------------------------------------------------------------
    
    cut/copy/paste rectangular region                 C-c C-x C-w/M-w/C-y
    fill paragraph across selected cells              C-c C-q
    
    --------------------------------------------------------------------------------
    Miscellaneous
    --------------------------------------------------------------------------------
    
    to limit column width to N characters, use        ...| <N> |...
    edit the current field in a separate window       C-c `
    make current field fully visible                  C-u TAB
    export as tab-separated file                      M-x org-table-export
    import tab-separated file                         M-x org-table-import
    sum numbers in current column/rectangle           C-c +
    
    --------------------------------------------------------------------------------
    Tables created with the table.el package
    --------------------------------------------------------------------------------
    
    insert a new table.el table                       C-c ~
    recognize existing table.el table                 C-c C-c
    convert table (Org-mode <-> table.el)             C-c ~
    
    --------------------------------------------------------------------------------
    Spreadsheet
    --------------------------------------------------------------------------------
    
    Formulas typed in field are executed by TAB,
    RET and C-c C-c.  = introduces a column
    formula, := a field formula.
    
    Example: Add Col1 and Col2                        |=$1+$2      |
    ... with printf format specification              |=$1+$2;%.2f|
    ... with constants from constants.el              |=$1/$c/$cm |
    sum from 2nd to 3rd hline                         |:=vsum(@II..@III)|
    apply current column formula                      | = |
    
    set and eval column formula                       C-c =
    set and eval field formula                        C-u C-c =
    re-apply all stored equations to current line     C-c *
    re-apply all stored equations to entire table     C-u C-c *
    iterate table to stability                        C-u C-u C-c *
    rotate calculation mark through # * ! ^ _ $       C-#
    show line, column, formula reference              C-c ?
    toggle grid / debugger                            C-c }/{
    
    --------------------------------------------------------------------------------
    Formula Editor
    --------------------------------------------------------------------------------
    
    edit formulas in separate buffer                  C-c '
    exit and install new formulas                     C-c C-c
    exit, install, and apply new formulas             C-u C-c C-c
    abort                                             C-c C-q
    toggle reference style                            C-c C-r
    pretty-print Lisp formula                         TAB
    complete Lisp symbol                              M-TAB
    shift reference point                             S-cursor
    shift test line for column references             M-up/down
    scroll the window showing the table               M-S-up/down
    toggle table coordinate grid                      C-c }
    
    ================================================================================
    Links
    ================================================================================
    
    globally store link to the current location       C-c l \noteone
    insert a link (TAB completes stored links)        C-c C-l
    insert file link with file name completion        C-u C-c C-l
    edit (also hidden part of) link at point          C-c C-l
    
    open file links in emacs                          C-c C-o
    ...force open in emacs/other window               C-u C-c C-o
    open link at point                                mouse-1/2
    ...force open in emacs/other window               mouse-3
    record a position in mark ring                    C-c %
    jump back to last followed link(s)                C-c &
    find next link                                    C-c C-x C-n
    find previous link                                C-c C-x C-p
    edit code snippet of file at point                C-c '
    toggle inline display of linked images            C-c C-x C-v
    
    ================================================================================
    Working with Code (Babel)
    ================================================================================
    
    execute code block at point                       C-c C-c
    open results of code block at point               C-c C-o
    check code block at point for errors              C-c C-v c
    insert a header argument with completion          C-c C-v j
    view expanded body of code block at point         C-c C-v v
    view information about code block at point        C-c C-v I
    go to named code block                            C-c C-v g
    go to named result                                C-c C-v r
    go to the head of the current code block          C-c C-v u
    go to the next code block                         C-c C-v n
    go to the previous code block                     C-c C-v p
    demarcate a code block                            C-c C-v d
    execute the next key sequence in the code edit bu C-c C-v x
    execute all code blocks in current buffer         C-c C-v b
    execute all code blocks in current subtree        C-c C-v s
    tangle code blocks in current file                C-c C-v t
    tangle code blocks in supplied file               C-c C-v f
    ingest all code blocks in supplied file into the  C-c C-v i
    switch to the session of the current code block   C-c C-v z
    load the current code block into a session        C-c C-v l
    view sha1 hash of the current code block          C-c C-v a
    
    ================================================================================
    Completion
    ================================================================================
    
    In-buffer completion completes TODO keywords at headline start, TeX
    macros after `\', option keywords after `#-', TAGS
    after  `:', and dictionary words elsewhere.
    
    complete word at point                            M-TAB
    
    
    
    
    ================================================================================
    TODO Items and Checkboxes
    ================================================================================
    
    rotate the state of the current item              C-c C-t
    select next/previous state                        S-LEFT/RIGHT
    select next/previous set                          C-S-LEFT/RIGHT
    toggle ORDERED property                           C-c C-x o
    view TODO items in a sparse tree                  C-c C-v
    view 3rd TODO keyword's sparse tree               C-3 C-c C-v
    
    set the priority of the current item              C-c , [ABC]
    remove priority cookie from current item          C-c , SPC
    raise/lower priority of current item              S-UP/DOWN\notetwo
    
    insert new checkbox item in plain list            M-S-RET
    toggle checkbox(es) in region/entry/at point      C-c C-x C-b
    toggle checkbox at point                          C-c C-c
    update checkbox statistics (C-u : whole file)     C-c #
    
    ================================================================================
    Tags
    ================================================================================
    
    set tags for current heading                      C-c C-q
    realign tags in all headings                      C-u C-c C-q
    create sparse tree with matching tags             C-c \\
    globally (agenda) match tags at cursor            C-c C-o
    
    ================================================================================
    Properties and Column View
    ================================================================================
    
    set property/effort                               C-c C-x p/e
    special commands in property lines                C-c C-c
    next/previous allowed value                       S-left/right
    turn on column view                               C-c C-x C-c
    capture columns view in dynamic block             C-c C-x i
    
    quit column view                                  q
    show full value                                   v
    edit value                                        e
    next/previous allowed value                       n/p or S-left/right
    edit allowed values list                          a
    make column wider/narrower                        > / <
    move column left/right                            M-left/right
    add new column                                    M-S-right
    Delete current column                             M-S-left
    
    
    ================================================================================
    Timestamps
    ================================================================================
    
    prompt for date and insert timestamp              C-c .
    like C-c . but insert date and time format        C-u C-c .
    like C-c . but make stamp inactive                C-c !
    insert DEADLINE timestamp                         C-c C-d
    insert SCHEDULED timestamp                        C-c C-s
    create sparse tree with all deadlines due         C-c / d
    the time between 2 dates in a time range          C-c C-y
    change timestamp at cursor A+/-1 day                S-RIGHT/LEFT\notetwo
    change year/month/day at cursor by A+/-1            S-UP/DOWN\notetwo
    access the calendar for the current date          C-c >
    insert timestamp matching date in calendar        C-c <
    access agenda for current date                    C-c C-o
    select date while prompted                        mouse-1/RET
    toggle custom format display for dates/times      C-c C-x C-t
    
    
    --------------------------------------------------------------------------------
    Clocking time
    --------------------------------------------------------------------------------
    
    start clock on current item                       C-c C-x C-i
    stop/cancel clock on current item                 C-c C-x C-o/x
    display total subtree times                       C-c C-x C-d
    remove displayed times                            C-c C-c
    insert/update table with clock report             C-c C-x C-r
    
    ================================================================================
    Agenda Views
    ================================================================================
    
    add/move current file to front of agenda          C-c [
    remove current file from your agenda              C-c ]
    cycle through agenda file list                    C-'
    set/remove restriction lock                       C-c C-x </>
    
    compile agenda for the current week               C-c a a \noteone
    compile global TODO list                          C-c a t \noteone
    compile TODO list for specific keyword            C-c a T \noteone
    match tags, TODO kwds, properties                 C-c a m \noteone
    match only in TODO entries                        C-c a M \noteone
    find stuck projects                               C-c a # \noteone
    show timeline of current org file                 C-c a L \noteone
    configure custom commands                         C-c a C \noteone
    agenda for date at cursor                         C-c C-o
    
    --------------------------------------------------------------------------------
    Commands available in an agenda buffer
    --------------------------------------------------------------------------------
    
    --------------------------------------------------------------------------------
    View Org file
    --------------------------------------------------------------------------------
    
    show original location of item                    SPC/mouse-3
    show and recenter window                          L
    goto original location in other window            TAB/mouse-2
    goto original location, delete other windows      RET
    show subtree in indirect buffer, ded.\ frame      C-c C-x b
    toggle follow-mode                                F
    
    --------------------------------------------------------------------------------
    Change display
    --------------------------------------------------------------------------------
    
    delete other windows                              o
    view mode dispatcher                              v
    switch to day/week/month/year/def view            d w vm vy vSP
    toggle diary entries / time grid / habits         D / G / K
    toggle entry text / clock report                  E / R
    toggle display of logbook entries                 l / v l/L/c
    toggle inclusion of archived trees/files          v a/A
    refresh agenda buffer with any changes            r / g
    filter with respect to a tag                      /
    save all org-mode buffers                         s
    display next/previous day,week,...                f / b
    goto today / some date (prompt)                   . / j
    
    --------------------------------------------------------------------------------
    Remote editing
    --------------------------------------------------------------------------------
    
    digit argument                                    0-9
    change state of current TODO item                 t
    kill item and source                              C-k
    archive default                                   $ / a
    refile the subtree                                C-c C-w
    set/show tags of current headline                 : / T
    set effort property (prefix=nth)                  e
    set / compute priority of current item            , / P
    raise/lower priority of current item              S-UP/DOWN\notetwo
    run an attachment command                         C-c C-a
    schedule/set deadline for this item               C-c C-s/d
    change timestamp one day earlier/later            S-LEFT/RIGHT\notetwo
    change timestamp to today                         >
    insert new entry into diary                       i
    start/stop/cancel the clock on current item       I / O / X
    jump to running clock entry                       J
    mark / unmark / execute bulk action               m / u / B
    
    --------------------------------------------------------------------------------
    Misc
    --------------------------------------------------------------------------------
    
    follow one or offer all links in current entry    C-c C-o
    
    --------------------------------------------------------------------------------
    Calendar commands
    --------------------------------------------------------------------------------
    
    find agenda cursor date in calendar               c
    compute agenda for calendar cursor date           c
    show phases of the moon                           M
    show sunrise/sunset times                         S
    show holidays                                     H
    convert date to other calendars                   C
    
    --------------------------------------------------------------------------------
    Quit and Exit
    --------------------------------------------------------------------------------
    
    quit agenda, remove agenda buffer                 q
    exit agenda, remove all agenda buffers            x
    
    ================================================================================
    LaTeX and cdlatex-mode
    ================================================================================
    
    preview LaTeX fragment                            C-c C-x C-l
    expand abbreviation (cdlatex-mode)                TAB
    insert/modify math symbol (cdlatex-mode)          ` / '
    insert citation using RefTeX                      C-c C-x [
    
    ================================================================================
    Exporting and Publishing
    ================================================================================
    
    Exporting creates files with extensions .txt and .html
    in the current directory.  Publishing puts the resulting file into
    some other place.
    
    export/publish dispatcher                         C-c C-e
    
    export visible part only                          C-c C-e v
    insert template of export options                 C-c C-e t
    toggle fixed width for entry or region            C-c :
    toggle pretty display of scripts, entities        C-c C-x {\tt\char`\}
    
    --------------------------------------------------------------------------------
    Comments: Text not being exported
    --------------------------------------------------------------------------------
    
    Lines starting with # and subtrees starting with COMMENT are
    never exported.
    
    toggle COMMENT keyword on entry                   C-c ;
    
    ================================================================================
    Dynamic Blocks
    ================================================================================
    
    update dynamic block at point                     C-c C-x C-u
    update all dynamic blocks                         C-u C-c C-x C-u
    
    ================================================================================
    Notes
    ================================================================================
    [1] This is only a suggestion for a binding of this command.  Choose
    your own key as shown under ACTIVATION.
    
    [2] Keybinding affected by org-support-shift-select and also
     org-replace-disputed-keys.


<a id="org2f10e43"></a>

## Tags

There are two types of tags, `todo` tags and `:patt1:` tags, working with them
is essentailly the difference between using `t` and `m` respectively.

There is a tag line at the top of the file that lists tags included in this
file, and you can add tags to the `org-tag-alist` variable, this is worth doing
to prevent you from creating double tags.

You can also merely specify any tag in the headline using `:patt1:` which can be
triggered by using `C-c C-q`, it&rsquo;s probably better to specify tags in the
preamble and/or variable because you can set mutually exclusive and nested tags.
after doing this make cure to press `C-c C-c` on the `#+TAGS:` line in order to
activate the changes


<a id="org3b27f3a"></a>

### DONE Listing used tags     :tagging:

<span class="timestamp-wrapper"><span class="timestamp">&lt;2019-11-19 Tue&gt;</span></span>

you should listt all tags like this to add them to the persistent list:

this is a drawer

I use the following chunk of elisp to create a dynamic block containing
a table where each row is a tag and number of use of that tag in the
file. Add the block to your org file and hit `C-c C-c` to expand it:

    #+BEGIN: tagblock
    #+END:

If you only want to count certain tags you can add a `:tags` option to
the block and to add a label to the resulting table use `:label`

    #+BEGIN: tagblock :tags ("tag1" "tag2" "tag3") :label tag-counts
    | tag1 | 2 |
    | tag2 | 4 |
    | tag3 | 8 |
    #+END:

With the `:todo` option, only entries with a todo state (either any or
in a list you specify) will be counted.

All the real work is done by the function `org-freq-count` which takes a
parameterized search string (the same as an agenda tags search) and
replaces `%s` in the search with each element of `targets`, counting the
number of matches. If `cmp` is given, it will be used as a comparison
function when sorting the output.

    (defun org-freq-count (search targets &optional cmp)
      (let ((cmp (if (functionp cmp)
                     cmp
                   (lambda (a b) nil))))
    
        (mapcar (lambda (x)
                  (list x (length (org-map-entries t (format search x) nil))))
                (sort
                 (delete-dups
                  (-filter #'stringp targets))
                 cmp)
                )
        ))
    
    (defun org--tagblock-all-tags ()
      (-filter #'stringp (-map #'car (append
                                      (org-get-buffer-tags)
                                      org-tag-alist
                                      org-tag-persistent-alist))))
    
    (defun org-write-freq-count (search targets name)
      (insert (s-concat
               (if name (insert (format "#+NAME: %s\n" name)))
               (mapconcat
                (lambda (x) (format "| %s | %s |" (nth 0 x) (nth 1 x)))
                (org-freq-count search targets)
                "\n")))
      (org-table-align)
      )
    
    (defun org-dblock-write:tagblock (params)
      (let ((todo (plist-get params :todo))
            (tags (or (plist-get params :tags) (org--tagblock-all-tags)))
            (label (plist-get params :label))
            (caption (plist-get params :caption))
            )
        (when caption (insert (format "#+CAPTION: %s\n" caption)))
        (org-write-freq-count (cond ((equal todo t)
                                     (format "%%s/%s" (mapconcat 'identity
                                                                 org-not-done-keywords
                                                                 "|"
                                                                 )))
                                    ((listp todo)
                                     (format "%%s/%s" (mapconcat 'identity
                                                                 todo
                                                            "|"
                                                            ))


<a id="org011becb"></a>

## Agenda Searching     :agenda:tagging:

Basically the search attaches only to things beneath a [headline, like a block](https://orgmode.org/worg/org-tutorials/advanced-searching.html).
To search for multiple terms you have to put `+` between the tearms, or you
can put this in your `init.el`

    (setq org-agenda-search-view-always-boolean t)

Then search the agenda with `org-agenda` which is:

-   `SPC o a` in Doom
-   `SPC a o` in Spacmacs

After getting a result of tags you can further filter the tags
by using backslash `\` (and maybe `TAB` on `Doom`) to further
match tags

<div class="notes">
<p>
Frustratingly this isn&rsquo;t recursive like my bash script <a href="file:///home/ryan/bin/tagFilter.sh">here</a> but the layout
is such that you can see what&rsquo;s going on if your eyes are good.
</p>

</div>

To concurrently filter tags use the `ESC SPC` transient state and use `ft` and
`fc` to filter by tag and category.

In Helm-Rifle the `C-c C-f` key sequence enters follow mode, in the agenda view
it&rsquo;s simply `F`, using `'` or `SPC` will only preview that one item. `RET` will
open that item and `TAB` will preview that item and take the point.

The `L` key will display the original date that a task occured
inside the agenda.

There&rsquo;s a lot you can do, [Read the Manual](https://orgmode.org/manual/Agenda-Commands.html).


<a id="org52de60d"></a>

# Inline Code


<a id="orga05aa79"></a>

## First Steps

First you have to activate languages, this is what I used:

    ;; Active Babel languages
    ;; Active Babel languages
    (org-babel-do-load-languages
       'org-babel-load-languages
        '((R          . t)
         (latex       . t)
         (python      . t)
         (gnuplot     . t)
         (java        . t)
         (sed         . t)
         (shell       . t)
         (mathematica . t)
         (emacs-lisp  . t)))

You need to specify how you want the code block to behave:

-   `:exports code`
    -   use this if you don&rsquo;t want the code evaluated (but want highlighting)
-   `: exports both`
    -   Code listing and result
-   `:exports results`
    -   Only the results of the code
-   `:exports none`
    -   The code just doesn&rsquo;t get exported

If you don&rsquo;t want something to evauluate set `:exports none`


<a id="org595e403"></a>

## Execute External Language

External languages can be executed by pressing `C-c C-c` and then pressing `y` for yes

    print(rnorm(3))

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-right" />
</colgroup>
<tbody>
<tr>
<td class="org-right">0.900968753791266</td>
</tr>


<tr>
<td class="org-right">0.0954723406079483</td>
</tr>


<tr>
<td class="org-right">-3.20877981827325</td>
</tr>
</tbody>
</table>

This can be handy for complicated things like:

    words <- tolower(scan("1.org", what="", na.strings=c("|",":")))
    t(sort(table(words[nchar(words) > 3]), decreasing=TRUE)[1:3])

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-right" />

<col  class="org-right" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-right">with</th>
<th scope="col" class="org-right">current</th>
<th scope="col" class="org-right">todo</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-right">59</td>
<td class="org-right">51</td>
<td class="org-right">49</td>
</tr>
</tbody>
</table>


<a id="org0b582c6"></a>

## Working with R     :R:diagrams:


<a id="orgbbc3ce8"></a>

### Integrating ESS Auto Complete     :R:AutoComplete:

first you need to add ESS to the spacemacs layers<sup><a id="fnr.5" class="footref" href="#fn.5">5</a></sup>.

1.  Using ESS

    once it&rsquo;s installed load any `.R` file (preferably in a new frame with `C-x 5 C-f` and it should just work<sup>tm</sup> and be in `ESS[R]` mode, if not activate that mode by using `M-x r-mode`.
    
    Next you will want to opon a REPL console underneath, which should be in `iESS` mode with the name **R**, do this by using `M-x R`, it will ask for a project location / directory, this is annoying and 90% of the time you&rsquo;re happy to have that as the working directory location of the original file, in order for that to happen put the following in your `.emacs.d/init.el`:
    
        ;R Binding for <-
        (setq-default dotspacemacs-configuration-layers '((ess :variables
                                                               ess-assign-key "\M--")))
        
        ;Set starting project directory to location of buffer =M-x pwd=
        ;https://ess.r-project.org/Manual/ess.html#Customizing-startup
        (setq ess-ask-for-ess-directory nil)
    
    if you want to open a seperate frame use `SPC w F` (remember a frame is an external X window and a window inisde by the Emacs language) and if you want to have the source code scroll over multiple panes use `follow-mode` by typing `SPC w f`

2.  Using ESS inside Org

    So one way is to just open an indirect buffer and/or change the mode, but that&rsquo;s a little painful because sometimes the point will be moved away and `C-o` / `g;` don&rsquo;t always work.
    
    another way is to switch to the buffer for that chunk using `org-edit-special` which is mapped to `C-c '` / `, '` , this works for other environments (read `C-h f org-edit-special`), when it&rsquo;s used in src code it will take copy code to a seperate buffer and when you finish by using `M-Ret '` it will copy it back, so here I&rsquo;ve used it to make a plot of *MtCars*:
    
        library(tidyverse)
        mtcars <- as_tibble(mtcars)
        myplot <-  ggplot(mtcars, aes(x = disp, y = mpg, col = hp, shape = as.factor(cyl))) +
          geom_point() +
          theme_classic() +
          labs(col = "HorsePower", shape = "Cylinders")
        myplot
    
    ![img](Example9832.png)
    
    Make sure to use the header arguments as shown above, there was a change to the `org-mode`
    version that broke this recently, now `results: ouput graphics file` is specifically
     required.<sup><a id="fnr.6" class="footref" href="#fn.6">6</a></sup> 
    
    1.  Naming plots     :ATTACH:
    
        Unfourtunately, every single code block MUST be named in order for this to work, what can happen is that using pandoc to export `*.rmd` &#x2013;> `*.md` includes a link to a path of an image and you mistake that as a `#+RESULTS:`, it will even appear under the `#+RESULTS:` because the results are blank, blank because the function gives no output, but, that&rsquo;s still just a link to a file and nothing is generated, easy mistake to make.
        
        You can set a global setting using
        
            #+PROPERTY: header-args: R :results output  :session *R* :dir ../
        
        but if you set `:file temp.png` globally every file will overwrite every other file, this is fairly undesirable, so instead use something like this:
        
            (defconst our-charset "0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz")
            (defconst our-charset-length (length our-charset))
            
            (defun random-string (&optional max-length min-length)
              "Generate a random string."
              (let (string)
                (dotimes (_i (+ (random (- (or max-length 10) (or min-length 5) -1)) (or min-length 5)))
                  (push (aref our-charset (random our-charset-length)) string))
                (concat string)))
            
            (random-string)
        
        And then just feed that to the function like this:
        
            #+begin_src R :file (random-string)  :results output graphics :exports results
            plot(rnorm(10))
            #+end_src
        
        <kDDcK>
        
        And so then the idea is that you would just specify that in the header with something like this:
        
            #+PROPERTY: header-args:R :exports both :session *R* :dir ./ :file (random-string) :results output graphics
        
        This however has the downside that EVERYTHING evaluated will be exported unfourtunately.
        
        Now the problem with this is that if you have similar file names in the same directory it won&rsquo;t work, an easy solution is either generating a[ random-string](https://common-lisp.net/project/bese/docs/arnesi/html/api/function_005FIT.BESE.ARNESI_003A_003ARANDOM-STRING.html) or using the file name
        The best about this though is that you can even split the window up to get an ***R*** `iESS` console underneath, follow mode on the right and the `org-edit-src-code` in one of the corners.
    
    2.  Working Directories
    
        Strangely `setwd()` won&rsquo;t persist in `org-mode`, instead it is necessary to set the working directory for every code block, this clearly isn&rsquo;t ideal so instead you can use:
        
            #+PROPERTY: header-args:R  :session *R* :dir "../"
        
        actually don&rsquo;t use this either, this causes problems as well, tread `org` just like `rmd` and always have the file in it&rsquo;s working directory, otherwise images that get put together upon export don&rsquo;t work properly.


<a id="org477a827"></a>

### Plotting     :ggplot2:

You can produce plots as well, but what gets complicated is using the correct
options in the header, they are reasonably self explanatory though:

-   Although observe that for the the `:results` argumnet the following must be

listed:

-   `output`
-   `graphics`
    -   This is necessary for `ggplot2`
-   `file`

for example the following code:

    #+BEGIN_SRC R :cache yes :exports both :results output graphics :file test.png
      library("ggplot2")
      ggplot(iris, aes(x = Sepal.Width, y = Sepal.Length, color = Species)) +
      geom_point() +
      theme_bw()
    \#+END_SRC

will produce the following plot and list the code appropriately:

    #+BEGIN_SRC R :cache yes :exports both :results output graphics :file ./test.png
      library("ggplot2")
      ggplot(iris, aes(x = Sepal.Width, y = Sepal.Length, color = Species)) +
      geom_point() +
      theme_bw()

1.  MatPlotLib in Python

    To do a similar thing in python look at this example:
    
        %matplotlib inline
        #+begin_src python
        # m is colours
        # n is number of folds
        # Z is number for border
        # cx is a function to transform the variables
        def main(m, n, z, cx):
            import numpy as np
            import matplotlib.pyplot as plt
        
            # Make the Empty Matrix
            mat = np.empty([2**n+1, 2**n+1])
            main.mat = mat
        
            # Fill the Borders
            mat[:,0] = mat[:,-1] = mat[0,:] = mat[-1,:] = z
        
            # Colour the Grid
            colorgrid(0, mat.shape[0]-1, 0, mat.shape[0]-1, m)
        
            # Plot the Matrix
            plt.matshow(mat)
        #    plt.savefig("Persian-Recursion")
        #    return "Persian-Recursion"
        
        
        
        # Define Helper Functions
        def colorgrid(l, r, t, b, m):
            # print(l, r, t, b)
            if (l < r -1):
                ## define the centre column and row
                mc = int((l+r)/2); mr = int((t+b)/2)
        
                ## Assign the colour
                main.mat[(t+1):b,mc] = cx(l, r, t, b, m)
                main.mat[mr,(l+1):r] = cx(l, r, t, b, m)
        
                ## Now Recall this function on the four new squares
                        #l r   t   b
                colorgrid(l, mc, t, mr, m)    # NW
                colorgrid(mc, r, t, mr, m)    # NE
                colorgrid(l, mc, mr, b, m)    # SW
                colorgrid(mc, r, mr, b, m)    # SE
        
        def cx(l, r, t, b, m):
            new_col = (main.mat[t,l] + main.mat[t,r] +  main.mat[b,l] + main.mat[b,r]) % m
            return new_col.astype(int)
        
        main(5,6, 1, cx)
    
    or this one:
    
        #+BEGIN_SRC ipython :session :ipyfile /tmp/image.png :exports both :results raw drawer
          plt.hist(np.random.randn(20000), bins=200)
        #+END_SRC
    
        plt.hist(np.random.randn(20000), bins=200)
    
    1.  SVG and PNG
    
        The `png` always comes out blurry so put `usepackage{svg}` in the \LaTeX header
        and use something like this: in order to get out a high res image that scales:
        
            %matplotlib inline
            %config InlineBackend.figure_format = 'svg'
            %matplotlib inline
            import matplotlib.pyplot as plt
            import random
            import numpy as np
            plt.hist(np.random.randn(20000), bins=200)
        
        ![img](media/ipython-example.svg "Output produced by listing with 9 folds")

2.  GNUPLOT

    ,#+begin<sub>src</sub> gnuplot
    
        complex(x,y) = x*{1,0}+y*{0,1}
        mandel(x,y,z,n) = (abs(z)>2.0 || n>=10) ? \
                          n : mandel(x,y,z*z+complex(x,y),n+1)
        
        set xrange [-0.5:0.5]
        set yrange [-0.5:0.5]
        set logscale z
        set isosample 50
        set hidden3d
        set contour
        a= -0.37
        b= -0.612
        splot mandel(a,b,complex(x,y),0) notitle


<a id="orgc8b6b04"></a>

## DONE Is there an easy way to convert rmd to org?

<span class="timestamp-wrapper"><span class="timestamp">&lt;2019-11-13 Wed&gt;</span></span>


<a id="orgfb5610a"></a>

## DONE Syntax Highlighting

By default the r-code doesn&rsquo;t have synatx highlighting.
In order to get syntax highlighting in LaTeX export you need to either use the *minted* or *listings* package, to use the minted package specify the following in your `~/.emacs.d/init.el`:

    (require 'org-latex)
    (setq org-export-latex-listings 'minted)
    (add-to-list 'org-export-latex-packages-alist '("" "minted"))


<a id="org4231a35"></a>

### Would it be worth using org-mode to manage code notes over boostnote?

Because boostnote is just open source `*.md` files, switching out is no drama, given how good `org-mode` is i&rsquo;d probably be better off just abandoning *Notable* all togethr and using *Boostnote* for want of the features (and hey open source) and use org-mode for everything else.

1.  Using Org-Mode to replace Boostnote

    <table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
    
    
    <colgroup>
    <col  class="org-left" />
    
    <col  class="org-left" />
    </colgroup>
    <tbody>
    <tr>
    <td class="org-left">Pros</td>
    <td class="org-left">cons</td>
    </tr>
    
    
    <tr>
    <td class="org-left">+ Closer to Terminal and Code</td>
    <td class="org-left">+ Less User Friendly</td>
    </tr>
    
    
    <tr>
    <td class="org-left">+ Easier to switch into because always open and bookmarks/recents</td>
    <td class="org-left">+ tags aren&rsquo;t as nice/usable</td>
    </tr>
    
    
    <tr>
    <td class="org-left">+ Way better text editing</td>
    <td class="org-left">&#xa0;</td>
    </tr>
    
    
    <tr>
    <td class="org-left">+ Can open fles externally</td>
    <td class="org-left">&#xa0;</td>
    </tr>
    
    
    <tr>
    <td class="org-left">+ Brings all notes together</td>
    <td class="org-left">&#xa0;</td>
    </tr>
    </tbody>
    </table>


<a id="org8103213"></a>

## DONE How do I include ggplot inline?     :R:

1.  ESS or R-org

    A really good tutorial on using ***R*** in org-mode is [org-mode *Worg*](https://orgmode.org/worg/org-tutorials/org-R/org-R.html) tutorials


<a id="orge80a4a1"></a>

## DONE Java Example

Write an example of java code

    // This is my first Java Program.
      public class MyFirstProg{
          public static void main(String[] args) {
              System.out.println("I'm a Program!");
          }
      }


<a id="orgf6f4381"></a>

## Syntax Highlighting

Syntax highlighting corresponds to major modes in vim,
for example there is a `python-mode`, because the word `python`
is suffixed with suffixed with `-mode`<sup><a id="fnr.7" class="footref" href="#fn.7">7</a></sup>  a `python` block should be started by
using `#+begin_src python`, like wise we would use  `R-mode` to edit *****R*****,
`vim` is a bit of an exception in this way, because [highlightJS](https://highlightjs.org/static/demo/) refers to it
as `vimscript` whereas *Emacs* uses `vimrc`<sup><a id="fnr.8" class="footref" href="#fn.8">8</a></sup>.

It&rsquo;s important to only evel call it `vim`, because the `minted`
package in LaTeX will fail if it does not recognize the language,
instead the appropriate avenue is instead to have `org` accept that
 we need to call the environment `vim` even if the mode is `vimrc-mode` <sup><a id="fnr.9" class="footref" href="#fn.9">9</a></sup>:

    (add-to-list 'org-src-lang-modes (cons "vim" 'vimrc))

If you do use `#+begin_src vimrc` there should be syntax highlighting inside
`org-mode` and inside the export.


<a id="org4f99de7"></a>

# Outshine Mode

Outshine mode is nice, previously orgstruct was built in [As discussed in this StackExchange Answer](https://emacs.stackexchange.com/a/8065/26057) but it&rsquo;s since been removed and replaced with [Outshine](https://orgmode.org/Changes.html)


<a id="orgd2b37f8"></a>

## TODO Need to add this to my elisp

Add it to doom with this <a id="org61d254b"></a>:

    ;; *** outline
    (use-package! outshine :load-path "~/.doom.d/local/"
      :hook ((outline-minor-mode . outshine-mode))
      :config
      (map! :map outline-minor-mode-map
    ;;        :nm [tab] #'outline-cycle
            :nm [backtab] #'outshine-cycle-buffer))
    
    ;; (define-key outline-minor-mode-map [tab] (lambda () (interactive) (+fold/toggle)))
    (define-key outline-minor-mode-map [tab] (lambda () (interactive) (outshine-cycle)))
    (define-key outline-minor-mode-map [backtab] (lambda () (interactive) (#'outshine-cycle-buffer)))


<a id="org962ca36"></a>

# TODO Can I integrate Stack Exchange with Emacs?


<a id="org6f5c5ec"></a>

# DONE Including Tikz Plots     :diagrams:Buffers:

CLOSED: <span class="timestamp-wrapper"><span class="timestamp">[2019-11-13 Wed 11:53]</span></span>


<a id="org4936422"></a>

## DONE Using a tikz picture

I could only get this to work in HTML following the example from [UCL](https://www.homepages.ucl.ac.uk/~ucahjde/blog/tikz.html) there&rsquo;s reference to this [orgmode.org/worg](https://orgmode.org/worg/org-contrib/babel/languages/ob-doc-LaTeX.html#orgad1adb5) tutorial on LaTeX in org where the idea is:

-   If it&rsquo;s exported to HTML
    -   then convert the tikz to zvg and insert the svg&rsquo;s
-   else if it&rsquo;s exported to LaTeX
    -   just include the LaTeX
-   else just leave it raw
-   the `t` backend refers to the inline org-mode *toggling*
    -   I just remember it as *toggling* because I can find no documentation on it.
    -   it is always triggered so you must put it at the end or it won&rsquo;t work properly

but it only works in HTML so far. The `+#_Header: = arguments are the same as putting them on the line =#+BEGIN_SRC`, but that would be a really long line.

In order to use the if then statements as I have add the following to the `~/.emacs.d/init.el` file:

    (setq org-babel-latex-htlatex "htlatex")
    (defmacro by-backend (&rest body)
      `(case (if (boundp 'backend) (org-export-backend-name backend) nil) ,@body))


<a id="Using-Tikz-Accross-Formats"></a>

### Making it work across formats

So the trick is, execute this tikz like this with `C-c C-c`:

    #+LATEX_HEADER: \usepackage{tikz}
    #+HEADER: :headers '("\\usepackage{tikz}")
    #+HEADER: :fit yes :imoutoptions -geometry 400 :iminoptions -density 600
    #+header: :file (by-backend (html "./img/dosage.svg") ) :imagemagick yes
    #+header: :results (by-backend (pdf "latex")  (html "raw") (t "raw"))
    \#+BEGIN_SRC latex  :file (by-backend (t "./img/dosage.svg") ) :imagemagick yes
    \begin{tikzpicture}[domain = 0:10, scale = (2/3)]
      \clip (-1,-1) rectangle (12,12);
      \draw[->, thick] (0,0) -- (0,10) node[right] {$C$ {\scriptsize nmol $\cdot  $ L$^{-1}$}};
      \draw[->, thick] (0,0) -- (10, 0) node[right] {$t$ };
      \draw[] [out=270, in = 180]  (0,5) to (3,2);
      \draw[dashed] (3,2)--(3,5);
      \draw[] [out=270, in=180] (3,5) to (6,3) ;
      \draw[dashed] (6,3)--(6,6);
      \draw[] [out=270, in=180] (6,6) to (9,4) ;
      \draw[dashed] (9,4)--(9, 7);
      \draw[ ] [out=270, in=180] (9,7) to (12,4);
      \draw[dotted]  (0,7)--(12,7) node[below left] {$C_n = H$};
      \draw[dotted]  (0,4)--(12,4) node[below left] {$R_\infty = L$};
      \node [left] at (0,5) {$C_0$};
      \draw[<-> ] (0.4,4)--(0.4,7) node[below right] {\tiny $C_0 = H-L$};
    \end{tikzpicture}
    \#+END_SRC

Then that should create, below it a section that looks like this:

    #+RESULTS:
    [[file:./img/dosage.svg]]

This results section will inline preview but it won&rsquo;t get pulled in by an export process, so now that the inline preview is done we can take the line immediately preceeding the code fence and <del>&rsquo;comment it out&rsquo;</del> delete it (comments, either `#_` or = or whatever DO NOT WORK between header and source so do not use it. you should delete the line after `latex` that matches:

    :file (by-backend (t "./img/dosage.svg") ) :imagemagick yes

And then we have tikz that compiles in LaTeX and an SVG that will &rsquo;just work<sup>tm</sup>&rsquo; when exporting to HTML and that can be leveraged for other exports.


<a id="org5b9e28e"></a>

### Example Tikz Export     :Tikz:

    #+LATEX_HEADER: \usepackage{tikz}
    #+HEADER: :headers '("\\usepackage{tikz}")
    #+HEADER: :fit yes :imoutoptions -geometry 400 :iminoptions -density 600
    #+header: :file (by-backend (html "./img/dosage.svg") (odt "./img/dosage.svg") (txt "./img/dosage.svg") (md "./img/dosage.svg")) :imagemagick yes
    #+header: :results (by-backend (pdf "latex")  (html "raw") (odt "raw") (txt "raw") (md "raw") (t "raw"))
    #+BEGIN_src
    \begin{tikzpicture}[domain = 0:10, scale = (2/3), draw = purple, text= pink]
      \clip (-1,-1) rectangle (12,12);
      \draw[->, thick] (0,0) -- (0,10) node[right] {$C$ {\scriptsize nmol $\cdot  $ L$^{-1}$}};
      \draw[->, thick] (0,0) -- (10, 0) node[right] {$t$ };
      \draw[] [out=270, in = 180]  (0,5) to (3,2); % node[right] {\scriptsize \(\left( t_{\textit{min}}, c_{\textit{min}} \right)\)};
      \draw[dashed] (3,2)--(3,5);
      \draw[] [out=270, in=180] (3,5) to (6,3) ;
      \draw[dashed] (6,3)--(6,6);
      \draw[] [out=270, in=180] (6,6) to (9,4) ;
      \draw[dashed] (9,4)--(9, 7);
      \draw[ ] [out=270, in=180] (9,7) to (12,4);
      \draw[dotted]  (0,7)--(12,7) node[below left] {$C_n = H$};
      \draw[dotted]  (0,4)--(12,4) node[below left] {$R_\infty = L$};
      \node [left] at (0,5) {$C_0$};
      \draw[<-> ] (0.4,4)--(0.4,7) node[below right] {\tiny $C_0 = H-L$};
    \end{tikzpicture}
    #+END_src

which returns:

    #+RESULTS:
    [[file:./img/dosage.svg]]

and it will create below something that says `#+RESULTS: file:./img` which should also inline display the image, now you can freely delete everything after `latex` in the header and it will work in all exports and you&rsquo;ll get to have the inline display, just copy it back if you want it again.


<a id="org470b16e"></a>

### Example 2

    #+LATEX_HEADER: \usepackage{tikz}
    #+HEADER: :headers '("\\usepackage{tikz}")
    #+HEADER: :fit yes :imoutoptions -geometry 400 :iminoptions -density 600
    #+header: :file (by-backend (html "./img/contour.svg") (odt "./img/contour.svg") (txt "./img/contour.svg") (md "./img/contour.svg")) :imagemagick yes
    #+header: :results (by-backend (pdf "latex")  (html "raw") (odt "raw") (txt "raw") (md "raw") (t "raw"))
    #+BEGIN_src latex
    \begin{tikzpicture}
    \draw[->] (-3,0) -- (-2,0) arc[radius=0.5cm,start angle=-180,end angle=0] (-1,0) -- (1,0) arc[radius=0.5cm,start angle=180,end angle=0] (2,0) -- (3,0);
    \filldraw (-1.5,0) circle[radius=1mm];
    \filldraw (1.5,0) circle[radius=1mm];
    \end{tikzpicture}
    #+END_src

which returns:

    #+RESULTS:
    [[file:./img/contour.svg]]

1.  Snippet     :Snippets:

    Using the tutorial [here](https://jaketrent.com/post/code-snippets-spacemacs/) and the [*YaSnippets* manual](http://joaotavora.github.io/yasnippet/snippet-expansion.html) I turned this into a snippet in [orgmode/plot](file:///home/ryan/.emacs./private/snippets/orgmode/plot). The snippet can be triggered by typing in `plot` and positinioning the cursor over and then running `M-x yas-expand` / `:yas-expand` / `<SPC> <SPC> yas-expand`.
    
    -   If the minor mode is enabled with `M-x yas-minor-mode` then I think you could just press `TAB` / `M-/` after plot and then jumping to the next field with `M-s-/`
    -   

2.  Exporting Guidelines

    If the svg files get deleted, they won&rsquo;t show up in exports, but they can be regenerated by moving the line back up and recompiling the tikz, the thing is, this code was intended to be fool-proof automatic, but it&rsquo;s not, and it might be more complicated that it needs to be, maybe just let sleeping dogs lie though.


<a id="org535ddfe"></a>

## Previewing inside Org-Mode

Put this inside the .vimrc and you should be able to preview tikz in place.

I&rsquo;ve found however that it only works with [texfrag-mode](https://github.com/TobiasZawada/texfrag), which is significantly faster and better behaved (with respect to themes and zoom) than the `org-latex-preview-fragment` anyway, so just use that. <sup><a id="fnr.10" class="footref" href="#fn.10">10</a></sup>

    (add-to-list 'org-latex-packages-alist
                 '("" "tikz" t))
    (eval-after-load "preview"
      '(add-to-list 'preview-default-preamble "\\PreviewEnvironment{tikzpicture}" t))

Without the png being embedded it won&rsquo;t work in HTML though, only LaTeX, that&rsquo;s what section [18.1.1](#Using-Tikz-Accross-Formats) is concerned with.

Then in theory you should be able to use something like `C-c C-x C-l` on othe below code to have it work:

\begin{tikzpicture}
% horizontal axis
\draw[->] (0,0) -- (6,0) node[anchor=north] {$f/f_N$};
% labels
\draw	(0,0) node[anchor=north] {0}
		(2,0) node[anchor=north] {1}
		(4,0) node[anchor=north] {2};
% ranges
\draw	(1,3.5) node{{\scriptsize Constant flux}}
		(4,3.5) node{{\scriptsize Field weakening}};

% vertical axis
\draw[->] (0,0) -- (0,4) node[anchor=east] {$U_s,\varPsi_s$};
% nominal speed
\draw[dotted] (2,0) -- (2,4);

% Us
\draw[thick] (0,0) -- (2,2) -- (6,2);
\draw (1,1.5) node {$U_s$}; %label

% Psis
\draw[thick,dashed] (0,3) -- (2,3) parabola[bend at end] (6,1);
\draw (2.5,3) node {$\varPsi_s$}; %label
\end{tikzpicture}


<a id="org5441acd"></a>

## Previewing inside Markdown


<a id="upmath"></a>

## Upmath

The Upmath Script can be embedded in markdown by doing something like
this:

\#+BEGIN<sub>html</sub>
  <p>
  <script src=&ldquo;<https://i.upmath.me/latex.js>&rdquo;></script>
  $$

\begin{tikzpicture}
...
\end{tikzpicture}

  $$
  </p>
\#+END<sub>HTML</sub>

Just make sure to wrap everything in `<p>` `</p>` tags, so for example in the markdown put something like this

    <p>
    <script src="https://i.upmath.me/latex.js"></script>
    cool tikz-pictures:
    $$
    \usetikzlibrary{decorations.pathmorphing}
    \begin{tikzpicture}[line width=0.2mm,scale=1.0545]\small
    \tikzset{&gt;=stealth}
    \tikzset{snake it/.style={-&gt;,semithick,
    decoration={snake,amplitude=.3mm,segment length=2.5mm,post length=0.9mm},decorate}}
    \def\h{3}
    \def\d{0.2}
    \def\ww{1.4}
    \def\w{1+\ww}
    \def\p{1.5}
    \def\r{0.7}
    \coordinate[label=below:$A_1$] (A1) at (\ww,\p);
    \coordinate[label=above:$B_1$] (B1) at (\ww,\p+\h);
    \coordinate[label=below:$A_2$] (A2) at (\w,\p);
    \coordinate[label=above:$B_2$] (B2) at (\w,\p+\h);
    \coordinate[label=left:$C$] (C1) at (0,0);
    \coordinate[label=left:$D$] (D) at (0,\h);
    \draw[fill=blue!14](A2)--(B2)-- ++(\d,0)-- ++(0,-\h)--cycle;
    \draw[gray,thin](C1)-- +(\w+\d,0);
    \draw[dashed,gray,fill=blue!5](A1)-- (B1)-- ++(\d,0)-- ++(0,-\h)-- cycle;
    \draw[dashed,line width=0.14mm](A1)--(C1)--(D)--(B1);
    \draw[snake it](C1)--(A2) node[pos=0.6,below] {$c\Delta t$};
    \draw[-&gt;,semithick](\ww,\p+0.44*\h)-- +(\w-\ww,0) node[pos=0.6,above] {$v\Delta t$};
    \draw[snake it](D)--(B2);
    \draw[thin](\r,0) arc (0:atan2(\p,\w):\r) node[midway,right,yshift=0.06cm] {$\theta$};
    \draw[opacity=0](-0.40,-0.14)-- ++(0,5.06);
    \end{tikzpicture}
    $$


<a id="org7656a81"></a>

## TikzJaz

You could have the HTML deal with the raw TikZ, this would be way simpler and something I should consider, all I would need to do is add a few lines to the header of a HTML, which I could achieve with `#+HTML_HEADER:`, a corresponding package is [TikzJax](https://github.com/kisonecat/tikzjax), I&rsquo;m not going to pursue this for the moment though because if I need to, on occasion, export to markdown or ODT, I&rsquo;ll be stuck without SVGs.
Probably refer to <Tikz-in-Markup.md>


<a id="orgea9300a"></a>

# Set up a workflow

Images

-   How do I do screenshots
-   How do I do ipad drawings?
-   How do I do drawings from inkscape
-   How do I just do outright tikz?


<a id="orgc432735"></a>

## DONE Install the /Prelude/Starter Kit.


<a id="orgd9250e5"></a>

## DONE How do I deal with headlines?

use `M-left/right` to demote and promote them, use `M-up/down` to move them.
To do items may be cycled by using =S-left/right.


<a id="orgd9f12eb"></a>

### Moving Headlines


<a id="orga8640ce"></a>

### Demoting and promoting headlines


<a id="org8692ac5"></a>

## DONE Can I Hide all the ToDo Tags from export?

Let&rsquo;s say that I use the todo tags to manage my notes and dates etc.
Could I hide that from an export?
[It looks like no](https://lists.gnu.org/archive/html/emacs-orgmode/2008-12/msg00078.html) but I could filter the tree and just toggle the state with `t`, export it, and not save the buffer, a hacky work arround but sufficient for now, I could also just use `regex`


<a id="org8504a94"></a>

## DONE Using Emacs for Notes


<a id="orgdc39569"></a>

### DONE Browsing all ToDO item     :Todo:

If you&rsquo;ve added a file to the agenda-variable with `C-c [` all todo items in the agenda can be searched using `<Spc> m a t`


<a id="org0ba17ea"></a>

### DONE Navigating a file

How do I jump to the top of a headline so that I can use `TAB` to fold it ?
You can use `C-c C-f=/=C-c C-n` / `gj` / `gl` will go forward headlines and `C-c C-b` / `gk` / `g;` / `C-c C-p` will go back headlines.
I have remapped these to `z k` and `z j` respectively

1.  Folding

    How do I fold and unfold the entire document?

2.  Marking Location

    Can I still use `m CHAR` to mark a location and jump back to it?

3.  Frames and windows

    often you will want to use `<SPC> m b` | `, b` to open an indirect buffer for items beneath a headline, it will then open a second window below that is out of focus `C-w C-w` / `C-x o` / `<SPC> w w` / `M-m w w` can be used to pull that window into focus (or any window with `SPC <NUM>` and then that window can be maximized with `C-x 1` / `<SPC> w m`

4.  Finding Shortcuts     :Buffers:

    If you&rsquo;re using spacemacs and you know a single shortcut it isn&rsquo;t usually difficult to find more shortcuts:
    
    1.  Switch to fullscreen
    2.  Move to a headline and press `, b`
    3.  Slowly enter the key-sequence `C-x`
    4.  Observe that the option `o` corresponds to the function `maximize-buffer`
    5.  Press `C-g` to clear out of the *minibuffer*
    6.  Press `<SPC> <SPC>` / `M-x` and type in `maximize-bu`
    7.  At or around the top should be the text `spacemacs/toggle maximize-buffer (M-m w m)`
    8.  Usually spacemacs will map `SPC` to `M-m` and in this case the corresponding shortcut is indeed `<SPC> w m`, if however it wasn&rsquo;t there&rsquo;s *Google* because you have the corresponding command.
    
    It&rsquo;s also possible to switch buffers with `<SPC> b n`.
    
    Listing buffers is weird, if you use `C-x b` / `:ls` you can just start typing in the file name, but if you get up the list of buffers with `C-x C-b` it won&rsquo;t take focus which is really annoying.
    
    press `<SPC> <SPC>` / `M-x`


<a id="org6006533"></a>

### DONE Attaching files     :Attachments:

Attachments are really cool, they can be copied or symlinked using  `<SPC> m i a`, that&rsquo;s even cause to give up on dropbox, the file can also just be linked to.

If you want to just link the file, open the org in vim and then use `fzf`.

fzf can be enabled in spacemacs using the  [AshyIsMe/fzf-spacemacs-layer](https://github.com/AshyIsMe/fzf-spacemacs-layer)

Also most `emacs` users recommend just using `projectile`

My preferred method is to use `fzf` inside `ranger` and then use `y p` to copy
the path, make sure you use `apt` to install `xsel` first though.


<a id="org90dda5f"></a>

### DONE Reading an Emacs File

-   How do I fold a section rather than the whole thing?
-   To fold the whole thing I can use `S+TAB+` which is analogous to `zr` and `zm` in vim but it cycles through


<a id="orgca44cfa"></a>

### DONE Use Vim Can I create a keybinding to open the file or buffer in *Vim*?     :vim:


<a id="orgd460214"></a>

### DONE How to mark lines just like in vim?

Using the bookmarks shortcuts are amazing, refer to them
in[ *Spacemacs* Documentation](https://github.com/syl20bnr/spacemacs/blob/master/doc/DOCUMENTATION.org#buffers-and-files), basically hit `<SPC> f b` and you can create and jump to bookmarks across and within files.

-   Bookmarks can be deleted with ,<sup><a id="fnr.11" class="footref" href="#fn.11">11</a></sup>
    -   `C-d`
-   Opened in another frame (i.e. an entirely new X Window)
    -   `C-c C-o`
-   Opened in anotgher window (i.e. internal to *Emacs*
    -   `C-c o`


<a id="org22ee6b5"></a>

## DONE Opening Current File in vim

-   Is there a way to bring my bindings into space macs?
    -   Probably, but it&rsquo;s a lot of work when you can just use both programs with no loss.

The binding (`C-c o` in *Prelude* and `Spc f 0` in *Spacemacs*
 will open the current file in an external editor (I&rsquo;m not sure
 if the file or the buffer tbh) just make sure the system has
 default editor as gvim  and that *gvim* is set to read the
 correct vimrc and your set, just remember to call `PlugUpdate`.
 Pure vim stopped working for me recently, I think it&rsquo;s getting
 trapped by the emacs terminal

I&rsquo;ve found two solutions for opening the current buffer in vim,
 on on the [*Emacs Wiki*](https://www.emacswiki.org/emacs/vim-current-buffer) which causes *Emacs* to crash and another
 one on [*Stack Exchange*](https://stackoverflow.com/a/52587681) that works flawlessly and remembers the line number:

    (defun my-open-current-file-in-vim ()
      (interactive)
      (async-shell-command
       (format "gvim +%d %s"
           (+ (if (bolp) 1 0) (count-lines 1 (point)))
           (shell-quote-argument buffer-file-name))))

If you want to use kitty terminal just specify `kitty` and
 avoid the popup <sup><a id="fnr.12" class="footref" href="#fn.12">12</a></sup> change it to `call-process-shell-command`:

    (defun my-open-current-file-in-vim ()
     (interactive)
     (call-process-shell-command
                                           ;  (format "gvim +%d %s"
      (format "~/.local/kitty.app/bin/kitty -e nvim +%d %s"
              (+ (if (bolp) 1 0) (count-lines 1 (point)))
              (shell-quote-argument buffer-file-name))))

Maybe later having something for notepad/vim etc. would be nice but it&rsquo;s pretty simple to just open stuff from vim win `:gedit "%"` and remapping that with `autocmd BufEnter *.org :map <f12> :w<cr>:!gedit "%" <Enter>`.

Actually it might have been `C-u C-c o`

Also to open a new line (i.e. `o` in vim) use `S-Enter`


<a id="org157ac43"></a>

### DONE Navigating Files

1.  DONE Moving to a previous location

    If you are following an internal link (i.e. a link to a target in the
    org-mode file), then org-mode automatically pushes the position in the
    mark-ring before jumping.
    
    So, you follow a link with `C-c C-o`, then you can jump back with
    `C-c &`.<sup><a id="fnr.13" class="footref" href="#fn.13">13</a></sup>

2.  Recently closed

    Use the key sequence `SPC f r` for *\*<sub>F</sub><sub>\*</sub>ind* *\*<sub>R</sub><sub>\*</sub>ecent* file.


<a id="org3a6c00a"></a>

## DONE Exporting     :Style:

<a id="org5cebf22"></a>


<a id="orgbe43ef7"></a>

### DONE In Line References

In order to reference code blocks [using org-ref](https://emacs.stackexchange.com/questions/20947/how-to-reference-source-blocks-in-org-text) you need to install the
`org-ref` package by following the instructions on their [GitHub](https://github.com/jkitchin/org-ref), you need to add
a line to your `.emacs.d/.init.el` but then you should be able to do `M-x
package-list-packages` and find `org-ref` in order to install it.

[According to this post](https://emacs.stackexchange.com/questions/38457/name-is-ignored-unless-running-emacs-with-q) you need to set `org-latex-prefer-user-labels` to
`non-nil` in order to use the custom ID given in `#+NAME`. Refer to the help
with `C-h v org-latex-prefer-user-labels` and the setting can be toggled from
there, the reason for the default is if you multiply define a label or use wrong
syntax the latex won&rsquo;t generate.

I can&rsquo;t find a simple way to easily reference figures and source code
cross-reference wise or academic wise, this could take a very long time.

1.  Dedicated targets

    maybe an easier way to figure this out is by using a [Dedicated target (go to
    top)](#org5cebf22), and you can reference sections by using `[[Section Name]]`

2.  DONE I haven&rsquo;t figured out how to fix labels with HTML though

    I tried looking for `org-HTML-prefer-user-labels` but no luck, there might be something in the [Manual](https://orgmode.org/manual/HTML-Export.html#HTML-Export).


<a id="orgf058324"></a>

### DONE Markdown

I need to figure how to export as markdown without breaking the dam thing

1.  Markdown Preview Export in Emacs

    There will be no math, what I did was go to [This file](file:///home/ryan/.emacs.d/.local/straight/repos/markdown-mode/markdown-mode.el) and add to the function `markdown-add-xhtml-header-and-footer` and put an insert call to [the mathjax script](file:///home/ryan/DotFiles/Templates/Templates/mathjax):
    
        <script type="text/javascript" async
          src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.5/MathJax.js?config=TeX-MML-AM_CHTML">
        </script>")
    
    Soo all tother that function now reads like this:
    
        defun markdown-add-xhtml-header-and-footer (title)
          "Wrap XHTML header and footer with given TITLE around current buffer."
          (goto-char (point-min))
          (insert "<?xml version=\"1.0\" encoding=\"UTF-8\" ?>\n"
                  "<!DOCTYPE html PUBLIC \"-//W3C//DTD XHTML 1.0 Strict//EN\"\n"
                  "\t\"http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd\">\n\n"
                  "<html xmlns=\"http://www.w3.org/1999/xhtml\">\n\n"
                  "<head>\n<title>")
          (insert title)
          (insert "
        <script type="text/javascript" async
          src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.5/MathJax.js?config=TeX-MML-AM_CHTML">
        </script>")
        
          (insert "</title>\n")
          (unless (= (length markdown-content-type) 0)
            (insert
             (format
              "<meta http-equiv=\"Content-Type\" content=\"%s;charset=%s\"/>\n"
              markdown-content-type
              (or (and markdown-coding-system
                       (coding-system-get markdown-coding-system
                                          'mime-charset))
                  (coding-system-get buffer-file-coding-system
                                     'mime-charset)
                  "utf-8"))))
          (if (> (length markdown-css-paths) 0)
              (insert (mapconcat #'markdown-stylesheet-link-string
                                 markdown-css-paths "\n")))
          (when (> (length markdown-xhtml-header-content) 0)
            (insert markdown-xhtml-header-content))
          (insert "\n</head>\n\n"
                  "<body>\n\n")
          (when (> (length markdown-xhtml-body-preamble) 0)
            (insert markdown-xhtml-body-preamble "\n"))
          (goto-char (point-max))
          (when (> (length markdown-xhtml-body-epilogue) 0)
            (insert "\n" markdown-xhtml-body-epilogue))
          (insert "\n"
                  "</body>\n"
                  "</html>\n")


<a id="org5549b1a"></a>

### DONE Export as eMail with Math

The easiest way is to take the exported html and download it using an add
on (*SingleFile* Export) and then copy that html, which is now mathml, into
thunderbird, trying to convert mathjax to mathml without losing the inline
css is like trying to pull out teeth.

Telling Org to use math-ml doesn&rsquo;t work, Using SVG&rsquo;s don&rsquo;t get embedded inline,
and, I don&rsquo;t really want to use pandoc when I don&rsquo;t have to given that the
inline is so nice, if I did however I could probably do something like this:

    pandoc -s --self-contained input.org --toc  -c ~/.emacs.d/org-css/Killercup.css -o out.html

1.  Test Email

    So the quadratic formula is given by:
    
    \begin{align}
    x&= \frac{- b \pm \sqrt{b^2- 4ac} }{2a}
    \end{align}
    
    the geometric series is given by
    
    \begin{align}
    S_n &= \sum^{n - 1}_{i = 0 }   \left[ a\cdot  r^n \right] \\
    &= \frac{1- r^n}{1- r} \\
     \implies  \sum^{\infty}_{n= 0} &=   \frac{1- \lim_{n \rightarrow
     \infty}\left[ r^n \right]}{1- r}
    \end{align}


<a id="org887b218"></a>

### DONE Styles

1.  DONE HTML Styles

    I found this nice Trick [on Reddit](https://www.reddit.com/r/emacs/comments/3pvbag/is_there_a_collection_of_css_styles_for_org/https://www.reddit.com/r/emacs/comments/3pvbag/is_there_a_collection_of_css_styles_for_org/) (insert a link with `C-c C-l`)<sup><a id="fnr.14" class="footref" href="#fn.14">14</a></sup>, in order
    to have inline CSS upon export (rather than two files) put CSS files in
    `~/.emacs.d/org-css/ and run =toggle-org-custom-inline-style` in an org buffer
    associated with a file, it should now prompt you for a theme on the next HTML
    export if you use this code shown in [some-source-code](#some-source-code) <sup><a id="fnr.15" class="footref" href="#fn.15">15</a></sup>
    
    So I did an error once where it complained about citeproc being an invalid
    function, ifthat occurs just use `M-x package-install-file` to install
    `~/Dropbox/DotFiles/Spacemacs/Downloads/citeproc-org-0.2.2.tar` and that seems
    to just about fix it.

2.  done LaTeX Styles upon Export.

    I can, I believe, set up a custom package for a template (of course that means that I&rsquo;ll have to fix the style that I&rsquo;ve been using from Computer algebra) by specifying a header of the form `#+LATEX_HEADER: \usepackage{mystyle.sty}`.
    
    I need to fix my LaTeX file so it will play ball externally
    
    When exporting to latex you need to be careful with loading in svg&rsquo;s, you will need to load a corresponding package
    
    In order to enable the listings package in a pdf export use the following in your `~/.emacs.d/init.el`:
    
        (require 'ox-latex)
        
        (setq org-latex-listings t)
        (add-to-list 'org-latex-packages-alist '("" "listings"))
        (add-to-list 'org-latex-packages-alist '("" "color"))
    
    It&rsquo;s also important never to include footnotes or hyperlinks in headings, even math should be avoided because LaTeX will throw non-descriptive errors, also I believe you need to be careful using the word `LaTeX` and this should perhaps be enclosed in code tags or deilberately lowercased.
    
    the command `\LaTeX` should never be wrapped in `$$` or `\( \)` because otherwise LaTeX will crash and because it automatically changes upon export..
    
    Never include multi-line math in tables, that&rsquo;s another thing latex really doesn&rsquo;t like
    
    Try to avoid unicode because while it can maybe work with XeLaTeX, it doesn&rsquo;t work with listings and is simply not worth the headache.

3.  JavaScript

    A tonne of options for exporting with extended javascript are also at my disposal, look at the [Manual](https://orgmode.org/manual/JavaScript-support.html#JavaScript-support), most importantly is `view:content` and `view:info`, so for example:
    
        view:info toc:nil
        #+INFOJS_OPT: view:info toc:nil
    
    Once your in the html, use `i` to toggle the *Table of Contents*.
    
        ;; Put your css files there
        (defvar org-theme-css-dir "~/.emacs.d/org-css/")
        
        (defun toggle-org-custom-inline-style ()
          (interactive)
          (let ((hook 'org-export-before-parsing-hook)
                (fun 'set-org-html-style))
            (if (memq fun (eval hook))
                (progn
                  (remove-hook hook fun 'buffer-local)
                  (message "Removed %s from %s" (symbol-name fun) (symbol-name hook)))
              (add-hook hook fun nil 'buffer-local)
              (message "Added %s to %s" (symbol-name fun) (symbol-name hook)))))
        
        (defun org-theme ()
          (interactive)
          (let* ((cssdir org-theme-css-dir)
                 (css-choices (directory-files cssdir nil ".css$"))
                 (css (completing-read "theme: " css-choices nil t)))
            (concat cssdir css)))
        
        (defun set-org-html-style (&optional backend)
          (interactive)
          (when (or (null backend) (eq backend 'html))
         (let ((f (or (and (boundp 'org-theme-css) org-theme-css) (org-theme))))
              (if (file-exists-p f)
                  (progn
                    (set (make-local-variable 'org-theme-css) f)
                    (set (make-local-variable 'org-html-head)
                         (with-temp-buffer
                           (insert "<style type=\"text/css\">\n<!--/*--><![CDATA[/*><!--*/\n")
                           (insert-file-contents f)
                           (goto-char (point-max))
                           (insert "\n/*]]>*/-->\n</style>\n")
                           (buffer-string)))
                    (set (make-local-variable 'org-html-head-include-default-style)
                         nil)
                    (message "Set custom style from %s" f))
                (message "Custom header file %s doesnt exist")))))
    
    -   How to specify a template for LaTeX
    
    So turn my typical `LaTeX` template into a `\usepackage{}`

4.  DONE Create CSS files

    Take the CSS files and merge them with something bare bones to colour the ToDO tags

5.  Shortcuts

    Exporting can be performed by using the shortcut `<SPC> m e e=/=C-c C-e`.

6.  DONE use spacemacs     :Workflow:

    when using spacemacs the config file remains as `~/.emacs.d/init.el`, the default
     config for all *spacemacs* settings however becomes the `~/.spacemacs` file, which,
     by default, has all the default settings in it; it is important to note that spacemacs settings will only be respected in that template and in that very specific style of wrapping, so just open the file and edit the settings of the `elisp` in place.
    it&rsquo;s well worth [Reading the Documentation](http://spacemacs.org/layers/+emacs/org/README.html) because it also mentions things like support for `GitHub Flavoured Markdown`

7.  Changing Themes

    You can install a bunch of themes by installing the `themes-megapack` as documented [on the GitHub repo](https://github.com/syl20bnr/spacemacs/blob/master/layers/+themes/themes-megapack/README.org), but the only way to change a theme that I&rsquo;ve found is to use `<M-x spacemacs/helm-themes>`.
    
    You&rsquo;ll need to change the default theme at loading however, because, the \(LaTeX\) will come out wrong otherwise, like black on a white background etc.
    
    If however you go to the `.spacemacs` file and locate the string `List of themes` there will be a list of default themes, these can be cycled through using `<SPC> T n`.

8.  DONE Toggle status of `ToDo`

    So this will still work with `<s-Right>` but preferably do it with just `t`
    
    1.  dealing with fonts
    
        you will likely need to fix the font, there is a bug [Described here on *Github*](https://github.com/syl20bnr/spacemacs/issues/501#issuecomment-534865654) that requires the font size listed at approximately line 135 as:
        
            dotspacemacs-default-font '("Source Code Pro"
                                           :size 13
                                           :weight normal
                                           :width normal
                                           :powerline-scale 1.1)
        
        to `13.0` otherwise it doesn&rsquo;t set the font to *point* like it should and the value is entirely ignored, making debugging hard.
    
    2.  Enabling layers
    
        You will need to uncomment lines in order to enable modes like `org` and `markdown`


<a id="orgfb91234"></a>

## ReWrite Documents in Org-Mode     :Workflow:

Documents I may want to rewrite in `org-mode`


<a id="org59dd9ec"></a>

### All Stats


<a id="org4d79f58"></a>

### Convert and import all R-Work


<a id="org5b2dc56"></a>

### All NMR


<a id="orgacabc11"></a>

### All Abstract Algebra


<a id="orgd07700e"></a>

# Tips and Tricks with Org Mode


<a id="org6a3eb02"></a>

## Reading Mode

Try the following to get a really nice book-esque layout for *Emacs*:

    cd /home/ryan/Notes/Org/elegant-emacs
    emacs -q -l sanity.el -l elegance.el Splash.org &


<a id="orgfd1a3df"></a>

## Folding

Open a second window with `C-x 2` and swap between the windows with `C-x o` (for \*O\*ther), the other window can be scrolled by using `C-M v`, this is handy for having a second reference window.

The second window can be closed by using `C-x 1` (as in keep **1** window i&rsquo;m already in )


<a id="org83a9b67"></a>

## Working with ToDo/HeadLine/list items

You can add a new `TODO` item with `M-S RET`.
Using `M-up/down` a headlines may be moved, they may be demoted with `M-left/right`
Using `S-left/right` will toggle to do list items.


<a id="org095b5ef"></a>

### Folding

You can fold a headline by using TAB if you are on a headline, the fold level of the entire document may be toggled with `S-TAB`


<a id="orgf1d9d09"></a>

### Trees

Refer to <sup><a id="fnr.16" class="footref" href="#fn.16">16</a></sup>

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">Key Binding</th>
<th scope="col" class="org-left">Description</th>
<th scope="col" class="org-left">Description</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left"><code>SPC m S l</code></td>
<td class="org-left">org-demote-subtree</td>
<td class="org-left">Move Right</td>
</tr>
</tbody>

<tbody>
<tr>
<td class="org-left">= SPC m S h 	=</td>
<td class="org-left">org-promote-subtree</td>
<td class="org-left">Move Left</td>
</tr>
</tbody>

<tbody>
<tr>
<td class="org-left">= SPC m S k 	=</td>
<td class="org-left">org-move-subtree-up</td>
<td class="org-left">Move UP</td>
</tr>
</tbody>

<tbody>
<tr>
<td class="org-left">= SPC m S j 	=</td>
<td class="org-left">org-move-subtree-down</td>
<td class="org-left">Move Down</td>
</tr>
</tbody>
</table>


<a id="org54fec3b"></a>

## Note Taking Guidlines     :Workflow:


<a id="orga48899d"></a>

### Links

You can create a link by using `C-c C-l` and I think `C-u C-c C-l` will attach an internal link


<a id="org39e6c78"></a>

## Exporting Org to Markdown

You should customize org-export-backends and enable the markdown backend.
That&rsquo;s: M-x customize-option and then org-export-backends and then arrow down to the checkbox to the left of &rsquo;md&rsquo; and press enter to enable it (or just click on it, if running emacs grqAphically). Then arrow back up and over to &rsquo;Apply and Save&rsquo; (or click on it)


<a id="orgc36bf23"></a>

## Including LaTeX Fragments     :LaTeX:

To preview LaTeX documents install `dvipng`, `dvisvgm` or `conver`.

In order to customise the preview customise the variables `org-format-latex-options` and `org-format-latex-header`.

(in order to enable the inline preview use the following press `<s TAB>` to insert a code block.)
As hown in \eqref{Quad}

    C-c C-x C-l (org-toggle-latex-fragment)

1.  Preview is Slow

    When using `C-c C-x C-l` to preview LaTeX fragments remember that it will
    generate the fragments using the latex settings corresponding to that buffer,
    including any additional header arguments you provide.
    
    Comment out the latex header you are using to give a style
    sheet, it&rsquo;s going to have lots of crap like TikZ which will slow things right
    the way down, It will even cripple latex exports, it&rsquo;s better to use that at the
    very end when you want a nicer product (timing it&rsquo;s about 4.5 X faster)
    
    Generate latex previews in temporary buffers, that will speed things up a lot
    
    Try to use `dvi2png` because it is alittle faster, avoid using `imagemagick` because it is
    slower.<sup><a id="fnr.17" class="footref" href="#fn.17">17</a></sup> 
    Review the variable org-latex-create-formula-image-program in order to verify
    which is being used.
    
    Anoter thing that can help is to make sure that you are using `pdflatex` NOT
    `xelatex`, I timed it on an arbitrary buffer and it went down from 45 to 35
    seconds.


<a id="org4316587"></a>

### Example LaTeX

\begin{align}
  \sum^{n- 1}_{n= 0} \left[ ar^n \right] &= a \cdot \frac{1-r^n}{1-r} \\
  \implies \sum^{\infty}_{n=0}\left[ ar^n \right]    &= a\cdot  \frac{1- \lim_{n \rightarrow \infty}\left[
  r^n\right]}{1-r}\notag \\
  \left| r \right| < 1 \iff \sum^{\infty}_{n = 0}  \left[ ar^n \right] &=
  \frac{1}{1- r}
\end{align}


<a id="orgad22f9e"></a>

## Tables

1.  Write a table draft by seperating with `|` characters
2.  Use `Tab` to fill it in
3.  move the point inside the table and press `C-c ~` to convert the table to
    `table.el`
    1.  This is only necessary if you desire text wrapping
4.  Now use `C-c '` to take the table into an special buffer
5.  Disable evil mode with `C-z` (IMPORTANT)
6.  Press Tab and edit the table in the buffer, you&rsquo;ll notice the text wraps in a
    well behaved fashion
7.  Press `C-u 20 C-C C-c <` to resize the table width


<a id="orga2c85bd"></a>

### DONE OLD Tables:Tables:

Let&rsquo;s make a table of key bindings, first we need to insert a table, we&rsquo;ll do
this wit a tamplate by typing in `SPC-m-t-n` for \*M\*ajor mode command, \*T\*able,
\*N\*ew.

<!-- This HTML table template is generated by emacs 27.1 -->
<table border="1">
  <tr>
    <td align="left" valign="top">
      &nbsp;Description&nbsp;for&nbsp;Tables&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br />
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    </td>
    <td align="left" valign="top">
      &nbsp;Key&nbsp;Binding&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br />
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    </td>
    <td align="left" valign="top">
      &nbsp;Notes&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br />
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    </td>
  </tr>
  <tr>
    <td align="left" valign="top">
      &nbsp;Move&nbsp;to&nbsp;next&nbsp;field&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    </td>
    <td align="left" valign="top">
      &nbsp;=SPC&nbsp;m&nbsp;t&nbsp;l=&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    </td>
    <td align="left" valign="top">
      &nbsp;.&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    </td>
  </tr>
  <tr>
    <td align="left" valign="top">
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Move&nbsp;along&nbsp;Table&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br />
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Cells&nbsp;(only&nbsp;for&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br />
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;=table.el)&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    </td>
    <td align="left" valign="top">
      &nbsp;=TAB=&nbsp;and&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br />
      =s-TAB=&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br />
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    </td>
    <td align="left" valign="top">
      &nbsp;There&nbsp;are&nbsp;other&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br />
      bindings&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br />
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    </td>
  </tr>
  <tr>
    <td align="left" valign="top">
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Convert&nbsp;table&nbsp;between&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br />
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;=org-mode=/=table.el=&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br />
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br />
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br />
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    </td>
    <td align="left" valign="top">
      &nbsp;=SPC&nbsp;m&nbsp;t&nbsp;c=&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br />
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br />
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br />
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br />
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    </td>
    <td align="left" valign="top">
      This&nbsp;only&nbsp;works&nbsp;well&nbsp;if&nbsp;<br />
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;you&nbsp;tab&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br />
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;between&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br />
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;cells/fields&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br />
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    </td>
  </tr>
  <tr>
    <td align="left" valign="top">
      &nbsp;Export&nbsp;to&nbsp;a&nbsp;file&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    </td>
    <td align="left" valign="top">
      &nbsp;=SPC&nbsp;m&nbsp;t&nbsp;E=&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    </td>
    <td align="left" valign="top">
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    </td>
  </tr>
  <tr>
    <td align="left" valign="top">
      &nbsp;Plot&nbsp;using&nbsp;/GnuPlot/&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br />
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br />
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    </td>
    <td align="left" valign="top">
      &nbsp;=SPC&nbsp;m&nbsp;t&nbsp;p=&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br />
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br />
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    </td>
    <td align="left" valign="top">
      &nbsp;=sudo&nbsp;apt&nbsp;install&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br />
      gnuplot=&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br />
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    </td>
  </tr>
  <tr>
    <td align="left" valign="top">
      &nbsp;Toggle&nbsp;Numbers&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br />
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br />
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    </td>
    <td align="left" valign="top">
      &nbsp;=SPC&nbsp;m&nbsp;t&nbsp;t&nbsp;o=&nbsp;&nbsp;&nbsp;<br />
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br />
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    </td>
    <td align="left" valign="top">
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;think&nbsp;*T*oggle&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br />
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*O*rg&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br />
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Coordinates&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    </td>
  </tr>
  <tr>
    <td align="left" valign="top">
      &nbsp;Move&nbsp;Table&nbsp;Rows&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br />
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br />
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    </td>
    <td align="left" valign="top">
      &nbsp;=SPC&nbsp;m&nbsp;t&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br />
      H/J/K/L=&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br />
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    </td>
    <td align="left" valign="top">
      &nbsp;Just&nbsp;use&nbsp;capital&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br />
      directions&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br />
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    </td>
  </tr>
  <tr>
    <td align="left" valign="top">
      &nbsp;Including&nbsp;LaTeX&nbsp;should&nbsp;work&nbsp;&nbsp;&nbsp;<br />
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br />
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br />
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br />
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br />
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br />
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    </td>
    <td align="left" valign="top">
      &nbsp;&nbsp;&nbsp;&nbsp;\(\oint&nbsp;z&nbsp;&nbsp;&nbsp;&nbsp;<br />
      \operatorname{d}x<br />
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;=&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br />
      &nbsp;{\scriptsize&nbsp;1}&nbsp;<br />
      &nbsp;&nbsp;{\big&nbsp;/}_{2}&nbsp;&nbsp;&nbsp;<br />
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\cdot&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br />
      &nbsp;&nbsp;&nbsp;&nbsp;z^2&nbsp;+&nbsp;C\)&nbsp;&nbsp;&nbsp;&nbsp;
    </td>
    <td align="left" valign="top">
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br />
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br />
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br />
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br />
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br />
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br />
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    </td>
  </tr>
</table>

-   Why can&rsquo;t I export this as a table?
    -   You have to be super careful with the formatting, the table MUST have bar
        lines on the sides, it doesn&rsquo;t need top and bottom `\hrule` indicators
        though.
    -   The conversion sometimes fucks up and this is where the problem comes in,
        make sure to use `TABS` to fill in data and when things go wrong just use
        Block mode to put `|` on the sides of the converted `org-mode` table, for
        some reason the conversion puts `+` there.
-   Can my tables include \(LaTeX\)
    -   yeah if it stops working just delete the LaTeX and start again, it&rsquo;s reall
        finnicky
-   Why does the `org-mode` table not include the mark up upon export?
-   Why does the `org-mode` table not respect the HTML CSS upon export when the
    `table.el` clearly does?
-   


<a id="orgafb2a4e"></a>

### Multi-Column Cells

If you want to merge cells etc. that&rsquo;s also doable, but it&rsquo;s real
finnicky <sup><a id="fnr.18" class="footref" href="#fn.18">18</a></sup> and it doesn&rsquo;t work in *BeOrg*.

<!-- This HTML table template is generated by emacs 27.1 -->
<table border="1">
  <tr>
    <td rowspan="3" align="left" valign="top">
      &nbsp;Region&nbsp;<br />
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br />
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br />
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br />
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    </td>
    <td colspan="8" align="left" valign="top">
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Sales&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    </td>
  </tr>
  <tr>
    <td colspan="2" align="left" valign="top">
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Q1&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    </td>
    <td colspan="2" align="left" valign="top">
      &nbsp;&nbsp;&nbsp;&nbsp;Q2&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    </td>
    <td colspan="2" align="left" valign="top">
      &nbsp;&nbsp;&nbsp;&nbsp;Q3&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    </td>
    <td colspan="2" align="left" valign="top">
      &nbsp;&nbsp;&nbsp;&nbsp;Q4&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    </td>
  </tr>
  <tr>
    <td align="left" valign="top">
      &nbsp;foo&nbsp;&nbsp;&nbsp;
    </td>
    <td align="left" valign="top">
      &nbsp;bar&nbsp;
    </td>
    <td align="left" valign="top">
      &nbsp;foo&nbsp;
    </td>
    <td align="left" valign="top">
      &nbsp;bar&nbsp;
    </td>
    <td align="left" valign="top">
      &nbsp;foo&nbsp;
    </td>
    <td align="left" valign="top">
      &nbsp;bar&nbsp;
    </td>
    <td align="left" valign="top">
      &nbsp;foo&nbsp;
    </td>
    <td align="left" valign="top">
      &nbsp;bar&nbsp;
    </td>
  </tr>
  <tr>
    <td align="left" valign="top">
      &nbsp;North&nbsp;&nbsp;
    </td>
    <td align="left" valign="top">
      &nbsp;350&nbsp;&nbsp;&nbsp;
    </td>
    <td align="left" valign="top">
      &nbsp;&nbsp;46&nbsp;
    </td>
    <td align="left" valign="top">
      &nbsp;253&nbsp;
    </td>
    <td align="left" valign="top">
      &nbsp;&nbsp;34&nbsp;
    </td>
    <td align="left" valign="top">
      &nbsp;234&nbsp;
    </td>
    <td align="left" valign="top">
      &nbsp;&nbsp;42&nbsp;
    </td>
    <td align="left" valign="top">
      &nbsp;382&nbsp;
    </td>
    <td align="left" valign="top">
      &nbsp;&nbsp;68&nbsp;
    </td>
  </tr>
  <tr>
    <td align="left" valign="top">
      &nbsp;South&nbsp;&nbsp;
    </td>
    <td align="left" valign="top">
      &nbsp;462&nbsp;&nbsp;&nbsp;
    </td>
    <td align="left" valign="top">
      &nbsp;&nbsp;84&nbsp;
    </td>
    <td align="left" valign="top">
      &nbsp;511&nbsp;
    </td>
    <td align="left" valign="top">
      &nbsp;&nbsp;78&nbsp;
    </td>
    <td align="left" valign="top">
      &nbsp;435&nbsp;
    </td>
    <td align="left" valign="top">
      &nbsp;&nbsp;45&nbsp;
    </td>
    <td align="left" valign="top">
      &nbsp;534&nbsp;
    </td>
    <td align="left" valign="top">
      &nbsp;&nbsp;89&nbsp;
    </td>
  </tr>
</table>


<a id="org9d1da23"></a>

## Drawers     :Drawers:

Insert a drawer with `SPC m a` / `, D`.

-   Basically this will appear as ordinary text but with the capacity to fold away in emacs
    -   So when you perform [Visibility Cycling](https://orgmode.org/manual/Visibility-Cycling.html#Visibility-Cycling) The drawer will not unfold unless you *pull it out* with `TAB`

\(\int 4x^3 dx\)


<a id="orgf1ce6b7"></a>

## DONE How to include links to files


<a id="org1da9ae1"></a>

### DONE Internal links

1.  Anchors

    Anchors can be created by using `<<TargetLandingText>>` and then accessed by
    using `[[TargetLandingText][Display Text]]`.


<a id="orgc26e25f"></a>

### DONE External Files

External files can be linked to by using the syntax `[[./myfile.ext]]` and they
can be jumped to with `Enter`, which would be `gf` / `gx` in *Vim*.


<a id="orgc304e10"></a>

# DONE Can I tag a specific lines

OK so i have all these notes in here now, like for example multi-column tables,
can I tag the specific line or subtree so that I can just jump straight to it??

This would be good for things like analysis where I might need a tag that says,
say for example, analysis/real/sequence.

To toggle inline images use `C-c C-x C-v` and to insert them just insert them as
a link using `C-c C-l`.

Dragging and Dropping does not work.


<a id="org0ea5445"></a>

# Custom Keybindings

just use `M-x global-set-key <RET> key cmd <RET>` as described in the manual [here](https://www.gnu.org/software/emacs/manual/html_node/efaq/Binding-keys-to-commands.html)

keyboard shortcuts manual


<a id="org46ca360"></a>

## Remap Esc

(setq evil-escape-key-sequence &ldquo;jj&rdquo;)


<a id="org29a500a"></a>

# Exporting Org Files

There are some Nice Parsers if you want a live preview of org-mode (This is
easy with markdown using iamcco, typora, marktext, zettlr, VSCode and atom)

Here is a list of interesting tools:

-   [Org-JS](https://mooz.github.io/org-js/)
    +[GitHub](https://github.com/mooz/org-js/)

+[Big List](https://orgmode.org/worg/org-tools/index.html) 


<a id="org64ade76"></a>

# Email


<a id="org546e233"></a>

## Receiving email

The easiest method is to:

-   use the [mbsync](http://isync.sourceforge.net/mbsync.html#CONFIGURATION) package, use theres [info on the Arch-Wiki](https://wiki.archlinux.org/index.php/Isync)
    -   [The config is here](file:///home/ryan/.mbsyncrc) and
    -   It can be installed with `sudo apt install isync`
-   use `notmuch` to manage the database
    -   install this with:
        -   `sudo apt install notmuch`
-   `notmuch` and `helm-notmuch` are in MELPA and work really well for searching through the database


<a id="orgedcaeb5"></a>

## Syncing Email

Use `mbsync gmail` and the email will be downloaded


<a id="orgc04c7d8"></a>

### Outlook Settings

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<tbody>
<tr>
<td class="org-left">Variable</td>
<td class="org-left">Value</td>
</tr>


<tr>
<td class="org-left">Server Name</td>
<td class="org-left"><code>outlook.office365.com</code></td>
</tr>


<tr>
<td class="org-left">Port</td>
<td class="org-left"><code>993</code></td>
</tr>


<tr>
<td class="org-left">User Name</td>
<td class="org-left"><code>17805315@student.westernsydney.edu.au</code></td>
</tr>


<tr>
<td class="org-left">Connection Security</td>
<td class="org-left"><code>SSL/TLS</code></td>
</tr>


<tr>
<td class="org-left">Auth Method</td>
<td class="org-left"><code>Normal Password</code></td>
</tr>


<tr>
<td class="org-left">Outgoing Serer Name</td>
<td class="org-left"><code>smtp.office365.com</code></td>
</tr>


<tr>
<td class="org-left">Port</td>
<td class="org-left"><code>587</code></td>
</tr>


<tr>
<td class="org-left">Outgoing Connection Sec</td>
<td class="org-left"><code>STARTTLS</code></td>
</tr>
</tbody>
</table>


<a id="org65a66c7"></a>

### Automatic Synch

This can be done via systemD, see the [Arch-Wiki](https://wiki.archlinux.org/index.php/Isync#Automatic_synchronization), basically just create a two files:

-   `~/.config/systemd/user/mbsync.service`
-   `~/.config/systemd/user/mbsync.service`


<a id="org313e462"></a>

## Sending Email

-   You&rsquo;ll need `apt install sendmail`
-   To format with `org-mode` use `org-mu4e`


<a id="org42ec1ea"></a>

## Config File

This is the `~/.mbsyncrc` file, installed via the `isync` package, it will pull email if you specify the channel, e.g. `mbsync gmail`

    IMAPAccount gmail
    # Address to connect to
    Host imap.gmail.com
    User RadiantDeceipt@gmail.com
    Pass "********************"
    # To store the password in an encrypted file use PassCmd instead of Pass
    # PassCmd "gpg2 -q --for-your-eyes-only --no-tty -d ~/.mailpass.gpg"
    #
    # Use SSL
    SSLType IMAPS
    # The following line should work. If get certificate errors, uncomment the two following lines and read the "Troubleshooting" section.
    CertificateFile /etc/ssl/certs/ca-certificates.crt
    #CertificateFile ~/.cert/imap.gmail.com.pem
    #CertificateFile ~/.cert/Equifax_Secure_CA.pem
    
    IMAPStore gmail-remote
    Account gmail
    
    MaildirStore gmail-local
    Subfolders Verbatim
    # The trailing "/" is important
    Path ~/.mail/gmail/
    Inbox ~/.mail/gmail/Inbox
    
    Channel gmail
    Master :gmail-remote:
    Slave :gmail-local:
    # Exclude everything under the internal [Gmail] folder, except the interesting folders
    Patterns * ![Gmail]* "[Gmail]/Sent Mail" "[Gmail]/Starred" "[Gmail]/All Mail"
    # Or include everything
    #Patterns *
    # Automatically create missing mailboxes, both locally and on the server
    Create Both
    # Save the synchronization state files in the relevant directory
    SyncState *
    
    
    IMAPAccount outlook
    # Address to connect to
    Host outlook.office365.com
    User 17805315@student.westernsydney.edu.au
    Pass "*******"
    # To store the password in an encrypted file use PassCmd instead of Pass
    # PassCmd "gpg2 -q --for-your-eyes-only --no-tty -d ~/.mailpass.gpg"
    #
    # Use SSL
    SSLType IMAPS
    # The following line should work. If get certificate errors, uncomment the two following lines and read the "Troubleshooting" section.
    CertificateFile /etc/ssl/certs/ca-certificates.crt
    #CertificateFile ~/.cert/imap.outlook.com.pem
    #CertificateFile ~/.cert/Equifax_Secure_CA.pem
    
    IMAPStore outlook-remote
    Account outlook
    
    MaildirStore outlook-local
    Subfolders Verbatim
    # The trailing "/" is important
    Path ~/.mail/outlook/
    Inbox ~/.mail/outlook/Inbox
    
    Channel outlook
    Master :outlook-remote:
    Slave :outlook-local:
    # Exclude everything under the internal [Outlook] folder, except the interesting folders
    Patterns * ![Outlook]* "[Outlook]/Sent Mail" "[Outlook]/Starred" "[Outlook]/All Mail"
    # Or include everything
    #Patterns *
    # Automatically create missing mailboxes, both locally and on the server
    Create Both
    # Save the synchronization state files in the relevant directory
    SyncState *


<a id="org1e66301"></a>

# Learning Elisp     :elisp:

See [this tutorial](file:///home/ryan/Dropbox/Studies/LISP/learn-emacs-lisp.el)


<a id="org662baa6"></a>

## Preliminaries

Functions are like this:

    (defun myp (var)
        (insert "Hello" var)
        )
    
    (myp "This was the Var")

If you don&rsquo;t use functions, you&rsquo;ll have to use `progn`:

    (progn
      (insert "Line 1")
      (insert "Line 2"))

`let` will also work:

    (let ((local-name "you"))
      (switch-to-buffer-other-window "*test*")
      (erase-buffer)
      (myp local-name)
      (other-window 1))

Get text from the minibuffer:

    (read-from-minibuffer "Heading Name: ")

Get a local or global variable:

    (let ((local-name "you"))
      (message local-name)
      )

    (progn
      (setq var "test")
      (message var)
      )

put those together:

    (let ((varname (read-from-minibuffer "Heading Name: ")))
      (message (number-to-string (length varname)))
      )

Now count insert the correct number of characters (interactive means you can get to it with `M-x`)

So first wrap it into a function

    (defun my-hd ()
      (interactive)
      (let ((varname (read-from-minibuffer "Heading Name: ")))
        (message (number-to-string (length varname)))
        )
    )

Now save the number of symbols to insert as a local variable

    (defun R-Heading-1 ()
      (interactive)
      (let ((hname (read-from-minibuffer "Heading Name: ")))
        (message (number-to-string (length hname)))
        (let ((hlen (length hname)))
          (let ((num (- 80 hlen)))
            (message (number-to-string num))
              (insert "## * ")
              (insert hname)
              (insert
                (apply 'concat (make-list (- 75 hlen) "-"))
               )
           )
         )
        )
    )


<a id="org6f61d3c"></a>

## Repeating text

so in ***R***:

    strrep("ha", 5)

but in emacs lisp:

    (apply 'concat (make-list 5 "ha"))


<a id="org8953350"></a>

## Making a R Heading Function

    (defun R-Heading-1 ()
      (let ((hname (read-from-minibuffer "Heading Name: ")))
        (message (number-to-string (length hname)))
        (let ((hlen (length hname)))
          (let ((num (- 80 hlen)))
            (message (number-to-string num))
              (insert "## * ")
              (insert hname)
              (insert
                (apply 'concat (make-list (- 75 hlen) "-"))
               )
           )
         )
        )
    )
    
    (defun R-Heading-2 ()
      (let ((hname (read-from-minibuffer "Heading Name: ")))
        (message (number-to-string (length hname)))
        (let ((hlen (length hname)))
          (let ((num (- 80 hlen)))
            (message (number-to-string num))
              (insert "## *** ")
              (insert hname)
              (insert
                (apply 'concat (make-list (- 74 hlen) "="))
               )
           )
         )
        )
    )
    
    (defun R-Heading-3 ()
      (let ((hname (read-from-minibuffer "Heading Name: ")))
        (message (number-to-string (length hname)))
        (let ((hlen (length hname)))
          (let ((num (- 80 hlen)))
            (message (number-to-string num))
              (insert "## *** ")
              (insert hname)
              (insert
                (apply 'concat (make-list (- 73 hlen) "#"))
               )
           )
         )
        )
    )
    
    
    (defun insert-r-heading ()
    (interactive)
    
    
    )
    
    
    
    (defun insert-r-heading (level)
      (interactive
       (list (completing-read "Choose: "
                              '(("1" . "Cow") ("2" . "Rabbit") ("3" . "Dog")) nil t)))
      (message "sdalfkju chose `%s'" level)
    level)
    
    (defun ask-age (x)
      "Ask age."
      (interactive "nEnter your age: ")
      (message "Name: %d" x))


<a id="orgdfd32ca"></a>

## Making Selection Choices

    (defun foo (choice)
      "..."
      (interactive
       (list (completing-read "Choose: "
                              '(("1" . "Cow") ("2" . "Rabbit") ("3" . "Dog")) nil t)))
      (message "You chose `%s'" choice)
      choice)


<a id="orgf6a67f6"></a>

## Making a greeting

    (defun greeting (from-name)
      (let ((your-name "Ryan"))
        (message (format  "Hello!\n\nI am %s and you are %s."
                         from-name ; This is the argument of the function
                         your-name ; This is the let bound variable
                         ))
      )
    )
    
    (greeting "Vidar")

1.  Make a greeting with a propt

        (defun ask-name (var)
          (let ((user-name (read-from-minibuffer "Enter your Name: " "Ryan?")))
            (message (format "Hello %s! \n\n I am %s"
                             var ;; these belong to the format function
                             user-name))
          )
        )
        (ask-name "Variable")
    
    1.  Now display that in another Window
    
            (defun ask-name (var)
              (switch-to-buffer-other-window "Temp")
              (let ((user-name (read-from-minibuffer "Enter your Name: " "Ryan?")))
                (insert (format "Hello %s! \n\n I am %s"
                                 var ;; these belong to the format function
                                 user-name))
              )
            )
            
            (ask-name "Vidar")


<a id="org6faf186"></a>

## Lists


<a id="org5377100"></a>

### Basic

use `'` to stop a list being evaluated

    (setq my-list-of-values '("Apples" "Oranges" "Banana"))


<a id="org01106f3"></a>

### Get the First/Last elements

    (car my-list-of-values)
    (cdr my-list-of-values)


<a id="org184d258"></a>

### Map a function over the list items

    (defun ask-name (var)
    ;;  (switch-to-buffer-other-window "Temp")
      (let ((user-name (read-from-minibuffer "Enter your Name: " "Ryan?")))
        (message (format "Hello %s! \n\n I am %s"
                         var ;; these belong to the format function
                         user-name))
      )
    )
    
    (mapcar 'ask-name my-list-of-values)

(mapcar)
\#+end<sub>src</sub>


<a id="org5903bf8"></a>

# Searching

-   [Read these notes](https://beepb00p.xyz/pkm-search.html)
    -   Look at org-ql


<a id="orgd2d57e4"></a>

# Exporting HTML

HTML Files
When exporting HTML Files with `org` export the images won&rsquo;t be embedded,
you can either:

-   use `pandoc --self-contained` and figure out how to make the

mathjax or katex self-contained (or use `mathml`)

-   either use pandoc to convert the org file outright
-   use pandoc to redo the HTML file

-   embed the images as base64
-   Make the HTML Stand-alone using pandoc


<a id="org454eeea"></a>

## DONE Making the HTML Standalone

How do i make stand alone HTML&rsquo;s in org-mode or is there an easy way to publish
them to a blog with gitpages.

So the base64 Image method worked, definitely, but I need a more foolproof way,
either get org-publish working or get a seperate repo

One easy method to do this is to export the HTML, host a local python server with `python3 -m http.server 8923`, go to `http://0.0.0.0:8923` and then use the firefox [SingleFile](https://addons.mozilla.org/en-US/firefox/addon/single-file/) extension.


<a id="org990af81"></a>

### Read [this Reddit Post](https://www.reddit.com/r/orgmode/comments/flibav/blogging_with_org_mode/) on making Blog Posts

It refers to [This Blog Post](https://justinhj.github.io/2020/03/09/how-to-blog-with-org-mode.html)


<a id="org02de07f"></a>

### Pandoc Workaround

Code something like the following will make the HTML self-contained, but, it will
break the references to a degree, making the format less nice.

    pandoc scratch.html --self-contained -c ~/Dropbox/profiles/Templates/CSS/github-pandoc.css -o scratch2.html


<a id="org80208ea"></a>

### TODO Make Function; Embedding Images as Base 64     :Evening:

So this Reddit post provides this method to embed images as base64, the code
suggests that it should work for `jpg`, `png` and `svg`:

    (defun replace-in-string (what with in)
      (replace-regexp-in-string (regexp-quote what) with in nil 'literal))
    
    (defun org-html--format-image (source attributes info)
      (progn
        (setq source (replace-in-string "%20" " " source))
        (format "<img src=\"data:image/%s;base64,%s\"%s />"
                (or (file-name-extension source) "")
                (base64-encode-string
                 (with-temp-buffer
                   (insert-file-contents-literally source)
                  (buffer-string)))
                (file-name-nondirectory source))
        ))

It actually works quite well, but, it&rsquo;s really slow and resource intensive,
also this would require the inline CSS method that I&rsquo;m already using


<a id="org96048c2"></a>

### TODO Tools for self contained HTML

The following tools can be used for self-contained html (it may be necessary to create as server using python3 -m http.server 8332):

-   Remi&rsquo;s Inliner
    -   `JavaScript`
-   [Trix&rsquo;s webpage2HTML](https://github.com/zTrix/webpage2html)
    -   `Python`
-   [Y2Z&rsquo;s monolith](https://github.com/Y2Z/monolith)
    -   `Rust, on /SnapCraft/`


<a id="org101759f"></a>

### Using JavaScript Inliner Tool

This might try and embed all links though, which will not be fun, the advante to
the base 64 `elisp` solution being that it only touches images.

[This inliner tool](https://github.com/remy/inliner) is really effective, meaning I could create a standalone HTML,
copy it to the repo and then push the repo thusly:

    # https://github.com/remy/inliner
    # npm install -g inliner
    inliner ./VisualAnalytics.html > ~/Documents/ryangreenup.github.io/VisualAnalytics.html
    cd ~/Documents/ryangreenup.github.io
    git add -A; git commit -m "Pushed from emacs"; git push

Unfourtunately this breaks the org-mode java script.

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<tbody>
<tr>
<td class="org-left">Pros</td>
<td class="org-left">Cons</td>
</tr>


<tr>
<td class="org-left">Nice Standardised Solution</td>
<td class="org-left">Breaks Org-JS</td>
</tr>


<tr>
<td class="org-left">Fast</td>
<td class="org-left">Doesn&rsquo;t seem to work properly</td>
</tr>
</tbody>
</table>

1.  Python Loop to do everything

    This script from [this reddit post](https://www.reddit.com/r/orgmode/comments/c1lhb5/html_output_that_can_be_used_on_an_android_phone/erejpfz/) doesn&rsquo;t work, I could probably do it in bash,
    but for reference sake:
    
        # https://github.com/remy/inliner
        # npm install -g inliner # Not as sudo, use NVM
        import glob
        import os
        import subprocess
        # html_file_list = glob.glob("/home/user/Dropbox/org/*.html")
        html_file_list = glob.glob("~/Notes/Org/*.html")
        export_dir = "/tmp/public_html/"
        for one_file in html_file_list:
            print(one_file)
            command = 'inliner ' + one_file + ' > ' + export_dir + os.path.basename(one_file)
            subprocess.call(command, shell=True)


<a id="org786c4c4"></a>

## Embedding Images my own script

So for svg images I use the following with TeX, I can&rsquo;t quite remember why but I
think it was something like `pandoc` doesn&rsquo;t like *TikZ*.

in bash you can use this to get the BASE64 encoding of an image:

    base64 ~/Pictures/background.jpg

I think I would need to modify this very slightly to accomidate

    #!/bin/bash
    
    #svgfile=9d9af7b10ca33c3d1bf4e525a1e32af0a2dc5a9a.svg
    htmlfile=$1
    
    
    if [ "$1" == "-h" ]; then
      echo "`basename $0` <SVG> <HTML>"
      exit 0
    fi
    
    # for consistency recreate the html file
    t2h doseReport.tex github-pandoc.css > t2h.log 2> /dev/null
    rm -f t2h.log
    
    ls *svg >> pics.txt
    for value in $(cat pics.txt)
    do
      svgfile=$value
    
    #Specify the specific Regex to remove
    oldtext="<p><img src=\"$svgfile\" \/><\/p>" # This might have been causing issues
    #oldtext="$svgfile"
    
    #capture the text of the svg
    svtext="$(cat $svgfile)" # This won't work
    echo $(sed '' $svgfile) # this won't work either, we
                                #need to escape special characters
    newtext=$(sed 's@[/\&]@\\&@g;$!s/$/\\/' $svgfile)
    #newtext="=========="
    # https://unix.stackexchange.com/a/152192
        #basically the 's@[/\&]@\\&@g;$!s/$/\\/' is necessary to
          #escape all the misbehaved characters
    
    
    # Identify the line in the html
         # sed -i -e "s/$oldtext/====/g" doseReport.html
    
    # Replace the line
     sed -i -e "s/$oldtext/$newtext/g" $htmlfile
    
     # Remove the svg
     rm $svgfile
    done
    rm pics.txt


<a id="orgda9478b"></a>

## DONE Throwing on Github


<a id="orga65af58"></a>

### Publishing Pathway

1.  New Attempt     :ATTACH:

    The general layout for a publishing function can be found [In the Manual](https://orgmode.org/manual/Complex-example.html#Complex-example)<sup><a id="fnr.18.100" class="footref" href="#fn.18">18</a></sup>
    but basically the idea is that regex is used to specify include and exclude, you
    can make multiple functions and you can have one function that calls multiple
    others, or, if you&rsquo;re organised, you can have one that uses regex as necessary.
    
    -   So Now I&rsquo;ve realise, it is necessary to export the entire project for it to
        work properly and copy over images.
    -   Also it seems that the CSS must have a relative path and/or be copied into the
    
    target directory beforehand
    
    -   It&rsquo;s actually Necessary to have Multiple functions, because you will need to
    
    have a different `:publishing-function` for different file types.
    
        ;; (remove-hook 'org-mode-hook 'toggle-org-custom-inline-style)
        ;; (toggle-org-custom-inline-style)
          (setq org-publish-project-alist
                '(
                  ("orgfiles"
                   :base-directory "~/Notes/Org/"
                   :base-extension "org"
                   :publishing-directory "/tmp/public_html/"
                   :publishing-function org-html-publish-to-html
                   :exclude "./journal.org" ;; regexp
        ;;           :include ["VisualAnalytics.org"] ;; regexp ;; everything included otherwise
                   :headline-levels 3
                   :recursive t
                   :section-numbers nil
                   :with-toc t
                   :html-head "<link rel=\"stylesheet\"
                   href=\"./style.css\" type=\"text/css\"/>"
                   :html-preamble t)
        
        
                  ("images"
                   :base-directory "~/Notes/Org/"
                   :base-extension "jpg\\|gif\\|png"
                   :exclude ".*ltximg.*" ;; regexp
                   :recursive t
                   :publishing-directory "/tmp/public_html/"
                   :publishing-function org-publish-attachment)
        
                  ("other"
                   :base-directory "~/Notes/Org/"
                   :base-extension "css\\|el\\|pdf\\|rmd\\|r\\|R\\|sh"
                   :recursive t
                   :publishing-directory "/tmp/public_html/"
                   :publishing-function org-publish-attachment)
        
                  ("website" :components ("orgfiles" "images" "other"))
                  ("ClassWork" :components ("Autumn2020" "images" "other"))))
    
    1.  Just Including Certain Notes
    
        Remember to push the github and you can test with python3 -m http.server 8003
        -bind 192.1680.0.1
        
            ;; (remove-hook 'org-mode-hook 'toggle-org-custom-inline-style)
            ;; (toggle-org-custom-inline-style)
              (setq org-publish-project-alist
                    '(
            
                      ("Aut_orgfiles"
                       :base-directory "~/Notes/Org/"
                       :base-extension "org"
                       :publishing-directory "~/Documents/ryangreenup.github.io/Org-Publish/"
                       :publishing-function org-html-publish-to-html
                       :exclude ".*" ;; Regexp
                       :include ("./VisualAnalytics.org" "ThinkingAboutData.org"
                                 "analytic_programming.org" "Social_Web_Analytics.org") ;; regexp ;; everything included otherwise
                       :headline-levels 3
                       :recursive t
                       :section-numbers nil
                       :with-toc t
                       :html-head "<link rel=\"stylesheet\"
                       href=\"./style.css\" type=\"text/css\"/>"
                       :html-preamble t)
            
            
                      ("Aut_images"
                       :base-directory "~/Notes/Org/"
                       :base-extension "jpg\\|gif\\|png"
                       :exclude ".*ltximg.*" ;; regexp
                       :recursive t
                       :publishing-directory "~/Documents/ryangreenup.github.io/Org-Publish/"
                       :publishing-function org-publish-attachment)
            
                      ("Aut_other"
                       :base-directory "~/Notes/Org/"
                       :base-extension "css\\|el\\|pdf\\|rmd\\|r\\|R\\|sh"
                       :exclude "journal.*" ;; Regexp
                       :recursive t
                       :publishing-directory "~/Documents/ryangreenup.github.io/Org-Publish/"
                       :publishing-function org-publish-attachment)
            
                      ("Autumn" :components ("Aut_orgfiles" "Aut_images" "Aut_other"))))
    
    2.  Using include and exclude
    
        In order `:base-extension` and `:exclude` should first be specified as regex and
        then `:include` should be used as a list of the form `("item1" "item2")`
        
        You definitely want to [read the manual](https://orgmode.org/manual/Selecting-files.html#Selecting-files)<sup><a id="fnr.19" class="footref" href="#fn.19">19</a></sup> .
    
    3.  Links and attachments
    
        The benefit of attaching files is that the directory of attachments can be
        browsed, manipulated and moved from within emacs which is really nice.
        
        Linking to attachments has some quirks though.
        
        -   **`attachment: file.pdf`**;
            -   If you make a link to a file with this link abbreviation it will not work
                upon HTML publish, which is really annoying.
        
        -   **`att: file.pdf`** ;
            -   if you define as shown at code listing 1 [91](#org5c1a350) as described on the [Mailing
                List](https://lists.gnu.org/archive/html/emacs-orgmode/2008-11/msg00108.html)<sup><a id="fnr.4.100" class="footref" href="#fn.4">4</a></sup> then the link will work upon HTML publish and it will move when
                the attachment directory is moved, but to enter it you won&rsquo;t have
                autocomplete.
        
        -   **`[[./Attachments/my.pdf]]`**;
            -   will work on HTML publish but will obviously break when/if the attachment
                directory is moved.
        
            (setq org-link-abbrev-alist '(("att" . org-attach-expand-link)))
    
    4.  Including Relative CSS
    
        For all use cases the css more or less must be in the same directory as the org file. when you get sick of that just use org-toggle-custom-inline-style.
        
        I&rsquo;m also going to make one to embed [as Base 64](#org80208ea)
    
    5.  Unchanged Files
    
        If a file has been removed from the publishing directory but the file has not
        changed, org-mode may not regenerate the file, in order to force the issue
        instead use a prefix command `C-u M-x org-publish`, it would also be possible to
        use the command shown in listing [92](#org82325b0)
        
            (org-publish "project name" t)


<a id="org66ed26d"></a>

## Previewing HTML

This is fairly easy, start a python server and then the index will automatically
display:

    python3 -m http.server -8367 #-bind 192.168.0.132

then open in in firefox:

    firefox 0.0.0.0:8351


<a id="org45ee922"></a>

# Org Agenda


<a id="org0afc1c4"></a>

## TimeStamps, Schedules and Deadlines

-   Relevant Links
    -   [Deadlines and Scheduling (The Org Manual)](https://orgmode.org/manual/Deadlines-and-Scheduling.html#:~:text=In%20Org%20mode%2C%20scheduling%20means,working%20on%20an%20action%20item.&text=in%20scheduling%20and%20deadline%20timestamps,issue%20early%20and%20late%20warnings.)
    -   [Timestamps (The Org Manual)](https://orgmode.org/manual/Timestamps.html#Timestamps)
-   TimeStamps
    -   Show an item on this date
-   Schedule
    -   Start working on an item on this date
-   Deadline
    -   The item should be finished by this time


<a id="org73e49ba"></a>

## Org Agenda Bindings

-   **`C-k`                        :** org-agenda-kill
-   **`C-n`                        :** org-agenda-next-line
-   **`C-p`                        :** org-agenda-previous-line
-   **`C-x`                        :** Prefix Command
-   **`ESC`                        :** Prefix Command
-   **`C-_`                        :** org-agenda-undo
-   **`SPC`                        :** org-agenda-show-and-scroll-up
-   **`!`                          :** org-agenda-toggle-deadlines
-   **`#`                          :** org-agenda-dim-blocked-tasks
-   **`$`                          :** org-agenda-archive
-   **`+`                          :** org-agenda-priority-up
-   **`,`                          :** org-agenda-priority
-   **`-`                          :** org-agenda-priority-down
-   **`/`                          :** org-agenda-filter
-   **`0`                          :** digit-argument
-   **`:`                          :** org-agenda-set-tags
-   **`;`                          :** org-timer-set-timer
-   **`<`                          :** org-agenda-filter-by-category
-   **`=`                          :** org-agenda-filter-by-regexp
-   **`>`                          :** org-agenda-date-prompt
-   **`?`                          :** org-agenda-show-the-flagging-note
-   **`B`                          :** org-agenda-bulk-action
-   **`C`                          :** org-agenda-convert-date
-   **`D`                          :** org-agenda-toggle-diary
-   **`E`                          :** org-agenda-entry-text-mode
-   **`F`                          :** org-agenda-follow-mode
-   **`G`                          :** org-agenda-toggle-time-grid
-   **`H`                          :** org-agenda-holidays
-   **`J`                          :** org-agenda-clock-goto
-   **`L`                          :** org-agenda-recenter
-   **`M`                          :** org-agenda-phases-of-moon
-   **`N`                          :** org-agenda-next-item
-   **`P`                          :** org-agenda-previous-item
-   **`Q`                          :** org-agenda-Quit
-   **`R`                          :** org-agenda-clockreport-mode
-   **`S`                          :** org-agenda-sunrise-sunset
-   **`T`                          :** org-agenda-show-tags
-   **`U`                          :** org-agenda-bulk-unmark-all
-   **`X`                          :** org-agenda-clock-cancel
-   **`[`                          :** org-agenda-manipulate-query-add
-   **`\`                          :** org-agenda-filter-by-tag
-   **`]`                          :** org-agenda-manipulate-query-subtract
-   **`^`                          :** org-agenda-filter-by-top-headline
-   **`_`                          :** org-agenda-filter-by-effort
-   **`a`                          :** org-agenda-archive-default-with-confirmation
-   **`b`                          :** org-agenda-earlier
-   **`c`                          :** org-agenda-goto-calendar
-   **`d`                          :** org-agenda-day-view
-   **`e`                          :** org-agenda-set-effort
-   **`f`                          :** org-agenda-later
-   **`g`                          :** org-agenda-redo-all
-   **`h`                          :** org-agenda-holidays
-   **`j`                          :** org-agenda-goto-date
-   **`k`                          :** org-agenda-capture
-   **`l`                          :** org-agenda-log-mode
-   **`m`                          :** org-agenda-bulk-mark
-   **`n`                          :** org-agenda-next-line
-   **`o`                          :** delete-other-windows
-   **`p`                          :** org-agenda-previous-line
-   **`q`                          :** org-agenda-quit
-   **`r`                          :** org-agenda-redo
-   **`s`                          :** org-save-all-org-buffers
-   **`u`                          :** org-agenda-bulk-unmark
-   **`v`                          :** org-agenda-view-mode-dispatch
-   **`w`                          :** org-agenda-week-view
-   **`x`                          :** org-agenda-exit
-   **`y`                          :** org-agenda-year-view
-   **`z`                          :** org-agenda-add-note
-   **`{`                          :** org-agenda-manipulate-query-add-re
-   **`|`                          :** org-agenda-filter-remove-all
-   **`}`                          :** org-agenda-manipulate-query-subtract-re
-   **`~`                          :** org-agenda-limit-interactively
-   **`DEL`                        :** org-agenda-show-scroll-down
-   **`C-/`                        :** org-agenda-undo
-   **`<C-S-left>`                 :** org-agenda-todo-previousset
-   **`<C-S-right>`                :** org-agenda-todo-nextset
-   **`<M-down>`                   :** org-agenda-drag-line-forward
-   **`<M-up>`                     :** org-agenda-drag-line-backward
-   **`<S-down>`                   :** org-agenda-priority-down
-   **`<S-left>`                   :** org-agenda-do-date-earlier
-   **`<S-right>`                  :** org-agenda-do-date-later
-   **`<S-up>`                     :** org-agenda-priority-up
-   **`<down>`                     :** org-agenda-next-line
-   **`<emacs-state>`              :** Prefix Command
-   **`<insert-state>`             :** Prefix Command
-   **`<motion-state>`             :** Prefix Command
-   **`<mouse-2>`                  :** org-agenda-goto-mouse
-   **`<mouse-3>`                  :** org-agenda-show-mouse
-   **`<normal-state>`             :** Prefix Command
-   **`<remap>`                    :** Prefix Command
-   **`<undo>`                     :** org-agenda-undo
-   **`<up>`                       :** org-agenda-previous-line
-   **~M-~\*                        :** org-agenda-bulk-toggle-all
-   **`M-m`                        :** org-agenda-bulk-toggle
-   **`C-c C-a`                    :** org-attach
-   **`C-c C-c`                    :** org-agenda-ctrl-c-ctrl-c
-   **`C-c C-d`                    :** org-agenda-deadline
-   **`C-c C-n`                    :** org-agenda-next-date-line
-   **`C-c C-o`                    :** org-agenda-open-link
-   **`C-c C-p`                    :** org-agenda-previous-date-line
-   **`C-c C-q`                    :** org-agenda-set-tags
-   **`C-c C-s`                    :** org-agenda-schedule
-   **`C-c C-t`                    :** org-agenda-todo
-   **`C-c C-w`                    :** org-agenda-refile
-   **`C-c C-x`                    :** Prefix Command
-   **`C-c C-z`                    :** org-agenda-add-note
-   **`C-c $`                      :** org-agenda-archive
-   **`C-c ,`                      :** org-agenda-priority
-   **`C-x C-s`                    :** org-save-all-org-buffers
-   **`C-x C-w`                    :** org-agenda-write
-   **`C-x u`                      :** org-agenda-undo
-   **`C-c C-x C-a`                :** org-agenda-archive-default
-   **`C-c C-x C-c`                :** org-agenda-columns
-   **`C-c C-x C-e`                :** org-clock-modify-effort-estimate
-   **~C-c C-x T~AB                :** org-agenda-clock-in
-   **`C-c C-x C-j`                :** org-clock-goto
-   **~C-c C-x R~ET                :** Prefix Command
-   **`C-c C-x C-o`                :** org-agenda-clock-out
-   **`C-c C-x C-s`                :** org-agenda-archive
-   **`C-c C-x C-x`                :** org-agenda-clock-cancel
-   **`C-c C-x !`                  :** org-reload
-   **`C-c C-x <`                  :** org-agenda-set-restriction-lock-from-agenda
-   **`C-c C-x >`                  :** org-agenda-remove-restriction-lock
-   **`C-c C-x A`                  :** org-agenda-archive-to-archive-sibling
-   **`C-c C-x I`                  :** org-info-find-node
-   **`C-c C-x _`                  :** org-timer-stop
-   **`C-c C-x a`                  :** org-agenda-toggle-archive-tag
-   **`C-c C-x b`                  :** org-agenda-tree-to-indirect-buffer
-   **`C-c C-x e`                  :** org-agenda-set-effort
-   **`C-c C-x p`                  :** org-agenda-set-property
-   **`C-c C-x <down>`             :** org-agenda-priority-down
-   **`C-c C-x <left>`             :** org-agenda-do-date-earlier
-   **`C-c C-x <right>`            :** org-agenda-do-date-later
-   **`C-c C-x <up>`               :** org-agenda-priority-up
-   **`<insert-state> M-SPC m c`   :** Prefix Command
-   **`<insert-state> M-SPC m d`   :** Prefix Command
-   **`<insert-state> M-SPC m q`   :** org-agenda-set-tags
-   **`<insert-state> M-SPC m r`   :** org-agenda-refile
-   **`<insert-state> M-SPC m t`   :** org-agenda-todo
-   **`<emacs-state> M-SPC m c`    :** Prefix Command
-   **`<emacs-state> M-SPC m d`    :** Prefix Command
-   **`<emacs-state> M-SPC m q`    :** org-agenda-set-tags
-   **`<emacs-state> M-SPC m r`    :** org-agenda-refile
-   **`<emacs-state> M-SPC m t`    :** org-agenda-todo
-   **`<visual-state> SPC m c`     :** Prefix Command
-   **`<visual-state> SPC m d`     :** Prefix Command
-   **`<visual-state> SPC m q`     :** org-agenda-set-tags
-   **`<visual-state> SPC m r`     :** org-agenda-refile
-   **`<visual-state> SPC m t`     :** org-agenda-todo
-   **`<normal-state> SPC m c`     :** Prefix Command
-   **`<normal-state> SPC m d`     :** Prefix Command
-   **`<normal-state> SPC m q`     :** org-agenda-set-tags
-   **`<normal-state> SPC m r`     :** org-agenda-refile
-   **`<normal-state> SPC m t`     :** org-agenda-todo
-   **`<motion-state> SPC m c`     :** Prefix Command
-   **`<motion-state> SPC m d`     :** Prefix Command
-   **`<motion-state> SPC m q`     :** org-agenda-set-tags
-   **`<motion-state> SPC m r`     :** org-agenda-refile
-   **`<motion-state> SPC m t`     :** org-agenda-todo
-   **`C-c C-x RET g`              :** org-mobile-pull
-   **`C-c C-x RET p`              :** org-mobile-push
-   **`<insert-state> M-SPC m c c` :** org-agenda-clock-cancel
-   **`<insert-state> M-SPC m c g` :** org-agenda-clock-goto
-   **`<insert-state> M-SPC m c i` :** org-agenda-clock-in
-   **`<insert-state> M-SPC m c o` :** org-agenda-clock-out
-   **`<insert-state> M-SPC m c r` :** org-agenda-clockreport-mode
-   **`<insert-state> M-SPC m c s` :** org-agenda-show-clocking-issues
-   **`<insert-state> M-SPC m d d` :** org-agenda-deadline
-   **`<insert-state> M-SPC m d s` :** org-agenda-schedule
-   **`<emacs-state> M-SPC m c c`  :** org-agenda-clock-cancel
-   **`<emacs-state> M-SPC m c g`  :** org-agenda-clock-goto
-   **`<emacs-state> M-SPC m c i`  :** org-agenda-clock-in
-   **`<emacs-state> M-SPC m c o`  :** org-agenda-clock-out
-   **`<emacs-state> M-SPC m c r`  :** org-agenda-clockreport-mode
-   **`<emacs-state> M-SPC m c s`  :** org-agenda-show-clocking-issues
-   **`<emacs-state> M-SPC m d d`  :** org-agenda-deadline
-   **`<emacs-state> M-SPC m d s`  :** org-agenda-schedule
-   **`<visual-state> SPC m c c`   :** org-agenda-clock-cancel
-   **`<visual-state> SPC m c g`   :** org-agenda-clock-goto
-   **`<visual-state> SPC m c i`   :** org-agenda-clock-in
-   **`<visual-state> SPC m c o`   :** org-agenda-clock-out
-   **`<visual-state> SPC m c r`   :** org-agenda-clockreport-mode
-   **`<visual-state> SPC m c s`   :** org-agenda-show-clocking-issues
-   **`<visual-state> SPC m d d`   :** org-agenda-deadline
-   **`<visual-state> SPC m d s`   :** org-agenda-schedule
-   **`<normal-state> SPC m c c`   :** org-agenda-clock-cancel
-   **`<normal-state> SPC m c g`   :** org-agenda-clock-goto
-   **`<normal-state> SPC m c i`   :** org-agenda-clock-in
-   **`<normal-state> SPC m c o`   :** org-agenda-clock-out
-   **`<normal-state> SPC m c r`   :** org-agenda-clockreport-mode
-   **`<normal-state> SPC m c s`   :** org-agenda-show-clocking-issues
-   **`<normal-state> SPC m d d`   :** org-agenda-deadline
-   **`<normal-state> SPC m d s`   :** org-agenda-schedule
-   **`<motion-state> SPC m c c`   :** org-agenda-clock-cancel
-   **`<motion-state> SPC m c g`   :** org-agenda-clock-goto
-   **`<motion-state> SPC m c i`   :** org-agenda-clock-in
-   **`<motion-state> SPC m c o`   :** org-agenda-clock-out
-   **`<motion-state> SPC m c r`   :** org-agenda-clockreport-mode
-   **`<motion-state> SPC m c s`   :** org-agenda-show-clocking-issues
-   **`<motion-state> SPC m d d`   :** org-agenda-deadline
-   **`<motion-state> SPC m d s`   :** org-agenda-schedule


<a id="orgf640efc"></a>

# References

<a id="orgc700c4f"></a>


<a id="orge56d60c"></a>

# Bibliography

<a id="orga71e7b0"></a>Ali, Ahmad Zamzuri Mohamad, Rahani Wahid, Khairulanuar Samsudin, and Muhammad Zaffwan Idris. 2013. “Reading on the Computer Screen: Does Font Type Have Effects on Web Text Readability?” 6 (3):26–35. <https://eric.ed.gov/?id=EJ1067757>.

<a id="org3431d91"></a>Benner, Sylvain. n.d. *BibTeX Layer*. <https://www.spacemacs.org/layers/+lang/bibtex/README.html>.

<a id="org078c3a7"></a>“Bibtex - Biblatex: Submitting to a Journal.” n.d. <https://tex.stackexchange.com/questions/12175/biblatex-submitting-to-a-journal>.

<a id="org5df0712"></a>Bloom, Stanley. n.d. “Effects of Radiation Damping on Spin Dynamics” 28 (7):800–805. <https://doi.org/10.1063/1.1722859>.

<a id="orgcfe9aa9"></a>Chaparro, Barbara S., and A. Dawn Shaikh. n.d. *The Effects of Line Length on Reading Online News*.

<a id="orgfb56fd3"></a>Chen, Ming-Pu, Others, and  . 1996. *The Effects of Font Size in a Hypertext Computer Based Instruction Environment*. <https://eric.ed.gov/?id=ED397784>.

<a id="org464d161"></a>“Choose a Comfortable Measure | the Elements of Typographic Style Applied to the Web.” n.d. <http://webtypography.net/2.1.2>.

<a id="org56ff4a5"></a>Credé, Marcus, and Nathan R. Kuncel. n.d. “Study Habits, Skills, and Attitudes: The Third Pillar Supporting Collegiate Academic Performance” 3 (6):425–53. <https://doi.org/10.1111/j.1745-6924.2008.00089.x>.

<a id="orgd2694ae"></a>Gist, Marilyn E., Anna G. Bavetta, and Cynthia Kay Stevens. n.d. “Transfer Training Method: Its Influence on Skill Generalization, Skill Repetition, and Performance Level” 43 (3):501–23. <http://ezproxy.uws.edu.au/login?url=http://search.ebscohost.com/login.aspx?direct=true&db=bth&AN=9609035670&site=ehost-live&scope=site>.

<a id="org59efe2b"></a>Hojjati, Nafiseh, and Balakrishnan Muniandy. n.d. “The Effects of Font Type and Spacing of Text for Online Readability and Performance” 5 (2):161–74. <https://dergipark.org.tr/en/pub/cet/271507>.

<a id="org336f229"></a>Munro’s, H H. n.d. “<//Psychology.Wichita.Edu/Newsurl/Usabilitynews/72/Columns>.,” 8.

<a id="org5520ca3"></a>Tinker, M. A., and D. G. Paterson. n.d. “Studies of Typographical Factors Influencing Speed of Reading. III. Length of Line” 13 (3):205–19.

NO<sub>ITEM</sub><sub>DATA</sub>:Wic2019

NO<sub>ITEM</sub><sub>DATA</sub>:Wor1939b

<a id="org88d6b26"></a>


# Footnotes

<sup><a id="fn.1" href="#fnr.1">1</a></sup> I got this from the[ O&rsquo;Toole Tutorial](https://orgmode.org/worg/org-tutorials/org4beginners.html)

<sup><a id="fn.2" href="#fnr.2">2</a></sup> [A Package in a league of its own: <code>Helm</code>](https://tuhdo.github.io/helm-intro.html)

<sup><a id="fn.3" href="#fnr.3">3</a></sup> LaTeX `citeproc` Usage

<sup><a id="fn.4" href="#fnr.4">4</a></sup> [Org-Mode Reference Card](https://orgmode.org/orgcard.txt)

<sup><a id="fn.5" href="#fnr.5">5</a></sup> [Look at the *GitHub* for the ESS layer](https://github.com/syl20bnr/spacemacs/tree/master/layers/%252Blang/html)

<sup><a id="fn.6" href="#fnr.6">6</a></sup> <https://stackoverflow.com/a/60070347/12843551>

<sup><a id="fn.7" href="#fnr.7">7</a></sup> [[[emacs - Syntax highlighting in org-mode. List of languages? - Stack
Overflow](<https://stackoverflow.com/a/22484646>)][]]

<sup><a id="fn.8" href="#fnr.8">8</a></sup> [GitHub - mcandre/vimrc-mode:
Enables syntax highlighting for .vimrc/<sub>vimrc</sub> files](https://github.com/mcandre/vimrc-mode)

<sup><a id="fn.9" href="#fnr.9">9</a></sup> [emacs - Syntax highlighting in org-mode. List of languages? - Stack
Overflow](https://stackoverflow.com/a/27529496)

<sup><a id="fn.10" href="#fnr.10">10</a></sup> See  [Enabling tikz previews in org-mode](http://bnbeckwith.com/blog/org-mode-tikz-previews-on-windows.html)

<sup><a id="fn.11" href="#fnr.11">11</a></sup> [Helm-bookmark manual](https://github.com/emacs-helm/helm/blob/master/helm-bookmark.el)

<sup><a id="fn.12" href="#fnr.12">12</a></sup> [asynchronous - How to avoid pop-up of **Async Shell Command** buffer in
Emacs? - Stack Overflow](https://stackoverflow.com/questions/13901955/how-to-avoid-pop-up-of-async-shell-command-buffer-in-emacs)

<sup><a id="fn.13" href="#fnr.13">13</a></sup> Refer to the documentation [here](http://orgmode.org/manual/Handling-links.html#Handling-links).

<sup><a id="fn.14" href="#fnr.14">14</a></sup> The shortcut for footnotes is `C-c C-x f` as described in [the manual](https://orgmode.org/manual/Footnotes.html) and
the shortcut for links is `C-c C-l`

<sup><a id="fn.15" href="#fnr.15">15</a></sup> having `emacs-lisp` after means it will be (atleast-partially) evaluated
upon HTML export, you will need to install [`emacs-htmlize`](https://github.com/hniksic/emacs-htmlize/blob/master/htmlize.el) in order to export
it, this can be done by typing in the following `M-x package-install RET
htmlize`; confusing that it isn&rsquo;t `emacs-htmlize`, maybe that&rsquo;s a standard?

<sup><a id="fn.16" href="#fnr.16">16</a></sup> Most of this is taken from the [*ReadTheDocs*](https://www.spacemacs.org/layers/+emacs/org/README.html#tree) Spacemacs link

<sup><a id="fn.17" href="#fnr.17">17</a></sup> [macos - Why does org-preview-latex-fragment work about 10 times slower in OSX than on linux? - Stack Overflow](https://stackoverflow.com/questions/22700904/why-does-org-preview-latex-fragment-work-about-10-times-slower-in-osx-than-on-li)

<sup><a id="fn.18" href="#fnr.18">18</a></sup> Refer to the[ Mailing List](https://lists.gnu.org/archive/html/emacs-orgmode/2010-08/msg00882.html) for `org-mode`

<sup><a id="fn.19" href="#fnr.19">19</a></sup> [This *StackExchange*](https://stackoverflow.com/a/27264339) answer shows why the help only expects one function
to be mapped to one function
