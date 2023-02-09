---
layout:     post   				                    # 使用的布局（不需要改）
title:      Basic Algebraic Geometry Class 11	# 标题 
subtitle:   Projective Algebra Sets
date:       2023-2-9 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/mathArt5.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - Math
    - Commutative Algebra
    - Notes
---

### Projective algebraic sets

In this note we will see some varieties that are not affine. 

The projective varieties are a class of important examples of non-affine varieties. The projective line $\mathbb{P}^{1}$ gave us new possibilities. Our general ideal is to replace affine varieties by projective varieties, and study algebraic sets in it.

Rather than gluing two varieties together as we did in the previous classes, here we introduce a new, more elegant definition of projective spaces in general. 

The general idea is to define projective spaces as the abstract space as geometrical objects. For example, to give you a taste of it, the one dimensional projective space can be defined as the space of all the lines crossing origin in a two dimensional plane. Each point in the projective line $\mathbb{P}^{1}$ would represent a line in a plane passing origin. Higher dimensional spaces can be defined similarly.

**Definition.** For $n\in \mathbb{N}$, projective $n$-space $\mathbb{P}^{n}=\mathbb{P}_ {k}^{n}=k\mathbb{P}^{n}$ ($k$ is a algebraically closed field) is the set of all $1$-dimensional vector subspaces of the vector space $k^{n+1}$. 

Take $n=1$ for example, the projective space $\mathbb{P}^{1}$ is the set of all the lines crossing the origin. Every point beside the origin defines one such line uniquely. Given the horizontal line $y=1$ in the $x-y$ plane, each line crossing the origin intersects $y=1$, except for one line: the $x$-axis, namely $y=0$ horizontal line, which you can say intersects with $y=1$ at infinity. Including that line, we kind of compactified $y=1$ by including a point "at the infinity", similar to how we constructed the Riemann sphere.

Another equivalent definition is to regard $\mathbb{P}^{n}$ as the set 
$$
\mathbb{P}^{n}:= (k^{n+1} - \left\{ 0 \right\} ) / \sim ,
$$
where $x\sim y$ if $x=\lambda y$ for some $\lambda \in k^{\ast}$, where $k^{\ast}=k-0$. Thus a point in $\mathbb{P}^{n}$ is given by the equivalence class
$$
[x_{0}:x_{1}:\dots:x_ {n}].
$$
We also have the canonical projection from $k^{n+1}\to\mathbb{P}^{n}$ by 
$$
(x_{0},\dots,x_{n})\mapsto[x_{0}:\dots: x_{n}].
$$
This is called the affine coordinates. The indices starting from $0$ is the conventional notation. The equivalence relation reduces the dimension by one.

- - -

Affine space `embeds` into projective space as the set $U_{0}$ of all points with $x_{0}\neq 0$. Note that $U_ {0}$ is not the origin, but the hyperplane where the first coordinate is zero. The unpleasant thing is that, this embedding reduces the dimension by $1$. Another way to embed an affine space of dimension $n$ to projective space of the same dimension is 
$$
(x_{1},\dots,x_{n})\mapsto [1: x_{1}:\dots: x_{n}].
$$
The open subset $U_ {0}$ can be identified as $\mathbb{A}^{n}$, namely the $x_{0}=1$ plane in $\mathbb{A}^{n+1}$.

Note that we used the word `embed`, not isomorphic, thus we allow the embedding map not being surjective. There might be points in $\mathbb{P}^{n}$ without a pre-image by the embedding map. 

The set 
$$
H_ {\infty}:= \mathbb{P}^{n} - U_ {0}
$$
is given by points of form $[0: x_{1} : \dots: x_{n}]$, which is isomorphic to $[x_{1} : \dots : x_{n}]$, which is a $n-1$ dimensional projective space. Thus $H_ {\infty}$ is a copy of $\mathbb{P}^{n-1}$, called the `hyperplane at infinity`.

### Algebraic sets

Having said what projective spaces are, we can go on and define algebraic sets on it. Again, a algebraic set is a set given by the zero loci of a polynomial function (or more precisely an ideal given by the polynomial function). But what does it mean in a projective space?

For example, consider the example
$$
f(T_{1},T_{2}) = T_{1}^{2}-T_{2} \subset k[T_{1},T_{2}].
$$
The zero loci contains the point,
$$
f(1,1)=0.
$$
Obviously $(-1,-1)$ is not in $V(f)$. This is fine in a two dimensional *affine* space since $(1,1)$ are $(-1,-1)$ are two distinct points. However in $\mathbb{P}^{2}$ it would raise problems since they are the same point $[1,1]$! How can a function both be zero and non zero on the same point? It can not. Thus we need to constrain the type of polynomials, if we want them to define consistent zero loci on a projective space.

The solution is to look only at `homogeneous polynomials`. Recall that a polynomial 
$$
f\in  k[T_{0},\dots,T_ {n}]
$$
is called `homogeneous of degree` $d$ if 
$$
f(\lambda t_{0},\dots,\lambda t_ {n}) = \lambda^{d} f(t_{0},\dots,t_ {n})
$$
for each $\lambda \in k^{\ast}$. 

Equivalently, all **monomials** of $f$ are of degree $d$. 

In our previous example, $f=T_ {1}^{2}-T_{2}$ is not homogeneous since $T_{2}$ has degree one while $T_{1}^{2}$ has degree two. We can make it homogeneous by, for example, replace the second monomial by $T_{2}T_{1}$.

As you can probably see, homogeneous polynomials are perfect for projective spaces, since if 
$$
(x_{0},x_{1},\dots,x_{n}) \in \mathbb{A}^{n+1}
$$
is a zero locus of some homogeneous polynomial, then so is the scaled point
$$
(\lambda x_{0},\dots,\lambda x_{n}),\quad \lambda \in k^{\ast }.
$$
This motivates the following definition.

**Definition.** For any set 
$$
F \subset k[T_{0},\dots,T_ {n}]
$$
of homogeneous polynomials, the `projective zero locus` 
$$
V(F) = V_ {p}(F)
$$
is the set of all 
$$
x \in  \mathbb{P}^{n}
$$
where 
$$
f(x)=0 \text{ for all } f \in  F.
$$

In short, **homogeneous polynomials are such that has well defined zero loci on projective spaces.**

The set $V(F)$ is called a `projective algebraic set`.

We will use the subscripts $p$ for projective and $a$ for affine algebraic set whenever confusion needs to be avoided.

### Graded rings

Now let us look at algebraic side of the algebraic sets. In the affine setting, we used ideals in the ring of polynomials to "algebraicise" these sets. When it comes to **homogeneous** polynomials we need to be extra careful. That's why we need the concept `graded ring`.

So-called graded ring is just a ring which is a direct summation of subrings, satisfying certain conditions. To be precise, the ring 
$$
R = k[T_0, \dots, T_ {n}]
$$
is a `graded ring` 
$$
(R,+) = \bigoplus_ {d\in \mathbb{N}} R_ {d} \text{ and } R_ {d} \times R_ {e}\subset R_ {d+e}
$$
where the `homogenous elements of degree` $d$ are homogeneous polynomials of degree $d$. 

Note that the "direct sum" means that every element can be written as sum of **finitely many** homogenous elements. 

The graded ring is in fact more than graded ring, it is also a graded $k$-algebra since 
$$
k R_ {d} \subset R_ {d}.
$$

The `homogeneous decomposition` is the finite sum of homogeneous elements,
$$
f = \sum f_ {d}, \quad f_ {d} \in  R_ {d}.
$$

- - -

Now knowing that the ring is graded, let's look at special kinds of ideals that respects this gradation. 

**Proposition.** For an ideal $J$ in a graded ring $R$, the following are equivalent.
- $J$ is generated by homogenous elements of $R$.
- If $f\in J$ has (unique) homogeneous decomposition $f = \sum_ {d} f_ {d}$, then $f_ {d}\in J$ for all $d$.

An ideal in a graded ring is called a `graded ideal` or `homogeneous ideal` if it satisfy these conditions. 

It is an exercise to check that the intersection, product and sum of graded ideals are also graded. For example, in $k[T_{1},T_{2}]$, the ideal $(T_{1},T_{2}^{2})$ is graded, but the ideal $(T_{1}-T_{2}^{2})$ is not graded. 

- - -

Now we can talk about the zero loci of graded ideals. 

**Definition.** For a graded ideal $J$ in $R=k[T_{0},\dots,T_ {n}]$, the `projective zero loci` $V(J)$ is the set of all $x \in \mathbb{P}^{n}$ such that $f(x)=0$ for all homogeneous $f\in J$.

In the other direction, we want to associate some idea to a given set. 

**Definition.** For any subset $X\subset\mathbb{P}^{n}$, the vanishing ideal $I(X)$ of $X$ is the ideal generated by all homogeneous $f\in k[T_{0},\dots,T_ {n}]$ such that $f(X)=0$. 

The variety of zero ideal $V(0)$ is the whole projective space. Going to the other extreme, when we want the variety to be $\emptyset$, in affine space we need $J$ as in $V(J)$ to be the whole ring $R$, but for projective varieties we just need the radical of $J$ to contain the ideal $(T_{0},\dots,T_ {n})$, namely 
$$
(T_{0},\dots,T_ {n}) \subset \sqrt{ I }
$$
then it is enough for $V(J)=\emptyset$. It is because the zero locus for $(T_{0},\dots,T_ {n})$ is the origin of the affine space $\mathbb{A}^{n+1}$, which is **excluded** in the projective space.

Singleton sets are also algebraic.

### Zariski topology

As in the affine case, we want to construct a topology. We list without proof the following.

Let $J,J'\subset k[T_{0},\dots,T_ {n}]$ be graded ideals.
1. If $J\subset J'$ then $V(J')\subset V(J)$, note the reversed direction of inclusion.
2. $V(J J')=V(J \cap J') = V(J) \cup V(J')$.
3. $V(J+J')=V(J) \cap V(J')$.

Moreover, relation (2) can be generalized to any finite collection, and (3) to any collection, of graded ideals. The justifies the Zariski on homogeneous spaces.

**The Zariski topology.** The projective algebraic sets are the closed sets of a topology on $\mathbb{P}^{n}$, the Zariski topology.

### Relating $\mathbb{P}^{n}$ to $\mathbb{A}^{n+1}$

First some jargons. 

**Definition.** A `cone` is an non-zero, affine algebraic set $X\subset\mathbb{A}^{n+1}$ which is closed under scalar multiplication (of coordinates). 

If $x \in X$ is a point in a cone, then $\lambda x$ where $\lambda \in k$ is also in a cone. The non-emptiness of a cone requires that the origin is always contained in a cone. It is nothing but a union of lines passing the origin in $\mathbb{A}^{n+1}$.

Now we want to attach cones to any projective space $\mathbb{P}^{n}$. 

**Definition.** Let 
$$
\pi: \mathbb{A}^{n+1}-\left\{ 0 \right\} \to \mathbb{P}^{n}
$$
be the usual projection. 
- The `affine cone` $C(X)$ over a projective, algebraic set $X\subset\mathbb{P}^{n}$ is defined to be 
$$
C(X) := \left\{ 0 \right\} \cup \pi^{-1}(X) \subset \mathbb{A}^{n+1}.
$$
- Let $Y\subset \mathbb{A}^{n+1}$ be a cone in $\mathbb{A}^{n+1}$. The `projectivization` of $Y$ is the projective, algebraic set
$$
P(Y):= \pi(Y-\left\{ 0 \right\} ) \subset\mathbb{P}^{n}.
$$

### Projective Nullstellensatz

**Theorem.** 
- For any algebraic set $X\subset\mathbb{P}^{n}$, we have $V(I(X))=X$. 
- For any homogeneous ideal $J\subset k[T_{0},\dots,T_ {n}]$ with $I_{0}\neq \sqrt{ J }$ where $I_{0}=(T_{0},\dots,T_ {n})$, we have $I(V(J))=\sqrt{ J }$.

### Toward projective varieties

Recall that to define a variety, it's not enough to have the Zariski topology, we also need to define the coordinate rings, which is the algebraic side of the varieties. To start with, we need to define the homogeneous coordinate rings. 

Let $X\subset\mathbb{P}^{n}$ be a projective algebraic set. The `homogenous coordinate ring` of $X$ is is the ring 
$$
\boxed{
S(X) := k[T_{0},\dots,T_ {n}] / I(X)
}
$$
where both $k[T_{0},\dots,T_ {n}]$ and the ideal are graded. The quotient ring $S(X)$ itself is also graded, according to the following lemma.

If $J$ is a graded ideal in a graded ring $R$, then $R / J$ is graded as a ring with homogeneous components in
$$
R_ {d} / (R_ {d} \cap J).
$$

We can also define the relative notion on $X$. We can define the zero loci $V_ {X}(J)$ in $X$ of a graded ideal $J\subset S(X)$, and the vanishing ideal $I_ {X}(Z)$ of some closed subset $Z\subset X$. As in the affine case, a relative nullstellensatz holds.

### Relating $\mathbb{A}^{n}$ to $\mathbb{P}^{n}$

Our goal here is to understand the embedding $\mathbb{A}^{n}\to\mathbb{P}^{n}$ topologically. 

The strategy is as follows. Given a graded ideal $J\subset K[T_{0},\dots,T_ {n}]$ in the context of $\mathbb{A}^{n+1}$, we want to find an ideal $J^{i}$ in $k[T_{1},\dots,T_ {n}]$ in the context of $\mathbb{A}^{n}$ such that 
$$
V_ {p}(J) \cap\mathbb{A}^{n} = V_ {a}(J^{i}).
$$
The $\mathbb{A}^{n}$ could be the sub-affine space given by $T_ {0}$ plane in $\mathbb{A}^{n+1}$.

Conversely, to each ideal $I\subset k[T_1,\dots,T_ {n}]$, we want to find a graded ideal $I^{h}\subset k[T_{0},\dots,T_ {n}]$ such that 
$$
V_ {a}(I) = V_ {p}(I^{h})\cap\mathbb{A}^{n}.
$$

Once it is done, it follows that $\mathbb{A}^{n}\to\mathbb{P}^{n}$, $(x_{1},\dots,x_{n})\mapsto [1:x_{1}:\dots : x_{n}]$ is a topological embedding.

**Dehomogenization.** Given a homogeneous polynomial in $n+1$ variables, $f\in k[T_{0},\dots,T_ {n}]$, its `dehomogenization` $f^{i}$ is defined simply by setting $T_{0}=1$, which is now a polynomial in $n$ variables.
$$
f^{i}(T_{1},\dots,T_ {n}) = f(T_{0}=0,T_{1},\dots,T_ {n}).
$$
The superscript $i$ is for inhomogeneous.

For example, given 
$$
f=T_{1}^{2}+T_{1}T_{2}
$$
which is homogenous, its dehomogenization would be 
$$
f^{i} = 1+T_{2}.
$$

The map $f\mapsto f^{i}$ is homomorphic. If $J\subset k[T_{0},\dots,T_ {n}]$ is a graded ideal, then its dehomogenization is an ideal 
$$
J^{i} = \left\{ f^{i} \,\middle\vert\, f \in  J \right\} 
$$
in $k[T_1,\dots,T_ {n}]$. One can check that the condition
$$
V_ {p}(J) \cap\mathbb{A}^{n} = V_ {a}(J^{i}).
$$
is also satisfied. 

In the other direction we have `homogenization`. For a nonzero polynomial $f\subset k[T_{1},\dots,T_ {n}]$ of degree $d$, its homogenization is 
$$
f^{h}(T_{0},T_{1},\dots,T_ {n}) = T_{0}^{d} f(T_{1} / T_{0}, \dots,T_ {n} / T_{0}).
$$
For example, given an inhomogeneous polynomial in one variable
$$
f = 1+T_{1}^{2}
$$
which has degree $d=2$, the homogenization of it would be 
$$
f^{h} = T_{0}^{2} (1+ T_{1}^{2} / T_{0}^{2}) = T_{0}^{2}+T_{1}^{2}.
$$
The homogenization of an ideal is defined similarly. 

### Projective closure

By setting the first coordinate to be $1$ we can switch from $\mathbb{P}^{n}$ to $\mathbb{A}^{n}$, that's great. But what is the meaning of $V_ {p}(J^{h})$ in terms of $V_ {a}(J)$?

**Proposition.** Let $X$ be a affine algebraic set in $\mathbb{A}^{n}$ given by ideal $J\subset k[T_{1},\dots,T_ {n}]$.  Then the closure $\overline{X}$ of $X$ in $\mathbb{P}^{n}$ is $V_ {p}(J^{h})$. 

The projective algebraic set $\overline{X}$ is called the `projective closure` of $X$, obtained by adding necessary point in the projective space, namely the point at infinity, to make $X$ into a projective algebraic set. 

