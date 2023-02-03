---
layout:     post   				                    # 使用的布局（不需要改）
title:      Basic Commutative Algebra Class 5		# 标题 
subtitle:   Zariski Topology
date:       2023-2-2 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/mathArt1.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - Math
    - Commutative Algebra
    - Notes
---

### Zariski Topology

Rings are purely algebraic structures, it was to my surprise that, in a very direct manner, we can endow it with topological structures, called Zariski topology. This has a feeling of unity of algebra and geometry, with topology represents the geometry side. It makes people wonder why is it possible to define a topology on rings so naturally... The answer I do not know, let me know if you have any ideas.  

First, an overview of the ideal of topological space. Given a set $X$, we want to introduce a geometric structure on $X$ by defining what the it means for a subset to be `closed` and `open`. Namely we classify all the subsets of $X$ into two categories, open and closed. They don't have to me mutual exclusive, a subset can be both open and closed, contrary to people's common sense, such sets are sometimes called clopen but I seldom see living human being ever utter that word. No need to make the terminology more complicated than it already is.

A topology on $X$ is a collection $\mathcal{T}$ of the subsets of $X$ called `closed` subsets, such that the following holds:
1. The empty set $\emptyset$ and whole set $X$ are closed, 
2. `finite` unions of closed sets are closed,
3. `arbitrary` (meaning finite and infinite) intersections of closed sets are closed.

The reason why we require **finite** unions of closed sets to be closed, rather than arbitrary unions, is that infinite unions of closed sets may be open. Take $\mathbb{R}$ for example, Let the topology on $\mathbb{R}$ be the usual topology, for example $(1,2)$ is a open set and $[1,2]$ is closed. However, the infinite union of closed sets
$$
\bigcap_{n\to \infty}\left[ 1+\frac{1}{n},2-\frac{1}{n} \right],\quad n\in \mathbb{N}
$$
is nothing but the open set $(1,2)$.

The set $X$ with topology $\mathcal{T}$ is called a `topological space`. It is a quite weak (or should I say abstract) sense of "space", since there is not necessarily the concept of distance, or metric. If the topology is clear from the contest you just say that $X$ is a topological space, without mentioning $\mathcal{T}$ explicitly. 

A set $U$ is called an open set if its complement, denoted by $X-U$ (or $X \backslash U$ ) is closed.   

This is how you define topology in terms of closed sets. More often the topology is defined by specifying which sets are open. Then the condition also changes from "finite union, arbitrary intersection" for closed sets to "finite intersection, arbitrary union" for open sets.

Once we have defined which sets are open, we can define which maps are `continuous.` A continuous map is a map between two topological spaces such that the pre-image of any closed sets is closed, equivalently (convince yourself of it) the pre-image of any open sets is open. 

Then we can further define `homeomorphism` (note the spelling is different from homomorphism in, for example, group theory). A homeomorphism is a continuous map with continuous inverse. By the way, there is a nice article online discussing the difference and connection between homeomorphism and homomorphism, sadly I am too lazy to put the link here, interested readers can google it. 

Whenever you need examples for these definitions, just think of $\mathbb{R}$ with usual topology. 

- - -

Now let's come back to algebraic sets and try to endow it with a topological structure. There are two ways to define the topology, one geometric and one algebraic. We will start with the geometric one.

**Proposition.** Let $X\subset \mathbb{A}^{n}$ ($\mathbb{A}$ for affine) be an `algebraic set` and $\mathcal{T}$ to be the collection of all `algebraic subsets` of $X$, then $\mathcal{T}$ is a topology of $X$ and $\mathcal{T}$ is the set of closed sets. 

In other words, a subset $U\subseteq X$ is closed if $U$ itself is algebraic, that is if $U$ is the variety of some ideals of $I(X)$, where $I(X)$ is the coordinate ring of $X$, namely the ring of non-zero polynomial functions on $X$.

The empty set $\emptyset$ is algebraic since it is the variety of $I(X)$ itself, the entire set $X$ is also algebraic since it is the variety of the zero element of $I(X)$. The union of algebraic sets are algebraic since 
$$
\bigcup_{i}V(I_{i}) = V\left( \prod_{i} I_{i} \right)
$$
and the intersection of algebraic sets are algebraic since
$$
\bigcap_{i} V(I_{i}) = V\left( \sum_{i}I_{i} \right).
$$

I'll leave the distinction between "arbitrary" and "finite" to readers.

This topology is called the `Zariski topology`.

From now on, when we talk about topology of an algebraic set, we would always assume Zariski topology, unless stated otherwise. 

Note that Zariski Topology is very different from the usual topology of $\mathbb{R}^{n}$ or $\mathbb{C}^{n}$, where open sets are open balls. For example, consider the complex plane $\mathbb{C}$ with usual metric topology where open sets are open balls
$$
\{ z\in \mathbb{C} \mid \left\lVert z \right\rVert  <1 \} 
$$

However, this open ball is **not Zariski open** for if it were, its complement must be closed, namely its complement must be the variety of some ideal of $\mathbb{C}[z]$, which is not true. Hence the open ball is not Zariski open. In this sense, the usual topology on $\mathbb{C}$ is **finer** than Zariski topology, meaning roughly with more open sets.

- - -

### Connectedness and Irreducibility

The definition of connectedness is quite intuitive: if a set can be written as the disjoint union of two proper subsets, then it is said to be disconnected, otherwise it is said to be connected. To be more specific,

**Definition.** Let $X$ be a topological space. If $X=X_{1} \sqcup X_{2}$ , where $\sqcup$ is the disjoint union and both $X_{1}$ and $X_{2}$ are closed (=algebraic) proper subsets of $X$, then $X$ is said to be `disconnected`, otherwise $X$ is said to be `connected`.

For example, if you put two entirely irrelevant varieties together, let there be no intersection or superposition, and consider then as one big variety, then it is clearly less interesting than to study the individual varieties separately. Thus connected varieties are more interesting to us, since otherwise we can separate the variety into connected parts and study them separately.

Another related yet different concept is reducibility. 

**Definition.** Let $X$ be a topological space and $X_{1},X_{2}$ be two `closed`, `proper` subsets, not necessarily disjoint. If $X=X_{1}\cup X_{2}$ then $X$ is said to be `reducible`. Otherwise it is said to be `irreducible`. 

Think about the difference between connectedness and irreducibility. 

Obviously, irreducibility implies connected but the converse is not true. As an example, consider Zariski topology and $V(xy)$. It is connected but reducible.

Zariski topology is a weird topology, with some uncommon properties. To start with, Zariski topology is `coarse`, meaning it has very few open or closed sets. Consider Zariski topology on the real affine line $\mathbb{A}^{1}$, the closed sets are the zero loci of polynomials in one variable. But every polynomial has but finite zeros, thus the closed sets comprises of finite point, it is a finite set. Then the open sets are the whole affine line with finite points removed. Similarly for a complex line $\mathbb{C}$. 

The problem is that, the definition of `neighborhood` of a point depends on the open sets. So, when taking the neighborhood of a point on $\mathbb{C}$, keep in mind that the open sets are the entire complex plane with finite points removed. Thus given two points on $\mathbb{C}$, you can't find two disjoint neighborhoods of these two points. Then, by definition, $\mathbb{C}$ with Zariski topology is not s Hausdorff space. Recall that in a Hausdorff space, two points, no matter how close they are to each other, can be separated by two **disjoint** open sets.

Another consequence of Zariski topology is that, the affine line $\mathbb{A}$ (or $\mathbb{C}$ in that matter) is not reducible, since a line is not the union of finite points.

Yet another consequence of Zariski topology is that, in any irreducible space $X$, every proper open subset of $X$ is `dense`. Recall that a proper subset $Y\subset X$ is dense in $X$ means the close of $Y$ is $X$.

- - -

We have told the geometric side of the story. On the algebraic side, we talk about the ideals. Let's start with the algebraic view on connectedness.

**Proposition.** If $X$ is a disconnected algebraic set with $X=X_{1}\sqcup X_{2}$, where $X_{1,2}$ are `closed proper` subsets, then the coordinate rings on them obey
$$
\mathcal{O}(X) = \mathcal{O}(X_{1}) \times  \mathcal{O}(X_{2}).
$$

Intuitively speaking, if $X$ is make of two separated parts $X_{1}$ and $X_{2}$, then the non-vanishing polynomial functions on $X$ is made up by the product of non-vanishing polynomial functions on $X_{1}$ and $X_{2}$.

The proof uses the Chinese Remainder theorem, which claims that if two ideals $J_{1},J_{2}$ satisfies $J_{1}+J_{2}=R$ and $J_{1}\cap J_{2}=(0)$, then 
$$
R\cong R / J_{1} \times R / J_{2}.
$$
In our case, let 
$$
R=\mathcal{O}(X)
$$
be the coordinate ring of $X$, and
$$
J_{1}= I(X_{1}),\quad J_{2}=I(X_{2}).
$$

Then we have 
$$
I(X_{1})\cap I(X_{2}) = I(X_{1}\cup X_{2}) = I(X),
$$
where the last equal sign is by assumption. An easy way to memorize the first equality is to keep mind that the smaller the ideal, the larger the corresponding variety. 

However, we know that $I(X)$ is zero since that's the only polynomial function that vanishes everywhere on $X$. Thus we have shown that 
$$
I(X_{1})\cap I(X_{2})=(0).
$$

On the other hand, we have 
$$
I(X_{1}\cap X_{2})=\sqrt{ I(X_{1})+I(X_{2}) }= I(\emptyset)
$$
since $X_{1}\cap X_{2}$ is empty. But $I(\emptyset)$ is nothing but the coordinate ring of $X$! namely
$$
\sqrt{ I(X_{1})+I(X_{2}) }=\mathcal{O}(X) = R.
$$
Any ideal whose radical is the entire ring $R$ is itself $R$, thus 
$$
I(X_{1})+I(X_{2})=\mathcal{O}(X).
$$
Then we can apply the Chinese remainder theorem to prove the proposition. 

Next let's turn to the algebraic view of irreducible varieties. 

**Proposition.** A non-empty algebraic set $X$ is irreducible iff $\mathcal{O}(X)$ is an `integral domain`.

First let's prove the "only if", then "if". 

If $\mathcal{O}(X)$ is not an integral domain, then there exists two zero-divisors $f_{1},f_{2}\in \mathcal{O}(X)$ such that non of them are zero but they 
multiply to zero, $f_{1}\times f_{2}=0$. The corresponding varieties $X_{1}:=V(f_{1})$ and $X_{2}:=V(f_{2})$ are proper subsets of $X$, and 
$$
V(f_{1}\times f_{2}) = V(f_{1})\cup V(f_{2}) =X_{1}\cup X_{2},
$$
on the other hand, 
$$
V(f_{1}\times f_{2}) = V(0) = X,
$$
thus 
$$
X = X_{1}\cup X_{2}.
$$

Now we prove that $\mathcal{O}(X)$ being an integral domain implies irreducibility. If $X$ is reducible, it can be written as $X_{1}\cup X_{2}$, where
$$
X_{I}, \quad I = \left\{ 1,2 \right\} 
$$
are the proper, closed subsets of $X$. Then we can choose two non-zero elements $f_{1}\in I(X_{1})$ and  $f_{2}\in I(X_{2})$, it is possible because $X_{I}$ are not equal to $X$. Apparently $f_{1}\times f_{2}$ is zero on $X_{1}\cup X_{2}$, which is $X$. But only $(0)$ can be zero on $X$, thus 
$$
f_{1}\times f_{2}=0
$$
and $f_{1},f_{2}$ are zero divisors, implying that $\mathcal{O}(X)$ is not an integral domain. 

By definition, the coordinate ring $\mathcal{O}(X)$ is $R / I(X)$ where $R$ is the polynomial ring. Recall that $R / I$ is an integral domain if $I$ is prime (similarly if $I$ is maximal then $R / I$ is a field), $\mathcal{O}(X)$ being an integral domain implies that $I(X)$ is a prime ideal, and note that prime ideals are automatically radical. Thus under the bijection between algebraic sets and radical ideals, irreducible algebraic sets (non-zero, of course) correspond to prime ideals in $k[X_{M}]$, where $M$ is an index set. 

- - -

### Noetherian Topological Space

Recall that a ring is called Noetherian if the ideals satisfy the ascending chain condition (ACC). We can interpret it geometrically in the context of Zariski topology. 

**Definition.** A topological space is called `Noetherian` if every descending chain of `closed` proper subsets terminates. Namely, the descending chain 
$$
V(J_{1})\supsetneq V(J_{2})\supsetneq\dots
$$
always terminates. 

This implies that, in terms of the ideals $J$s, the ascending chain
$$
J_{1}\subsetneq J_{2} \dots
$$
terminates, hence the name Noetherian. 

Apparently, any subsets of a Noetherian topological space is also Noetherian. We also mention that algebraic sets (with Zariski topology) is Noetherian, since there exists a smallest closed algebraic set, namely the set of points. 

The good thing about Noetherian topological spaces is that, they can be reduced to irreducible subsets. Let $X$ be a Noetherian topological space, then there exists non-empty irreducible subsets $X_{1},\dots,X_{n}$ such that 
$$
X = X_{1}\cup \dots \cup X_{n},
$$
this decomposition is unique up to permutation. 

- - -

### Zariski Open Sets

We want to understand the open sets of a algebraic variety in Zariski topology in detail. First, we define a fundamental concept.

**Definition.** Given $f\in \mathcal{O}(X)$, the `principla` or `distinguished open subset` $U_{f}$ if given by 
$$
U_{f} := \{ x\in X \mid f(x)\neq 0 \},\text{ or equivalently } U_{f}=X-V(f).
$$
Since $V(f)$ is closed by definition, $U_{f}$ is obvious open. 

The reason why principal open sets are so useful is that if $U\subset X$ is open, then $U$ is finite union of principal open sets,
$$
U = \bigcup_{i}U_{i}
$$
where $U_{i}$ are principal. 

To prove it, notice that if $U$ is open then we have 
$$
U = X - V(J)
$$
for some $J\in\mathcal{O}(X)$. Suppose $J$ is finitely generated by $f_{M}\in\mathcal{O}(X),M=1,2,\dots,m$, then
$$
U = X - V(f_{1},\dots,f_{m})= X- \bigcap_{m}V(f_{m}) = \bigcup_{m}X-V(f_{m})=\bigcup_{m}U_{f_{m}}.
$$

Thus, principal open subsets form a `base` for the Zariski topology on $X$.

- - -

### Regular Functions on Open Sets

The closed sets and opens sets are very different in Zariski topology, much more so than in usual topology. To see that, consider the definition of coordinate ring of a algebraic subset $Z\subset X$,
$$
\mathcal{O}(Z) = \mathcal{O}(X) / I_{X}(Z)
$$
where $I_{X}(Z)$ is the vanishing ideal in $\mathcal{O}(X)$ on $Z$. Such a definition would **not** work for open sets: If $X$ is irreducible and $U\subset X$ is open, then no polynomial function $f\in\mathcal{O}(X)$ vanishes on $U$, since $U$ would be the entire affine space minus finite points. So $I_{X}(U)=(0)$ and $\mathcal{O}(U)=\mathcal{O}(X)$, which creates all kinds of problems.

The solution is not to see open subsets as obstructions but opportunities. We should allow quotients whenever the denominator is non-zero. And we should aim locally. This leads us to the following definition.

**Definition.**   Let $X$ be an algebraic set and $U\subset X$ an open subset. A `regular function` $\phi$ on $U$ is a map
$$
\phi: U\to k
$$
where $k$ is the base field (real, complex, whatever), such that for each point $a\in U$, there exists a subset $U_{a}\subset U$ and $f,g\in\mathcal{O}(X)$ satisfying 
$$
\forall\, x\in U_{a}: f(x)\neq 0 \text{ and } \phi(x) = \frac{g(x)}{f(x)}.
$$
It is nothing but quotient of polynomial functions on some "neighborhood" of $a$. 

Note that the specific $f(x)$ and $g(x)$ would depend on the choice of $a$. This definition is local in nature.

The set of all regular functions on $U$ is denoted $\mathcal{O}(U)$. It is a $k$-algebra under pointwise operations. 

On principal open sets, the denominator can be fixed globally. Given any $f\in\mathcal{O}(X)$, the corresponding principal open set is $U_{f}=X-V(f)$, $f$ is non-zero on $U_{f}$ by construction, thus we can define 
$$
\mathcal{O}(U_{f}) = \left\{  \frac{g(x)}{f^{n}(x)} \mid g(x)\in \mathcal{O}(X) \text{ and } n\in \mathbb{N}  \right\}. 
$$
