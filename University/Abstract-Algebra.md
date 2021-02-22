---
title: Abstract Algebra
description: 
published: 1
date: 2021-02-22T14:15:03.810Z
tags: 
editor: markdown
dateCreated: 2021-02-22T12:16:49.272Z
---

---
title: Abstract Algebra Topic Summary
tags: [Notebooks/Mathematics/Abstract Algebra]
created: '2019-11-01T05:43:10.730Z'
modified: '2019-11-01T05:44:12.232Z'
---

# Abstract Algebra Topic Summary
> *Abstract Algebra*  <sub> TB: An Introduction to abstract algebra_ by Nicodemi, Sutherland and Towsley </sub>

**Author:** *Ryan G; 17805315*

<a name="antoc"></a>

Alternative/Accessible Textbooks:

* [*An Introduction to Abstract Algebra* by Derek Robinson](http://booksdescr.org/item/index.php?md5=8116F6EE260EE2681415ABFD600696AC)
* [*Abstract Algebra: An Introduction* by Thomas Hungerford](http://booksdescr.org/item/index.php?md5=7519238B77AC24ABEEB6B3F4A0A1392F)
* [*Introduction to Modern Abstract Algebra* by David Burton](http://booksdescr.org/item/index.php?md5=D4CCAD47CC508CFE7C7DD857AB0AEF98)

[TOC]

---

# 1) Induction and Divisibility

<a name="aatop1"></a>

> ***Week 1 Material, Due Thur. 7 March<sub> TB: [1.1], [1.2], [2.1], [2.2] </sub>***
![](![]())
* [Numbers and Sets](#aa(1)sets)



<a name="aa(1)sets"></a>

## Numbers and Sets

This is mostly reproduced in the Topic 1 section on Sets in the [Analysis Notes](https://ryangreenup.github.io/AnalysisNotes/AnalysisNotes.html#an(1)sets)

### Set Orders

The Natural Numbers have an intuitive order:

$0<1<2<3<4 \dots$

As to the Real Numbers:

$-99<-1<0<e<\pi<e^{4\pi}<\frac{999}{2}​$

However, the [Field of Complex Numbers](#aa(5)rings2) has no intuitive order because the numbers do not exist on a line but on a plane.

On a line mathematical operations can be seen as a symmetrical transformation of that line, but on a plane order becomes somewhat arbitrary. [*3Blue1Brown](<https://www.youtube.com/watch?v=mvmuCPvRoWQ>) has a great video on this.

### Mathematical Induction

Refer to [these notes](https://ryangreenup.github.io/AnalysisNotes/AnalysisNotes.html#an(1)wop) in Analysis, they overlap entirely.

## Arithmetic and Divisibility

<a name="aa(1)divis"></a>

Whats important here, is the division Algorithm, which states:

> If an integer is divided by some $b \in \mathbb{N}$ , there will always be some remainder $r$ : $0<r<b$

This is a pretty straightforward proposition, but it underlies all later proofs of abstract algebra.

### Properties of the Integers

Investigating the properties of number sets will be important later for considering the algebraic structure of sets, but for now, consider the 6 properties of the integers:

1. **Associative** under addition and multiplication
   1. $\forall (a,b,c \in \mathbb{Z}), a + (b+c) = (a+b) + c$
   2. $\forall (a,b,c \in \mathbb{Z}), a \cdot (b\cdot c) = (a\cdot b) + c$
2. **Commutative** under multiplication and addition
   1. $\forall (a,b \in \mathbb{Z}),  a + b = b + a$
   2. $\forall (a,b \in \mathbb{Z}),  a \cdot b = b \cdot a$
3. There always exists a unique **additive Identity**, $0$
   1. $\forall x \in \mathbb{z}, !\exists 0 : 0+x=x​$
4. There always exists a unique **multiplicative identity**, $1$
   1. $\forall x \in \mathbb{z}, !\exists 1 : 1\cdot x=x$
5. Every integer has an **additive inverse**\
   1. $\forall x \in \mathbb{Z}, \exists (-x) : x + (-x) = 0$
6. Addition and multiplication satisfy the **distributive law**
   1. $\forall (x,y,z \in \mathbb{Z}), (x\cdot y) + (x\cdot z)$

### Divisibility Definition

Let $a$ and $b$ be integers with $b \neq 0$:
$$
(a,b) \in \mathbb{Z} : b \neq 0
$$
it is said that $b$ **divides** $a$ (written $b|a$), if there is some integer $q$ such that $\enspace a = b\cdot q$:
$$
b|a \iff \exists q \in \mathbb{Z} : a = b\cdot q
$$
This is the same as saying:

* $a$ is **divisible** by $b$
* $a$ is a **multiple** of $b$

### Divisibility Properties

1. $a|b \enspace  \wedge \enspace b|c \implies a|c$
2. $a|b \enspace \wedge \enspace a|c \implies a|(mb + nc)$

####
##### Proof
Observe that:
$a|b \implies b = k\cdot a, \enspace \exists t \in \mathbb{Z} \quad \text{and} \quad b|c \implies c = s \cdot b, \enspace \exists s \in \mathbb{z}$

### Division Algorithm

The definition of the algorithm:

Let $a$ and $b$ bey any integers with $b >0$.

There are unique integers $q$ and $r$ such that $a = qb +r$, where $0 \leq r <b$, i.e.:
$$
!\exists (q,r \in \mathbb{Z}, \enspace q \neq r)  : (a = qb +r) \wedge (0 \leq r < b)
$$

## Greatest Common Divisors and Euclids Algorithm

### Definition of the GCD

Suppose $a$ and $b$ are nonzero integers, the *greatest common divisor* of $a$ and $b$ is the largest integer that divides both of them and is denoted:

​                   $gcd(a,b)​$

Observe some properties of the gcd

1. $\gcd(0,0)$ is undefined because it would be

2. $\gcd(a,0) = a$ ; because any number divides     and the largest number that divides     is itself
   1. unless $a=0​$ in which case it would be like (1) above.

3. $\gcd(b, qb) = b​$ ; because the $b​$ divides both terms and is the largest possible divisor of$b​$

### Theorem 1

The $\gcd(a,b)$ is the smallest positive integer that can be expressed in the form:
$$
ma + nb : (m,n \in \mathbb{Z})
$$

#### Corollary

Observe further, that for $x \in \mathbb{Z}$ , thwse two statements are wholly equivalent:

1. $x = ma+nb$
2. $\gcd(a,b)|x

> i.e. $x = ma + nb \iff \gcd(a,b) | x$



### Relatively Prime

#### Definition

Suppose $a$ and $b$ are non-zero integers, they are *relatively prime* (i.e. *coprime*) if $\gcd(a,b)=1​$

#### Proposition; Relatively Prime by GCD

Suppose $a$ and $b$ are non-zero integers, and let $\gcd(a,b) =d$

Then $\frac{a}{d}$ and $\frac{b}{d}$ are relatively prime.

### Euclid's Lemma (P.18)

#### Definition

Suppose $a, b, c$ are integers such that $a$ and $b$ are coprime.

if $b\cdot c$ is a multiple of $a$,

Then $c$ must be a multiple of $a$

​	(because $p$ was prime)

### Theorem; GCD becomes Remainder and Factor

Suppose $(a,b,q,r)$ are all integers, such tat:
$$
a = qb +r
$$
Then,
$$
\gcd(a,b) =\gcd(b,r)
$$

### Euclid's Algorithm (i.e. Calculating GCD's)

*Euclid's Algorithm* allows for a method to find the *Greatest Common Denominator*:

For two positive natural numbers, $a,b$ such that $a>b$:

1. write in the form of $a=qb+r$,  where $(q,r\in \mathbb{Z})$ with $0<r<b$
2. If $r=0$, then $a=q\cdot b$ and hence $\gcd(a,b) = \gcd(b,r)$
3. if $r\neq​$ 0, then $\gcd(a,b) = \gcd(b,r)​$
   1. Now repeat from step 1

### Lowest Common Multiples

For two integers $(a,b) \in \mathbb{Z}$, the *Lowest Common Multiple*, is the smallest integer that is a multiple of both $a$ and $b$

The $LCM$ is a number that is the smallest possible multiple of other numbers

#### Finding the *LCM*

In order to find the *LCM* use the formula:
$$
\text{lcm} (a,b) = \frac{a\cdot b}{\gcd(a,b)}
$$

---

# (2) Prime Numbers
<a name="aatop3"></a>

[Back to Top](#antoc)

## Definitions

Prime and composite numbers are any numbers that satisfy the following conditions:

| **Prime Numbers** | Composite Numbers |
| ---| --- |
|  1. $p>1$ <br> 2. $p \in \mathbb{z}$ <br> 3. $x \mid p \iff (x =1 \enspace \wedge \enspace x=p)$<br> | 1. $c > 1$ <br> 2. $c \text{ is not prime}$               |







| Prime Numbers                                                | Composite Numbers                                           |
| ------------------------------------------------------------ | ----------------------------------------------------------- |
|  |  |

Observe that $1$ is neither a prime nor a composite number, this is important for later

## Infinite Primes

### Summary

There are infinite prime numbers

### Proof

Suppose;

$$
S = \{p_1, p_2, p_3, \dots p_n\}
$$

is the set of the first $n$ prime numbers,

let:
$$
q = (p_1 \cdot p_2 \cdot p_3 \cdot \dots p_n)
$$




Observe that $q$ would not be a multiple of any value $p \in S$

> <sub>Although this does not mean $q$ is necessarily prime (primes can be [much more difficult](https://www.youtube.com/watch?v=tlpYjrbujG0) to generate), $q$ is possible a composite of primes not in $S$, but regardless, $q$ is not divisible by any $p \in S$ </sub>

Thus $S$ cannot contain all prime values.

Observe likewise, no set $S​$ could be constructed such that it contained all the primes

> <sub> or atleast no finite set $S​$ </sub>

$\therefore​$ , the set of all Prime numbers must not be finite (i.e. there are infinite primes).

<div style="text-align: right">⬛ </div>

## Primes of Multiples

If a prime number divides a composite, it must divide one of
the factors of that composite number

### Summary

$p$ is a prime number *if and only if*:
$$
\forall (a,b \in \mathbb{z}), \enspace p|a\cdot b \implies p|a \enspace \vee \enspace p|b
$$

### Proof

Suppose $p​$ is a prime number:

$$
\enspace p | (a \cdot b)
$$

Either $p$ divides $a$ or it does not:

| $p\mid a$                                                    | $p\nmid a$                                                   |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| $p\mid a$ , thus<br />$$p\mid ab \implies p|a \vee p|b \quad \blacksquare$$ | $p \nmid a$, thus:<br /><br />$$gcd(a,p) = 1$$ <br /><br /> because $p|ab$ and $\gcd(a,p) = 1$<br /><br />Then by Euclid's Lemma:<br />$p|b$<br /><br />thus, <br />$p|ab \implies p|a \vee p|b \quad \blacksquare$ |

Thus:
$$
p|ab \implies p|a \vee p|b
$$

## Prime Factors

### Summary

Suppose $p$ is prime and $p$ divides some number $a_1 \cdot a_2 \cdot a_3 \dots a_n$

Then $p$ divides $a_k \enspace : \enspace 1 \leq k \leq n$

Moreover, if $a_k$ is prime, then $p=a_k$

## The Fundamental Theorem of Arithmetic

### Summary

```
```
For any integer $n$:

1. $\enspace n = p^{k_1}_1\cdot p^{k_2}_2 \cdot p^{k_3}_3 \dots p^{k_m}_m$
2. The above factorisation of $n$ is unique to the value of $n$

This proof is provided on p. 28 of the TB.

### Corollary, Rational Numbers

Every rational number can be expressed in a lowes form of relatively prime integers.

#### Summary

Every rational number can be expressed uniquely as some fraction of integers:
$$
\forall r \in \mathbb{Q}, \enspace !\exists m,n \in \mathbb{Z} : r = \frac{m}{n}
$$

##### $\sqrt{2}$ is not rational

A rational number can be expressed as a ratio, $\sqrt{2}$ cannot be, the proof is in the [Analysis Textbook](http://booksdl.org/get.php?md5=ef3626243a81006414e1f5a67ce694e0) at [2.1.4].

###### Proof

Just refer to the textbook

## Theorems of Euler and Fermat (ch. [1.7])

<a name="aa(2)euler"></a>

### Euler-Phi Function

The *Euler-Phi Function* counts the number of integers relatively prime to $n$ that are less than $n$,

#### Definition

for $n \geq 1$;

$\phi(n)$ is the number of positive integers less than or equal to $n$ that are relatively prime to $n$

> e.g. $2, 3, 7$ are relatively prime to $10$, thus $\phi(10) = 3$

### Powers of Euler-Phi Function

#### Summary

if $p$ is prime and $i \geq 1$,
$$
\begin{align}
\phi(p^i) &= p^i - p^{i-1} \\
&=p^i(1-frac{1}{p})
\end{align}
$$

#### Proof

All the numbers between $1$ and $p-1$ are relatively prime to p, thus $\phi(p)=p-1$.

All integers less than $p^i$ (for $i\geq 1$) are relatively prime to $p^i$ except for multiples of $p$.
	i.e. all values less than $p^i$ are relatively prime except for $1p,2p,3p \dots p^(i-1) p$.

So there are exactly $p^{i-1}$ multiples of $p$ that are multiples and hence not relatively prime.

Thus there is a total of $p^i-p^{i-1}$ numbers between $1$ and $p^i$ that are relatively prime to $p^i$.

### Euler-Phi Function is Multiplicative

#### Summary

For positive relatively prime integers $m$ and $n$:
$$
\gcd(m, n) = 1 \implies \phi(m \cdot n) = \phi(m) \cdot \phi(n)
$$

#### Proof

Refer to p. 44 of the TB.

#### Corollary

for primes $p, e \in \mathbb{N}$,

Given some $n$ value:
$$
n = p^{e_1}_1 \times p^{e_2}_2 \times p^{e_3}_3 \times p^{e_r}_r
$$

Then the Euler Phi function is:

$$
\phi(n) = p^{e_1-1}_1 \cdot (p_1-1) \times p^{e_2-1}_2 \cdot (p_2-1) \times p^{e_3-1}_3 \cdot (p_3-1) \dots p^{e_r-1}_r \cdot (p_r-1)
$$

Further it follows:

$$
\phi(n) = n \times \frac{p_1 -1}{p_1} \times \frac{p_2 -1}{p_2} \times \frac{p_3 -1}{p_3} \times \frac{p_r -1}{p_r}
$$



> <sub>I've merely interchanged $\cdot$ and $\times$ here
> for want of illustration, there is no significant
> meaning right here whatsoever (where as maybe
> later down $\cdot$ may refer to more abstract
> ideas of multiplication but it's pretty lose as it stands)</sub>

### Eulers Theorem

<a name="aa(2)eulphi"></a>

#### Summary

For relatively prime integers $a$ and $m \geq 1$:
$$
m | (a^{\phi(m)} - 1)
$$

#### Proof

The proof is on page 45 of the TB.

#### Fermats Little Theorem

The special case of *Euler's Theorem*, men $m$ is prime, in known as *Fermat's Little Theorem*.

##### Summary

For some prime $p$ and integer $a$:
$$
p \mid (a^p -a)
$$

##### Proof

It must be such that $p​$ divides $a​$ or $p​$ does not divide $a​$ , hence:

| $p \mid a$                                                   | $ p \nmid a$                                                 |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| if $p \mid a$ <br />$\implies p \mid a^n, \enspace \exists n \in \mathbb{N}$<br /> $\implies p \mid a^{p-1}$ <br /> $\implies p \mid (a^p -a)$ | if $p\nmid a$<br /><br />Then $p$ and $a$ are relatively prime, thus, *Eulers Theorem* applies;<br /><br />By *Euler's Theorem*:<br />$p|(a^{\phi(p)}-1)$<br />$\implies p \mid (a^{(p^1-p^0)}-1)$<br />$\implies p \mid (a^{(p-1)}-1)$<br />$\implies p \mid (a \cdot (a^{(p-1)}-1))$<br />$\implies p \mid (a^p-a)$ |

Thus for a prime $p$ and integer $a$:
$$
p \mid (a^p - a)
$$

---
# (3) Relations and Congruence
<a name="aatop3"></a>

[Back to Top](#antoc)

* [Relations](#aa(3)rel)
* [Congruence Modulo n](#aa(3)con)
* [The Ring](#aa(3)ringintro)

## Relations

<a name="aa(3)rel"></a>

A relation on a set $A$ is a subset $R$ of the cartesian product:
$$
A\times A = \{(a,b) : a,b \in A\}
$$
if $(a,b) \in R$ we write that $\enspace a \enspace R \enspace b$

### Example

If we had the relation $<$ on the set $A$ = \{1,2,3\}.

​	The Cartesian product would be:
$$
A \times A = \{(1,1), (1,2), (1,3), (2,1), (2,2), (2, 3), (3, 1), (3, 2), (3,3)\}
$$
The set corresponding to the relation $<$ would be:
$$
\{(1,2), (1, 3), (2, 3)\}
$$

### Relation Types

* **Reflexive** relations are relations where
  * $a \enspace R \enspace a$
    * $\forall a \enspace \in A$
* **Symmetric** relations are such that
  * $a \enspace R \enspace b \implies b \enspace R \enspace a$
    * $\forall a, b \in A$
* **Transitive** relations are such that
  * $a \enspace R \enspace b \quad \wedge \quad  b \enspace R \enspace c \implies  b \enspace R \enspace a$
    * $\forall a,b,c\in A$

An equivalence relation is a relation that is reflexive, symmetric and transitive.

#### Example 1

Let $S = \{\text{all people}\}$

We will define a relation $R$ as satisfied if thouse people share the same parents

##### Define a relation

$x \enspace R \enspace y$ if $x$ has the same parents as $y$

observe the following properties:

* **Reflexivity**; any person will be related to themselves because they share the same parents

* **symmetry**; If percy is related to Fred, then they share parents and hence then Fred must be related to Percy.

* **Transivity**; If Percy is related to Fred and Fred is Related to Ron, Ron and Percy must share parents, thus Ron and Percy are Related.

#### Example 2

Let $S$ be all real numbers

##### Define a Relation:

$x<y \iff x \enspace R \enspace y$

observe the following properties:

* **Non-Reflexive**; any number is not less than its own value.
* **Non-Symmetry**
  * Take 5 and 7, if $5<7$ , then $7 \nless 5$
* **Transitive**; It is true that if, say, $3<4$ and $4<5$ then $3<5$
  * This property is why we ordinarily write interval notation in this format, e.g. $x\in (3,5) \iff 3<x<5​$
    * Be careful though, using greater than symbols is not transitive per se and may lead to making transcription errors.

### Equivalence Class

Given a relation $R$ on some set $A$,

If $[a]$ is the set of all elements of $A$ that satisfy the relation for $a$:
$$
[a]_R = [a] = \{b \in A : b\enspace R \enspace a\}
$$
This is called the *equivalence class of*  $a$ *with respect to* $R$

#### Example

Let $S$ all real numbers.

**Define a relation:**

$x \enspace R \enspace y \iff x < y$

Let’s find the equivalence class of $[6]$:

$[6]_R = \{1,2,3,4,5\}$

#### Proposition

Let $R$ be an equivalence relation on $A$:

​	if $a,b \in A$, then either,

* $[a] = [b]$, OR
* $[a]\cap [b] = \emptyset$

So if $a$ and $b$ are both elements of $A$, then their equivalence classes are identical or absolutely different.



## Congruence Modulo *n*

<a name="aa(3)con"></a>

Let $a, b \in \mathbb{Z}$ and $n \in \mathbb{Z}^{+}$

We say that:

$a$ and $b$ are *congruent modulo n$ if $n \mid (a-b)$, and it is expressed:

$$
a\equiv b \enspace \pmod{n}
$$

or in other words:

$$
a\equiv b \enspace (mod n) \iff a = b + q\cdot n : q \in \mathbb{R}
$$


### Further Notation;
Generally the notation:

$$
a \mod n = r
$$

Refers to the remainder after $a$ has been divided by $n$ (i.e. the residue of $a$ modulo $n$)

So be careful:

| **This is a number** | **This is a statement about Divisibility** |
| -------------------- | ------------------------------------------ |
| $a \mod n = r$       | $a\equiv b \enspace \pmod{n}$              |

### The Euclidean Algorithm

if $a = q\cdot b +r$ then $a\equiv b \enspace \pmod{n}$

Recall from the *Euclidean Algorithm*:

$$
a = q\cdot b +r \implies \gcd(a,b) = \gcd(b,r)
$$

This translates to:

$a \equiv r \pmod{b} \implies \gcd(a,b) = \gcd(b,r)$

#### Eulers Theorem

*Euler's Theorem* (and hence *Fermat's Little Theorem) can now be restated in terms of modulos.

For relatively prime integers $a$ and $m \geq 1$:

$$
\begin{align}
m \mid (&a^{\phi (m)}-1) \\
&a^{\phi (m)} \equiv 1 \pmod{m}
\end{align}
$$

##### Fermats Little Theorem
The special case of $Euler's Theorem$, when $m$ is prime, is known as *Fermat's Little Theorem*.

$$
p \mid (a^p-a) \\
a^p \equiv a \pmod{p}
$$

### Residue of $a$ modulo $n$ (i.e. remainder of Division Algorithm)
If $a,b \in \mathbb{Z}$ and $n \in \mathbb{Z}^+$

Then $a = b \pmod{n}$ if and only if $a$ and $b$ have the same remainder when divided by $n$.

If the remainder is $r$ then:

$$
a \equiv r \pmod{n}
$$

> i.e. $a = p\cdot n +r, \enspace \exists p \in \mathbb{R}$

This valur $r$ is known as the *residue of a modulo n$ and can always be found to exist.

### Mod Laws
Let $n \in \mathbb{Z}^+$ and $ a,b,c,d, k \in \mathbb{Z}
nd $m \in \mathbb{N}$

1. $a \equiv b \pmod{n} \implies k\cdot a \equiv k\cdot b \pmod{n}​$
2. $\Big( a \equiv b \pmod{n} \enspace \wedge \enspace c = d \pmod{n} \Big)$
   1. $\implies (a+c) \equiv (b+d) \pmod{n}$, and also
   2. $\implies (a\cdot c) \equiv (b\cdot d) \pmod{n}$

### Congruence Class

Let $n \in \mathbb{Z}^+$ and $a \in \mathbb{Z}$

The congruence class of $a$ modulo $n$ is epxressed as $[a]_n$

It is the equivalence class of $a$ whereby the relation is a congruence in modulo $n$.

So in mathematical terms, the congruence class of $a$ is $[a]_n$:

$$
[a]_n = \{ b \in \mathbb{Z} : b \equiv a \pmod{n} \}
$$

> e.g. $[10]_3 = \{1,4,7,10,13,16 \dots 3n + r : n \in \mathbb{Z} \}$
>
> > Observe here that $r=1$


## The Ring [2.4]

<a name="aa(3)ringintro"></a>

The ring $\mathbb{Z}_m$ is the set of all congruence classes less than $m$ such that:

$$
\mathbb{Z}_m = \{ [0]_m, [1]_m, [2]_m, [3]_m, \dots [m-1]_m\}, \enspace  \forall m \in \mathbb{Z}^+
$$

### Example
We could list all the congruence classes of $\mathbb{Z}_5$:

$$
\mathbb{Z}_5 = \{[0]_5, [1]_5, [2]_5, [3]_5, [4]_5\}
$$

Where:

* $[0]_5 = \{\dots -5, 0, 5, 10, 15 \dots \}$
* $[1]_5 = \{\dots -4, 1, 6, 11, 16 \dots \}$
* $[2]_5 = \{ \dots -3, 2, 7, 12, 17, \dots \}$
* $[3]_5 = \{ \dots -2, 3, 8, 13, 18 \dots \}$
* $[4]_5 = \{\dots -1, 4, 9, 14, 19 \dots \}$

Hence $\mathbb{Z}_5$ could be expressed equivalently as:

$$
 \mathbb{Z}_5 = \{[5]_5, [11]_5, [17]_5, [19]_5, [9]_5\}
$$

### Operations on Congruence Classes
The elements of  $\mathbb{Z}_5$ can be manipulated algebraically, they have an algebraic structure, observe the following operations $\forall a,b,c \in \mathbb{Z}$.

#### Addition
Addition is commutative and associative:

$$
\begin{align}
[a]_m + [b]_m &= [a+b]_m \\
&= [b]_m + [a]_m
\end{align}
$$

#### Multiplication
Multiplication is commutative and associative

$$
\begin{align}
[a]_m \cdot [b]_m &= [a\cdot b]_m\\
&= [b]_m \cdot  [a]_m
\end{align}
$$

#### Linear Combination
Addition and Multiplication can be combined:
$$
[a]_m \cdot \big( [b]_m + [c]_m \big) = [a]_m \cdot [b]_m + [a]_m \cdot [c]_m
$$

---

---
# (4) Rings
<a name="aatop4"></a>

[Back to Top](#antoc)


* [Linear Congruence Equations](#aa(4)lincon)

* [Divisibility Tests](#aa(4)divtest)

* [The Ring](aa(4)thering)

* [Rings](#aa(4)rings)



## Linear Congruence Equations [2.1]

<a name="aa(4)lincon"></a>

A linear congruence equation is of the form:


$$
a\cdot x \equiv b \pmod{n}
$$

where $a,b \in \mathbb{z}$ and $n \in \mathbb{Z}^+$ are fixed numbers and $x \in \mathbb{Z}$ is a variable.

So an example could be:

$$
3x \equiv 7 \pmod{8}
$$

The solution to this equation is the set of all x values values for which the expression is true, i.e. the solution is the set $X$ such that:

$$
X = \{x: 3x \equiv 7 \pmod{8} \}
$$

### Coingruence Class
if some $z \in \mathbb{Z}$ is a solution of a linear congruence equation, then all members of the congruence class $[z]_n$ are also solutions as well.

The complete set of solutions is the congruence class $[z]_{\frac{n}{d}}.

### Testing whether a solution exists
A linear congruence equation only has a solution, if and only if:

$$
\gcd(a,n) \mid b
$$

#### Example

* $2x \equiv 1 \pmod{4}$ has **no** solution because $\gcd(2,4) = 2 \nmid 1$
* $2x \equiv 1 \pmod{3}$ has a solution because $\gcd(2,3) = 1 \mid 1$
* $ax \equiv b \pmod{p}$ has a solution **only if** $\gcd(a,p) \mid b$

### Quick solution for multiples

if $a \neq 0$ then,
$$
ax \equiv ab \pmod{n} \iff x \equiv b \pmod{\small\frac{n}{\gcd(a,n)}}
$$

#### Example

Solve,
$$
3x \equiv 3 \pmod{9}
$$
$3 \neq 0$, thus:
$$
\begin{align}
3x \equiv 3 \times 1 \pmod{9} \iff x &\equiv 1 \pmod{ \small{\frac{9}{\gcd(3,9)}} }\\
\implies x &\equiv 1 \pmod{\small {\frac{9}{3}}}\\
\implies x & \equiv 1 \pmod{3}
\end{align}
$$
Thus we know that the difference between $x$ and $1$ is always divisible by $3$, so:
$$
x = \{1, 4, 7, 10, 13, 16, 19, 22, 25, 28, 31, 34, \dots\}
$$
So the solution is the congruence class:
$$
[1]_3 = \left \{ x : x = 1 + 3n, \enspace n \in \mathbb{Z} \right \}
$$

### General Method for Solving Linear Congruence Equations

Consider the equation $ax \equiv b \pmod{n}$, where $ d = \gcd(a,n)$ and $ d \mid b$

* Is there a solution for $x$?
  * There is because $\gcd(a,n) \mid b$
* A solution can thus be found using the *Euclidean Algorithm*
* If $x=z$ is a solution to the equation, then the complete set of solutions is $[z]_\frac{n}{d}$
  * This is proven on p. 64 of the TB
  * Although all elements of $[Z]_n$ are solutions, the set may not contain all the solutions.

#### Example 1 (*Euclidean Algorithm*)

Give the complete set of solutions to $34x \equiv 20 \pmod{60}$.

First observe that $\gcd(34, 60) = 2 | 20$, thus there is a solution for $x$.

If $x$ is an integer solution, then:
$$
\begin{align}
60 \mid (34x-20) &\implies 60t = 34x-20 \enspace t \in \mathbb{Z} \\
&\implies 20 = 34x + 60t
\end{align}
$$
The values of $x$ and $t$ can be solved via the *Euclidean Algorithm by using back substitution

##### Euclidean Algorithm

We are concerned with $\gcd(34,60)$, because that's what our variables are multiplied by:
$$
\begin{alignat}{2}
60 = 1 \times 34 +26 &\implies 26 = 60-1 \times 34 \qquad &(1) \\
34 = 1\times 26 + 8 &\implies 8 = 34-1\times 26 \qquad &(2) \\
26 = 3 \times 8 + 2 & \implies 2 = 26 -3 \times 8 \qquad & (3) \\
\ \\
8 = 4\times 2 + 0 &\implies \gcd(60, 34) = 2 &
\end{alignat}
$$
Now recall that we are trying to find the values of $x​$ and $t​$:
$$
20 = 34x+60t
$$
We will solve for $\gcd(34,60) = 2$ in terms of 34 and 60, because $\gcd(34, 60) = 2 \mid 20$ we will be able to multiply by a factor of $20 \mid 2$ afterwards and have all integer solutions.

###### Backward Substitution

*State $(3)$*
$$
2 = 26-3\times 8
$$
*Sub $(2)$*
$$
\begin{align}
2 &= 26 -3 \cdot (34-26) \\
 &= 26 -3 \times 34 -3\times 26 \\
 &= 4 \times 60 -7 \times 34
\end{align}
$$
*Sub $(1)$*
$$
\begin{align}
2 &= 4 \cdot (60-34)-3\times 34 \\
 &= 4 \times 60 -4 \times 34 -3 \times 34 \\
&= 4 \times 60 - 7 \times 34
\end{align}
$$
*Multiply by $\frac{20}{2}$*
$$
\begin{align}
20 &= 40 \times 60 - 70\times 34 \\
 &= 34 \times (-70) + 60 \times 40
\end{align}
$$

###### Solve for $x$ and $t$

Thus,
$$
\begin{alignat}{4}
20 &= 34 \cdot &x      &+ 60 \cdot t& \\
20 &= 34 \times &(-70) &+ 60 \times 40& \\
\ \\
&&&\implies x = -70\\
&&&\implies t = 40
\end{alignat}
$$
Hence,
$$
34 \times (-70) \equiv 20 \pmod{60}
$$
And,
$$
\begin{align}
x &= -70 \pmod{60} \\
  &= 5
\end{align}
$$

##### Conclusion

Thus a soltuion is $x = 5$,

The set of all solutions is $[z]_{\frac{n}{d}}​$ ,

where:

* $n$ is the modulo
* $d = \gcd(a,n)​$
* $z$ is the solution to $x$

Thus the solution set for $x$ is the congruence class:
$$
[5]_{\frac{60}{2}} = [5]_{30} = \left \{  \dots -25, 5, 35, 65, 95 \dots \right \}
$$


#### Example 2 (Multiplicative Inverse)

Solve $17x \equiv 3 \pmod{29}$,

In thgis case because $\gcd(a,n) = 1$, we can solve this using a multiplicative inverse as an alternate method (p. 66 of TB).

The multiplicative inverse cannot be solved for when $\gcd(a,n) \neq 1$ (p. 66 of TB).

What we are looking for, is a multiplicative inverse, we will call it $v$, such that:
$$
17 \times v \equiv 1 \pmod{29} \\
$$
When we find $v$, we expect that:
$$
x \equiv 3 \cdot 3v \pmod{29}
$$
Now, if:
$$
17\cdot v \equiv 1 \pmod{29}
$$
Then:
$$
\begin{align}
17\cdot v &= (1-29\cdot w) \enspace : \enspace w \in \mathbb{Z}\\
1 &= 17\cdot v + 29w
\end{align}
$$

##### Euclidean Algorithm

Now use the **Euclidean Algorithm** on the numbers $17$ and $29$.

We are concerned with $\gcd(17,29)$, because that's what our variables are multiplied by:
$$
\begin{alignat}{2}
29 = 1 \times 17 + 12 &\implies 12 = 29-17 \qquad &(1) \\
17 = 1\times 12 + 5 &\implies 5 = 17-12 \qquad &(2) \\
12 = 1\times 5 + 2 &\implies 2 = 12-2\times 5 \qquad &(3) \\
5 = 2 \times 2 + 1 & \implies 1 = 5 - 2 \times 2 \qquad & (4) \\
\ \\
2 = 2\times 1 + 0 &\implies \gcd(29, 17) = 1 &
\end{alignat}
$$

###### Backwards Substitution

So our goal is to find $v$, $w$:
$$
17\cdot v + 29 \cdot w =1
$$
*state $(4)$*
$$
1 = 5 -2\times2
$$
*sub $(3)$*
$$
\begin{align}
1 &= 5 - 2 \times (12-2 \times 5) \\
&= 5 - 2 \times 12 + 4 \times 5 \\
&= 5 \times 5 - 2 \times 12
\end{align}
$$
*sub $(2)$*
$$
\begin{align}
1 &= 5 \times (17 - 12) - 2 \times 12 \\
  &= 5 \times 17 - 7 \times 29 + 7 \times 17 \\
  &= 12 \times 17 - 7 \times 29 \\
\end{align}
$$
*Sub $(1)$*
$$
\begin{align}
1 &= 5 \times 17 - 7 \times (29-17) \\
  &= 5 \times 17 - 7 \times 29 + 7 \times 17 \\
  &= 12 \times 17 - 7 \times 29
\end{align}
$$

###### Solve for $x$ and $t$

Now;
$$
\begin{alignat}{4}
1 &= 17 \cdot &v      &+ 29 \cdot w& \\
1 &= 17 \times &12 &+ 29 \times (-7)& \\
\ \\
&&&\implies v = 12\\
&&&\implies w = 1
\end{alignat}
$$
The original question is:
$$
\begin{align}
17x &\equiv 3 \pmod{29} \\
17x \times 12 &\equiv 3 \times 12 \pmod{29} \\
(17\times 12) x &\equiv 12 \times 3 \pmod{29} \\
(1)x &\equiv 12 \times 3 \pmod{29} \\
x &\equiv 36 \pmod{29}
\end{align}
$$
Thus $x = 36$ is a solution, hence the residue is a solution:
$$
\begin{align}
x &= 36 \pmod{29} \\
  &= 7
\end{align}
$$

##### Conclusion; Solve the set of solutions

The complete set of solutions is the congruence class:
$$
[7]_{\frac{n}{d}}
$$
Where $n$ is the modulo and $d = \gcd(a, n)$:
$$
\begin{align}
x = [7]_{\frac{n}{d}} = [7]_{\frac{n}{d}}=[7]_{29} &= \left \{ \dots, -22, 7, 36, 65 \dots \right \}\\
&= 7 + 29 \cdot q \enspace : \enspace q \in \mathbb{Z}
\end{align}
$$


## Divisibility Tests [2.2]

<a name="aa(4)divtest"></a>

This isn't a particularly important part of the topic, but a cool algebra trick.

It is possible to test for divisibility by 9 or 3 by summing the components, e.g.:
$$
\begin{align}
9|832005 &\iff 9 \mid (8+3+2+0+0+5) \\
&\iff 9 \mid (18)
\end{align}
$$
This can be generalised into a theorem:

An integer $x = x_nx_{n-1}x_{n-2} \dots x_2x_1x_0​$ (in decimal notation, <sub> as in each $x​$ represents the a part of the unit value of the number  </sub>) is divisible by 9 if and only if $( x_n + x_{n-1} + x_{n-2} + x_2 + x_1 +x_0)​$ is divisible by 9

### Proof

First observe that any integer can be expressed as a sum of its unit values (e.g. $342 = 3 \times 100 + 4 \times 10 + 1 \times 2$), hence:
$$
\begin{align}
x = (x_n \times 10^n) + (x_{n-1} \times 10^{n-1}) + (x_{n-2} \times 10^{n-2}) \dots (x_2 \times 10^2) + (x_1 \times 10) + x_0
\end{align}
$$
Now utilise the fact that $10 \mod 9=1$ and that the $\mod \ $ operator distributes over addition:
$$
\begin{alignat}{2}
x &\equiv (x_n \times 1^n) + (x_{n-1} \times 1^{n-1}) + (x_{n-2} \times 1^{n-2}) \dots (x_2 \times 1^2) + (x_1 \times 1) + x_0 &\pmod{9}\\
&\equiv  x_n + x_{n-1} + x_{n-2} + x_2 + x_1 +x_0 &\pmod{9}
\end{alignat}
$$
Now we know that $9 \mid x \iff x \equiv 0 \pmod{9}$, thus
$$
\begin{align}
9 \mid x &\iff  (x_n + x_{n-1} + x_{n-2} + x_2 + x_1 +x_0) \pmod{9} \\
& \iff  x_n + x_{n-1} + x_{n-2} + x_2 + x_1 +x_0
\end{align}
$$

 #### In Terms of 3

Observe that $9= 3 \times 3; hence the same rules apply for the value of 3, and a similar proof.



## The Ring [2.4]

<a name="aa(4)thering"></a>

For $n \in \mathbb{Z}$:
$$
\mathbb{Z}_n := \left \{ [0]_n, [1]_n, [2]_n, \dots [n-1]_n  \right \}
$$

### Example

$$
\mathbb{Z}_4 =\left \{ [0]_4, [1]_4, [2]_4, [3]_4 \right \}
$$

Recall that:

$$
\begin{align}
[0]_4 &= \left \{  \dots, -4, 0, 4, 8, 12, 16, \dots \right \} \\
[1]_4 &= \left \{  \dots, -3, 1, 5, 9, 13 \dots \right \} \\
[2]_4 &= \left \{  \dots, -2, 2, 6, 10, 14 \dots \right \} \\
[3]_4 &= \left \{  \dots, -1, 7, 11, 15, 19 \dots \right \}
\end{align}
$$

Hence,

$$
\begin{align}
 \mathbb{Z}_4 &= \left \{ [0]_4, [1]_4, [2]_4, [3]_4 \right \}
 \mathbb{Z}_4 &= \left \{ [8]_4, [9]_4, [10]_4, [7]_4 \right \}
\end{align}
$$


### Algebra with Rings

In order to do algebra in $\mathbb{Z}_m$ we need some means by which to manipulate the elements of $\mathbb{Z}_m$.

Take $a, b, c \in \mathbb{Z}$:

$$
[a]_m, [b]_m, [c]_m \in \mathbb{Z}
$$

#### Addition
We define:

$$
[a]_m + [b]_m := [a+b]_m
$$

Because:

$$
\begin{align}
[a]_m = \left \{ x: \enspace x = a + qm, \enspace q \in \mathbb{Z} \right \} \\
[b]_m = \left \{ y: \enspace x = a + pm, \enspace p \in \mathbb{Z} \right \} \\
\end{align}
$$

We choose to define:

$$
\begin{align}
[a+b]_m = \left \{ x+y \right \} \\
\end{align}
$$



Addition is commutative

## Rings [2.5]

<a name="aa(4)rings"></a>

### Definitions and Axioms

A ring is a set $R$ that has two binary operations:

* One that is associated with Addition
  * for which the following symbol is used $(+)$
* One that is associated with Multiplication $(*)$
  * Occassionally $(\cdot)$ is used as well



> #### Binary Operations
>
> Binary operations are basically an operation between two values, a formal definition of binary operations is:
>
> A **Binary Operation** $*$ on some set S is a function $f_*$:
> $$
> f_*\enspace : \enspace  S\times S \rightarrow S \enspace  : \enspace (a,b) \mapsto f_*(a,b)
> $$



And satisfies the axioms of a ring:

1. ***Associativity of Addition***

   a)  $(\forall a, b, c \in R) (a+b) + c = a + (b+c)$

2. ***Commutativity of Addition***

   a) $(\forall a, b \in R) \enspace a + b = b + a$

3. ***Additive Elements Exists***

   a) $(\forall a, b \in R) \wedge (\exists0 \in R) \enspace a + 0 = 0 + a = 0$

4. ***Associativity of Addition***

   a)  $(\forall a, b, c \in R) (a+b) + c = a + (b+c)$

5. ***Commutativity of Addition***

   a) $(\forall a, b \in R) \enspace a + b = b + a$

6. ***Additive Elements Exists***

   a) $(\forall a, b \in R) \wedge (\exists0 \in R) \enspace a + 0 = 0 + a = 0$



   #### Further Axioms

     These further axioms provide different classes of  following axioms are not necessarily exhibited by rings, but if they are the rings



   7. **Commutativity of Multiplication***
      1. $(\forall a,b \in R) a \cdot b = b \cdot a$
         1. A ring that satisfies this property is called a **commutative Ring**
   8. **Existence of a Multiplicative identity Element (a ring with Unity)**
      1. $(\exists1 \in R) (\forall a \in R) \enspace 1 \cdot a = a \cdot 1 = a$
         1. A ring that satisfies this property is called a **a ring with identity** or equivalently a **a ring with unity**

   ##### Examples of Rings

   * $\mathbb{N}$ is not a ring, because there is no additive inverse
   * $\mathbb{Z}, \mathbb{R}, \mathbb{Q}, \mathbb{C}$ are all commutative rings with identity/unity
   * The set of all even integers ($2\mathbb{Z}$) is a ring because
     * It is closed under addition and multiplicaiton
     * It satisfies all other axioms
     * It is a commutative ring
     * Because 1 is not even there is no multiplicative identity, hence it is NOT a ring with unity.
   * Square matrices are rings with unity/identity
     * They are not commutative because the order of multiplication is important.



   #### Properties of Rings

   Proofs for these properties are provided in the textbook

   #### Unique Identitities

   * The additive Identity of a ring is always unique
   * The additive inverse of a ring is always unique
   * The multiplicative identity of a ring is always unique
     * (i.e. If the ring has a multiplicative inverse)

   #### Algebraic Rules

   The following rules hold for rings:

   Let $a, b \in R$;

   1. $0a = a0 =0$
   2. $a(-b)=-(ab)$
   3. $-(-a)=a$
   4. $(-a)(-b) = ab$
   5. $(-1)a=-a$
      1. Assuming a multiplicative identity exists for the ring $R$



   ### Zero Divisors

   An element of some ring $R$ is a **zero divisor** if:
   $$
   \begin{align}
   &a,b \in R: \\
   \ \\
   &(\forall a \in R : a \neq 0) (\exists b \in R : b \neq 0) : \\
   \ \\
   &\qquad \qquad \qquad ab = 0 \enspace \vee \enspace ba = 0
   \end{align}
   $$

   #### Examples

   $$
   2,3 \in \mathbb{Z}_6 : \\
   \ \\
   2 * 3 = [6]_6 = [0]_6
   $$



Hence, 2 and 3 are both **Zero Divisors**

### Units

An element $a \in R$ of some ring $R$ is a **unit** if:

The element always has a multiplicative inverse, i.e.
$$
a \text{ is a unit} \iff \exists b \in R : ab = ba =1
$$

* 1 is a unit of all rings
* Any ring with unity/identity is such that -1 is a unit
  * Because (-1) \times (-1) = 1

#### Application

If $a \in \mathbb{Z}_n$ is a unit, then the equation:
$$
x \equiv b \pmod{n}
$$
Can be solved by multiplying both sides by $a^{-1}$

##### Example

$$
3x \equiv 5 \pmod{7}
$$

For $3\in \mathbb{Z}_7$ there exists an inverse:
$$
3 \times 5 = 1 \implies 3^{-1} = 5
$$
3 is a unit because there exists 5 such that:
$$
3 \times 5 = 5\times 3 = 1 \in \mathbb{Z}_7
$$
Hence,
$$
\begin{alignat}{2}
3x &\equiv 5 &\pmod{7} \\
5 \times 3x &\equiv 5 \times 5 &\pmod{7} \\
15x &\equiv 25 &\pmod{7} \\
(1x) &\equiv 25 &\pmod{7} \\
x &\equiv 25 &\pmod{7} \\
&\equiv 3 &\pmod{7} \\
&= [3]_7 &\pmod{7} \\
\end{alignat}
$$


<a name="notboth"></a>

### Unit or Zero Divisor but not both

an element $a \in R$ cannot be both a zero divisor and a unit

​	Because the prior multiplies to give zero and the latter multiplies to give 1.



# (5) Fields and Complex Numbers
<a name="aatop5"></a>

> TB: [2.5], [2.6] </sub>***

[Back to Top](#antoc)


* [Rings](#aa(5)rings2)
* [The Field of Complex Numbers](aa(5)fieldc)

## Rings [2.5]

<a name="aa(5)rings2"></a>

### Integral Domain

An integral domain is a ring that is:

 	1. Is commutative
 	2. Is with unity/identity
 	3. Has no Zero Divisors

#### Properties of Integral Domains

In an integral domain we can cancel, i.e.:
$$
(c \neq 0) \enspace \wedge \enspace (ac = bc) \implies a = b
$$

##### Proof

$$
\begin{align}
ac &= bc \\
ac - bc = 0 \\
c\cdot (a-b) = 0 \\
\ \\
\text{But} \\
c\neq 0 \\
\implies a - b = 0 \\
a=b
\end{align}
$$

#### Example

So for example $\mathbb{Z}_5$ is an integral domain because:

1. The elements of $\mathbb{Z}_5$ are commutative
2. $1 \in \mathbb{Z}_5$, hence it is with unity
3. There are no non-zero values in $\mathbb{Z}_5$ that multiply to give 0

Further,

Take $\mathbb{Z}_p : p = \left \{ 2,3, 5, 7, 11, 13, 17, \dots \right \}$

​	All $\mathbb{Z}_p$ are integral Domains



### Fields

A field is:

1. An integral Domain
2. In which every non-zero element is a unit.



So for clarity a field is a set $F$ that is:

1. A Ring
2. A commutative Ring
3. A Ring with unity/identity
4. All elements are units
   1. This necessitates that no elements can be zero-divisors because they are [mutually exclusive](#notboth)

#### Examples

$\mathbb{N}$ is not a Ring because it does not contain an additive identify $0$

$\mathbb{Z}$ is an integral domain because it is commutative, with unity and has no non-zero value that multiply to give 0;

It is NOT a field because not all values have an inverse (e.g. $3^{-1} = \frac{1}{3} \notin \mathbb{Z}$)

$\mathbb{Q}$, $\mathbb{R}$, $\mathbb{C}$ are all fields because every element has a multiplicative identity and are hence units.



## The Field of Complex Numbers

<a name="aa(5)fieldc"></a>

The field of complex numbers is:
$$
\mathbb{C} = \left \{ a + b i : a, b \in \mathbb{R} \right \}
$$
Addition is defined by:
$$
(a+bi) + (c+di) = (a+c) + (b+d)i
$$
Multiplication is defined by:
$$
(a+bi)\cdot (c + di) = (ac-bd) + (ad+bc)i
$$
More over we represent the real and imaginary parts of a complex number thusly:
$$
z = a + bi \\
\implies \text{Re}(z) = a \enspace ; \enspace \text{Im}(z) =b
$$

### The set of Complex Numbers is a Field

Remember that a field is:

1. A Ring
2. A Commutative Ring
3. A Ring with Identity
4. All elements are units
   1. This necessitates that no elements can be zero-divisors, for they are mutually exclusive.



In this case the complex numbers:

1. Are indeed a ring
2. Complex Numbers are commutative
3. There existws a multiplicative Identity ($z = 1 + 0i$)
4. Every element has an inverse
   1. $z \times \frac{1}{z} = 1$

### Polar Notation

A complex Number can be represented on the complex Plane:

![1551604985277](1551604985277.png)

And any complex number can be represented also in polar notation:
$$
\begin{align}
z &= a +bi = r \cdot \text{cis}(\theta) \\
\end{align}
$$
Where:

> $r = \sqrt{a^2 +b^2} \\
> \theta = \text{Atan}(\frac{b}{a})$

And the combination is equivalent because:
$$
\begin{align}
\text{cis}(\theta) & = \cos(\theta) + i \cdot \sin(\theta) \\
&= \cos{\theta} + i\cdot \sin{\left ( \text{Asin}\left( \frac{b}{a} \right ) \right )} \\
&=a + bi
\end{align}
$$
Flowing from power series for exponential, cosine and sine functions we have also:
$$
z = a + bi = r \text{cis}(\theta) = e^{i\theta}
$$


### Multiplying Complex Numbers

Polar notation makes it far easier to multiply complex numbers

> Remember that multiplying a number on the complex plane is [really a transformative process](https://www.youtube.com/watch?v=mvmuCPvRoWQ) involving scaling and rotating the plane from the point 1 (the multiplicative identity) top the point of the multiplier.
>
> Hence it stands to reason that the distance from the origin of the new point will be larger by a factor of the scaling and the rotation on the plane will simply be added.

For:
$$
u = r\cdot \text{cis}(\theta) \enspace \text{and} \enspace v = s \cdot \text{cis}(\phi) \\
\ \\
u\cdot v = rs \cdot \text{cis}(\phi + \theta)
$$




 ### Power of Complex Numbers (De Moivre's Theorem)

If follows algebraically that raising complex numbers to the power of some $n$:


$$
\begin{align}
z &= r \cdot \text{cis}(\theta) \\
  &\implies z^n = r^n \cdot \text{cis}(n\cdot \theta) \enspace : \enspace n \in \mathbb{Z^*}
\end{align}
$$

> Recall that $\mathbb{Z^*}$ is the set of non-negative integers {0, 1, 2, 3, 4 ...}.
>
> > This is an important distinction from $\mathbb{N}$ because although many texts provide $0 \notin \mathbb{N}$ using the reasoning that the naturals are the various possible sums of 1, many authors provide $0 \in \mathbb{N}$ where it is convenient, so try not to use $\mathbb{N}$ because it can be ambiguous



### Roots of Complex Numbers

Multiple Complex Numbers, when raised to a power, may equal the same end result, hence solutions for $z$ given $z^n$ are:
$$
z^{1/n} = r ^{1/n} \cdot \text{cis}\left( \frac{\theta + 2k\pi}{n} \right ), \quad \text{for} k = 1,2,3, \dots (n-1)
$$
There are always $n$ roots.



# Endnotes

Notes on Polynomials and the Fundamental Theorem of Arithmetic are contained in the PDF file.

I don't have any notes whatsoever on anything thereafter.






# collapsible markdown?
<details><summary>CLICK ME</summary><p>
## Test
</p>
</details>


  <br><!-- WSpace Important --><details closed markdown="1"><summary><p>

# Notes on Markdown
</p></summary><p>

* Small MathBlocks on iPhone

  * If numbered equations are used, they will render extremely small on an iPhone, is the trade off worth it?

    * It's relatively easy to enable and disable numbered mathblocks in *Typora* on the fly through the preferences <kbd> Ctrl </kbd> + <kbd> , </kbd>  <sub> on mac <kbd> ⌘ </kbd> + <kbd> , </kbd> </sub>



[Topic 1][14]

[^1]:	www.google.com

[^2]:	https://en.wikipedia.org/wiki/Subset





</p>
<!--Newline Important-->
</details>
<!--Newline Important-->
