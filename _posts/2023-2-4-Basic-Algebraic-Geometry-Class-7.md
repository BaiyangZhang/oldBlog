---
layout:     post   				                    # 使用的布局（不需要改）
title:      Basic Algebraic Geometry Class 7		# 标题 
subtitle:   Class 7
date:       2023-2-4 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/mathArt3.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - Math
    - Commutative Algebra
    - Notes
---

### Localization

Localization is a technique used in commutative algebra in both algebra and geometry. In geometry it is used when we want to look at points in varieties locally, hence the name. 

Let $R$ be a ring (commutative, unital). The general idea is that, given a certain subset $S\subset R$, we want to introduce the invers of $S$, namely the inverse of all the elements $s\in S$, into $R$. In other words, we want to `division` by $S$. 

As a motivating example, look at the ring of integers $\mathbb{Z}$. Let $S$ be the non-zero integers, $S = \mathbb{Z}-0$. Inverting all elements of $S$ one obtains the ring of rational numbers $\mathbb{Q}$, or the field of rational numbers since all the elements are invertible. Formally, a rational number can be considered as a pair of integers $(a,s)$ where $a\in\mathbb{Z}$ and $s\in S$, plus the equivalence relation
$$
(a,s) \sim (a',s') \iff as'=a's,
$$
then the equivalent class $(a,s)$ is denoted $a / s$, and addition and multiplication is `defined` by 
$$
(a,s)+(a',s') = (as'+a's,ss'),\quad (a,s)\cdot (a',s')=(aa',ss').
$$

Now we want to generalize this procedure to arbitrary rings. The first observation is that one can not introduce the inverse of just about any arbitrary subsets, but just `multiplicatively closed` sets, namely sets that is closed under multiplication. To be accurate, A subset $S\subset R$ is said to be multiplicatively closed if 
$$
1\in S \text{ and } s,s'\in S\implies ss'\in S.
$$

In spirits of construction of rational numbers from integers, we define the equivalence class $(a,s),a\in R,s\in S$ under the equivalence relation 
$$
(a,s)\sim (a',s') \iff \exists u\in S \text{ such that } u(as'-a's)=0.
$$
The set of equivalence classes is denoted by $S^{-1}R$, with addition and multiplication defined as before. 

Readers can check that $R^{-1}S$ indeed form a ring, called the `localization` of $R$ at $S$. 

Note that the condition 
$$
\exists u\in S \text{ such that } u(as'-a's)=0
$$
means that if $R$ is a integral domain, then $as'-a's$ itself must be zero since there are no zero devisors. $u$ should not be $0$ or we will get a trivial localization. 

There is a natural isomorphic map from $R$ to $S^{-1}R$ defined by $\iota : a\mapsto a / 1$. Surprisingly the map is not always injective, it is only so when $S$ does not contain zero divisors. To see it, take a look at the kernel of $\iota$,
$$
\text{ker }(\iota) = \left\{ a\in R \,\middle\vert\, \frac{a}{1}=\frac{0}{1} \right\}, 
$$
the equivalence relations says that the equal sign holds if there exists non-zero $u\in S$ such that 
$$
u(a\cdot 1-1\cdot 0)=ua=0,
$$
namely if $u$ is a zero divisor. 

By the way, $S$ contains zero divisors does **not** necessarily means that $S$ contains zero itself, think about it. 

Given a ring it is always important to first identify its `zero` and `unity`. The zero element of $S^{-1}R$ is the equivalence class $[0 / 1]$ and unity $[1 / 1]$. Here the bracket denotes the equivalence class. 

If $S$ has only one element $1$, in terminology if you localize $R$ with respect to $1$, then you are adding nothing new to the ring, thus $S^{-1}R=R$. If $S=0$, then the kernel of $\iota$ is the whole ring $R$ thus $\iota$ would map everything to $0$, namely $0^{-1}R$ is the trivial ring.

In the following we list some important examples of localization.

- **Fields of fractions.** If $R$ is an integral domain and $S=R-0$, then $S^{-1}R$ is the field of fractions of $R$.
- **Localization at an element.** If we want to localize $R$ at an element $a$, it is not enough to just write $a^{-1}R$ since the thing we localized at must be multiplicatively closed. Thus we have to make $a$ into a multiplicative set, by defining
$$
S= \text{ all the powers of }a, S = \left\{ a^{n} \,\middle\vert\, n\in \mathbb{N} \right\}
$$
  then we can localized $R$ at $S$, the resulting ring $S^{-1}R$ is denoted $R_{a}$, called the localization of $R$ at the element $a$.
- **Localization at a prime ideal.** If ${\frak p}\in R$ is a prime ideal, we can construct a multiplicative set $R-{\frak p}$, it is closed under multiplication since, by the definition of prime ideals, 
$$
a \notin {\frak p} \text{ and } b\notin {\frak p} \implies a\cdot p\notin {\frak p}.
$$
  We can go on and localize $R$ at $S$, the resulting ring is denoted $R_{\frak p}$, called the localization of $R$ at the prime ideal ${\frak p}$. 
  
  Note the potential confusion between two similar but opposite concepts, the localization at an element and at a prime ideal. The localization of an element $R_{a}$ means $a$ is made inversible in $R_{a}$, however the localization of a prime ideal means that everything **but** the prime ideal ${\frak p}$ is made inversible in $R_{\frak p}$.

- - -

When we localize rings, we would like to know what is the relation between the prime ideals in the original ring and the prime ideals in the localized ring. 

Let $S$ be a multiplicatively closed subset of $R$, and denote 
$$
\sigma: R\to S^{-1}R
$$
the canonical map (I used $\iota$ before, sorry for the arbitrary use of notations).

Since $\sigma$ is a ring homomorphism, we know that if $J$ is an ideal in $R^{-1}R$, then the pre-image of $J$ is also an ideal in $R$. It has nothing to do with special properties of the canonical map, it is general for all ring homomorphisms.

Without prove, we introduce the following proposition.

**Proposition.** The association 
$$
J\mapsto \sigma^{-1}(J)
$$
defines a bijection between the set of prime rings in $S^{-1}R$ and the set of prime rings in $R$ that do not intersect $S$. 

This bijections contains two sides of information. On the one hand, if $J$ is a prime ideal in $S^{-1}R$, then $\sigma^{-1}(J)$ is a prime ideal in $R$ that does not intersect $S$. On the other hand, for all prime ideals in $I\subset R$, if $I\cap S=\emptyset$, then $\sigma(I)$ is a prime ideal in the localized ring. $I$ must not intersect $S$ since if it does, then $I$ contains elements in $S$, whose image under $\sigma$ are units, and when units appear in an ideal the ideal is bounded to be the whole ring. 

**Corollary.** Let ${\frak p}\subset R$ be a prime ideal in $R$, and $S=R-{\frak p}$. The association 
$$
J \to \sigma^{-1}(J)
$$
is a bijection between the prime ideals in $R_{\frak p}$, or $S^{-1}R$, and the prime ideals contained in ${\frak p}$. 

Note that an ideal contained in ${\frak p}$ just means the ideal does not intersect $R-{\frak p}=S$.

### Local Rings

A ring is called a `local ring` if it has exactly one maximal ideal. 

Local rings has a close relation between the localization of a ring at the prime ideals. Let ${\frak p}\subset R$ be a prime ideal, the localization of $R$ at ${\frak p}$, or $R_{\frak p}$ is a local ring, with maximal ideal
$$
\frac{\frak p}{R-{\frak p}}:=\left\{ \frac{p}{r} \,\middle\vert\, p\in {\frak p},\,r\in R-{\frak p} \right\} .
$$

To have a feeling about this, consider a maximal ideal $M$ in $R_{\frak p}$. Since maximal ideals are automatically prime ideals, we knwo that $\sigma^{-1}(M)$ is a prime ideal in $R$ that is contained in ${\frak p}$, furthermore, since $\sigma$ and its inverse respects inclusion, namely respects the order between sets, $M$ being the maximal ideal means that $\sigma^{-1}(M)$ must be the biggest ring contained in ${\frak p}$, namely ${\frak p}$ itself, ${\frak p}=\sigma^{-1}(M)$. This means that $M=\sigma({\frak p})$, which is nothing but ${\frak p} / (R-{\frak p})$.

Returning to the case of an affine variety $X,\mathcal{O}(X)$ and a point $a\in X$. We will use this to shed light on the `stalk` denoted $\mathcal{O}_{X,a}$. 

- - -

### Local Study

Sometimes in an affine variety we want to study the regular functions that are defined "at a point $a$", namely locally at point $a$, or in an arbitrarily small open neighborhood of $a$. We want to study how regular functions are seen by a point $a$. For a near-sighted point $a$, it can only see what happens in its neighborhood, if there is another point $b$ distant from $a$, then $a$ doesn't really care what $b$ has to say about a regular function. As far as $a$ is concerned, two functions are the same if they agree with each other at some neighborhood of $a$, no matter how small the neighborhood is. This motivates the following definition.

**Stalks and germs.** Let $\mathcal{F}$ be a `presheaf`on a topological space $X$. Let $a\in X$ be a point in $X$. The `stalk` of $\mathcal{F}$ at $a$ is defined as
$$
\mathcal{F}_{a} := \left\{ (U,\phi) \,\middle\vert\, U\subset X \text{ containing } a,\,\phi \in \mathcal{F}(U) \right\} / \sim 
$$
with the equivalence relation
$$
(U,\phi)\sim (U',\phi') \text{ if } \phi\mid_{V} =\phi'\mid _{V}
$$
for some 
$$
V\subset U\cap U' \text{ containing } a.
$$

Elements of $\mathcal{F}_{a}$ are called `germs` of $\mathcal{F}$ at $a$. The terminology is because in complex plane holomorphic functions can be "grown" out of a locally defined function, I guess.

Morally, germs are functions defined locally at $a$, namely at an arbitrarily small neighborhood of $a$: their properties depend on no other points.

For example, consider the stalk of $\mathcal{F}$ on $\mathbb{A}^{1}$, namely the real line, at the origin $0$. Regular functions are the ratio of two polynomial functions $f(x) / g(x)$, for it to be well defined at $0$ we just need 
$$
g(0) \neq 0 .
$$
It does not matter if $g(x)$ vanishes at some other points. 

To better understand these local objects, we need the notion of localization. Returning to the case of an affine variety $(X,\mathcal{O}_ {X})$, given a point $a\in X$, the machinery of localization sheds light on the `stalk` of $\mathcal{O}_ {X}$ at $a$, denoted $\mathcal{O}_ {X,a}$. 

But before that, let's look at an easier version of localization, namely not the localization of prime ideals, but at an element of the ring. 

### First Geometric Application

Now we have two concepts, one geometrical, one algebraic. 

-  The open set given by a polynomial function, and the regular functions that could be defined on it.
-  The localization of a ring at some multiplicative closed set. 

It is far from obvious, but there indeed exists a deep relation between them, which we will talk about. 

Let $X$ be an algebraic set, and $f\in\mathcal{O}(X)$ some polynomial functions (quotient $I(X)$, of course) defined on $X$. Recall that $f$ also defines an open set denoted
$$
U_ {f} = \left\{ x\in X \,\middle\vert\, f(x)\neq 0 \right\} .
$$

**Proposition.** The ring of regular functions on $U_ {f}$ is the ring localization of $\mathcal{O}(X)$ at $f$, i.e.
$$
\mathcal{O}_ {X}(U_ {f}) = \text{ localization of } \mathcal{O} (X) \text{ at } f . 
$$

Recall that the sheaf on $U_ {f}$ is 
$$
\mathcal{O}_ {X}(U_ {f}) = \left\{ \frac{g(x)}{f^{n}(x)} \,\middle\vert\, g(x)\in \mathcal{O}(X) \right\} 
\tag{1}
$$

and the localization of $\mathcal{O}(X)$ at $f$ is 
$$
\mathcal{O}(X)_ {f}:= \left\{ (g,f^{n}) \,\middle\vert\, g\in \mathcal{O}(X) \right\} \text{ with equivalence relation},
$$
sometimes denoted 
$$
\mathcal{O}(X)_ {f}:= \left\{ \frac{g}{f^{n}} \,\middle\vert\, g\in \mathcal{O}(X) \right\} \text{ with equivalence relation},
\tag{2}
$$

comparing Eq. (1) with Eq.(2) we find they formally look the same, which is actually kind of misleading since the quotient has different meanings in different context. However, thanks to the equivalence equation defined in ring localization, one can show that there indeed exists a bijection between $\mathcal{O}_ {X}(U_ {f})$ and the localization of $\mathcal{O}(X)$ at $f$. 

### Stalks are Localizations

Let $X$ be an affine variety with structure sheaf $\mathcal{O}_ {X}$, and $a\in X$ a point in $X$. Recall that $I(a)$ is a maximal ideal in $\mathcal{O}(X)$, thus a prime ideal. 

**Proposition.** The `stalk` $\mathcal{O}_ {X}(a)$ is the isomorphic to the localization $\mathcal{O}(X)_ {I(a)}$ of the coordinate ring $\mathcal{O}(X)$ at the prime ideal $I(a)$. 

We will omit the proof here. 

- - -

### Local and Global Properties of Morphisms

Recall that, roughly speaking, a morphism for ringed space is a continuous map where the pull-back of the structure sheaf is well-defined. 

Let $(X,\mathcal{O}_ {X})$ and $(Y,\mathcal{O}_ {Y})$ be two ringed spaces. We have the following properties.

**Restriction.** If
$$
f: X\to Y
$$
is a morphism, let $U\subset X$ and $V \subset Y$ be two open subsets and $f(U)\subset V$, then the restriction of $f$ on $U$ is morphism of ringed spaces.

**Gluing.** If $f: X\to Y$ is a map between two topological spaces, $f$ need not be continuous. If there exists an open cover of $X$ denoted $U_ {i}$ and $f\mid_ {U_ {i}}: U_ {i}\to Y$ are all morphisms, then we can glue them all together and $f$ is itself a morphism. 

**Categorical properties.** A composition of morphism is a morphism. An identity is a morphism. Thus ringed space form a category, where the arrows are morphisms. We will focus on the *full subcategory of affine varieties*. 

- - -

Roughly speaking, affine varieties are varieties embedded in affine space with structure sheaves. Let $X=(X,\mathcal{O}_ {X})$ and $Y=(Y,\mathcal{O}_ {Y})$ be two affine varieties, and $Y\subset\mathbb{A}^{n}$. Let $U\in X$ be an open set. 

Since $Y$ is embedded in $n$-dimensional affine space, $Y$ has $n$ coordinates in $\mathbb{A}^{n}$, for example a circle in $\mathbb{R}^{2}$ has two coordinates $(x,y)$. If there exists a morphism from $X$ to $Y$, then $f$ can pull-back there coordinate functions, for coordinates are nothing but regular functions $Y\to k$. This motivates the following proposition.

Given a map 
$$
f: U\to Y,
$$
it is a morphism if and only if there exists $n$ regular functions 
$$
f_ {i} \in \mathcal{O}_ {X}(U)
$$
such that
$$
f=(f_{1},\dots,f_ {n}) : x\mapsto(f_{1}(x),\dots,f_ {n}(x))
$$
where $(f_{1}(x),\dots,f_ {n}(x))$ denotes a point in $Y$ with coordinates given by these $f$s. 

The prove can be found elsewhere.

As a corollary, a morphism to $\mathbb{A}^{1}$ is just a regular function. 

### Principal Open Subsets are Affine Varieties

The title is rather confusing, since by definition varieties are closed sets, and principal open subsets $U_ {f}$ are, as the name suggests, open. How can they be the same thing? The answer is that, to make a principal open set into a closed affine variety, we need to increase the dimension of the embedding affine space by $1$. 

Let $X=(X,\mathcal{O}_ {X}$ be an affine space and $f\in\mathcal{O}(X)$ some function of $X$. The principal open subset 
$$
U_ {f} = X - V(f)
$$
is an affine variety with coordinate algebra $\mathcal{O}(X)_ {f}$.

To see this, let's introduce a new dimension of affine space and let the coordinate be $t$. Define 
$$
Y = \left\{ (x,t)\in X\times \mathbb{A}^{1} \,\middle\vert\, tf(x)=1 \right\} 
$$
which is closed in the higher-dimensional affine space since it is the vanishing set of $t f(x)-1$. This is a well-defined map $U_ {f}\to X\times\mathbb{A}^{1}$ since $f(x)\neq 0$ on $U_ {f}$ by construction.

