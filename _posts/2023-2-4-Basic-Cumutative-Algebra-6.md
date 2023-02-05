---
layout:     post   				                    # 使用的布局（不需要改）
title:      Basic Commutative Algebra Class 6		# 标题 
subtitle:   Affine Varieties
date:       2023-2-4 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/mathArt2.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - Math
    - Commutative Algebra
    - Notes
---

The goal here is to obtain an `intrinsic` description of **algebra and geometry** of `algebraic sets`, or varieties, or zero loci of polynomials. 

Given a variety $X\subset \mathbb{A}^{n}$ with $k$ being the base (closed) field, we can introduce certain geometric structure on $X$, namely the Zariski topology. Then $X$ is made into a Noetherian topological space. This is the geometric side of the story. On each open subset of $X$ we can define a ring (which is also an $k$-algebra), namely the ring of regular functions, which are rational functions of polynomial functions ${f(x)} / {g(x)}$ where $f(x),g(x)$ are elements of $\mathcal{O}(X)$. This is the algebraic side of the story. 

To summarize, our data is a pair
$$
(X,\mathcal{O}_ {X})
$$
Note that it is $O_ {X}$ not $\mathcal{O}(X)$. $O_ {X}$ is a "gadget" that assigns a ring $O_ {X}(U)$ to each open subset $U\subset X$ in a coherent way. 

Here we have slightly an abuse of notation. $\mathcal{O}(\text{closed sets})$ are coordinate rings, $\mathcal{O}(\text{open sets})$ are the rings of regular functions. Different things depending on where the argument is closed or open. Well I didn't invent the notation.

What we will do next is to extract the important properties of $\mathcal{O}_X$ into a general definition, which we can work with to define affine varieties. 

Let's look at some properties of $\mathcal{O}_ {X}$.  

### Properties of Regular Function Rings

The first thing to notice is that $\mathcal{O} _ {X}$ is not itself a ring, but a "gadget" that, when fed by an open set $U$, spits out a ring $O_ {X}(U)$, or $\mathcal{O}(U)$ for short.

Let $X\subset\mathbb{A}^{n}_ {k}$ be an algebraic set, a subset of n-dimensional affine space of field $k$. Let $U\subsetneq X$ be an `open` subset of $X$. We consider the assignment  
$$
\begin{align}
U &\mapsto \mathcal{O} _ X(U)=: \mathcal{O}(U), \\
 \mathcal{O}(U)&=\left\{  \phi: U\to k \,\middle\vert \,  \phi =\frac{f}{g},f\in \mathcal{O}(X),g\in \mathcal{O}(X) \text{ and } g\neq 0\text{ on }U\right\}
\end{align}
$$
where $=:$ means the right hand side is defined by the left hand side. $\mathcal{O}(U)$ is also a $k$-algebra. In the following we list some properties of the ring of regular functions on open sets.

- Any inclusion $U\subset V$ of open sets in $X$ gives a `restriction` homomorphism 
$$
\rho_{U,V}: \mathcal{O}(V) \to \mathcal{O}(U), \quad \phi\mapsto \phi \mid_{U}.
$$
The restriction of regular functions on $U$ to its subset $V$ is obvious a ring homomorphism.

- The ring of regular functions on empty set, $\mathcal{O}(\emptyset)$, is trivial. 

- If you look at the restriction of regular functions on $U$ to $U$ itself, then you are not changing anything, thus for any $U$, 
$$
\rho_{U,U} = \text{Id}_{\mathcal{O}(U)}
$$

- Restriction respects composition. The restriction of $W$ to $V$ then to $U$ is the restriction of $W$ to $U$. If $U\subset V\subset W$, then  $\rho_{U,V}\circ \rho_{V,W}=\rho_{U,W}$ .

The above properties are kind of "out there in the open", the next one is less so.

- Functions that are defined locally on an open cover, and agree on intersection, have a unique lift.

Let $U =U_{1}\cup U_{2}$ be the union of two open sets, $V:=U_{1}\cap U_{2}\neq \emptyset$. Let $\phi_{1}$ be a regular function on $U_{1}$ and $\phi_{2}$ on $U_{2}$. If $\phi_{1}$ and $\phi_{2}$ agree on the intersection, that is, the restriction of $\phi_{1}$ on $V$ is equal to the restriction of $\phi_{2}$ on $V$, then there exists a unique regular function defined on the whole of $U$, call it $\phi$, such that $\phi \mid_{U_{1}}=\phi_{1}$ and $\phi \mid_ {U_{2}}=\phi_{2}$.  

Now let's generalize these properties to a definition.

### Presheaves and sheaves

Let $X$ be an arbitrary topological space. 

**Definition.** A `presheaf` $\mathcal{F}$ of rings on $X$ consists of the following data:
- For each open set $U\subset X$, is assigned a ring $\mathcal{F}(U)$. Think of the ring of regular functions for example, but $\mathcal{F}(U)$ need be nothing like it, it could be any ring ;
- For each inclusion $U\subset V$ of open sets in $X$, there is a `ring homomorphism` 
$$
\rho_{U,V}: \mathcal{F}(V)\to \mathcal{F}(U),
$$
subject to the following conditions:
- $\mathcal{F}(\emptyset)$ is the trivial ring,
- For any open subset $U$, 
$$\rho_{U,U}=\text{Id}_{\mathcal{F}(U)},$$
- If $U\subset V\subset W$, 
$$
\rho_{U,V}\circ \rho_{V,W}=\rho_{U,W}.
$$
Elements of $\mathcal{F}(U)$ are called `sections` of $\mathcal{F}$ over $U$. Notice the similar usage of terminology from fiber bundle.

The homomorphism $\rho_{U,V}$ is called the `restriction map` from $V$ to $U$, and denoted $\phi\mapsto \phi \mid_{U}$.

The name `sheaf` is rather pictorial. A sheaf in farming is a bundle of grain stalks tied up and laid on the ground, you could say that it is an assignment of bundle of stalks to areas of lands. Here in mathematics a presheaf is an assignment of ring structure to open subsets.

We want a sheave to represent the nice properties we have for ring of regular functions, thus we need the above given conditions for restriction maps. 

Notice that in the definition of presheaf, everything is local. Given a open set $U$, a presheaf only tells you that you can go further into $U$ (restriction), it does not say anything globally. For example ,it does not say if you are given an open cover of some whole space $X$, how can you glue these open charts together to have something defined on the whole atlas. That is why it is called a **pre**sheaf.

**Definition.** A `presheaf` $\mathcal{F}$ is upgraded to a `sheaf` is the following `gluing properties` holds for any open set $U\subset X$:

If 
$$
\{ U_{i} \mid ,i\in I \}
$$
is an open cover of $U$, and if $\phi_{i}$ are sections satisfying 
$$
\phi_{i} \mid_{U_{i}\cap U_{j}} = \phi_{j} \mid_{U_{i}\cap U_{j}}
$$
**for all** $i,j\in I$, then there exists a `unique` $\phi \in\mathcal{F}(U)$ such that 
$$
\phi \mid_{U_{i}} = \phi_{i}, \text{ or equivalently } \phi_{i} = \rho_{U_{i},U}\phi.
$$

It is interesting to compare this compatibility condition with that of fiber bundles, where we use transition functions to glue different bundles. 

Think: what if two open subsets are disjoint, namely $U_{i}\cap U_{j}=\emptyset$? Given two sections separately, $\phi_{i}$ and $\phi_{j}$, what are the restrictions of them on the empty set? Should there be a bigger section $\phi$ defined on $U_{i} \cup U_{j}$ such that the restriction of $\phi$ on $U_{i}$ is $\phi_{i}$ (similarly for $U_{j}$)? I'll leave this small problem to interested readers.( When in doubts, mathoverflow!) For less interested readers, when the overlap is empty, then the overlap condition is vacuous and automatically true.

Some examples are in order. The most familiar example of a sheaf would be

- The sheaf $\mathcal{O}_ {X}$ of rings (regular functions) on an algebraic space $X$, to refresh your memory, 
$$
\mathcal{O}_ {X}(U) = \{ \text{regular functions on }U  \} 
$$
and the restriction is given by the usual restriction of functions.

- The sheaf of real-valued continuous function on a topological space $X$, denoted by $\mathcal{C}(X)$ sometimes. $\mathcal{C}(U)$ where $U$ is some open subset of $\mathbb{R}^{n}$ would be the ring of continuous functions. 

The next example is more interesting. 

- The `presheaf` of constant functions. Consider the (real-valued) real functions on a topological space $X$. Let $U=U_{1}\sqcup U_{2}$, namely the union of two disjoint (non-empty) open sets. choose two sections $\phi_{1}=0$ everywhere on $U_{1}$ and $\phi_{2}=1$ everywhere on $U_{2}$, then the overlap condition is satisfied trivially but the gluing condition is not, since you can not find a constant function on the whole of $U$ whose restrictions are blah and blah. This is an example of a presheaf which is not a sheaf. One way out of this problem is to loosen up the continuous condition a little, instead of globally constant functions we consider the locally constant functions, then we may make it into a sheaf, this process is called `sheafification`.

Roughly speaking, whenever you are dealing with a ring of functions on open sets, you can expect them to be presheaves. But for them to be sheaves, you want them to satisfy `local` conditions. The constant functions, for example, from last example, are not local, since you can't decide if a function is constant or not locally, and that's a hint that it is not a sheave. On the other hand, when we defined regular functions, we didn't say that a regular function must be given by the same quotient expression everywhere (globally), but rather on some (principal) open set (locally). 

### Ringed Spaces

Topological spaces with a sheave structure has its own name.

**Definition.** A `ringed space` is a topological space $X$ together with a sheaf $\mathcal{O}_ {X}$ of rings on $X$, called the `structure sheaf`.

For example, let $U\subset X$ be an open subset of $X$, if $X$ is a ringed space then there exists a ring $\mathcal{O}_ {X}(U)$, also the overlapping condition, restriction condition and gluing condition are all satisfied.

The ringed space $(X,\mathcal{O}_ {X})$ is referred to as $X$ if the structure sheaf is clear from context. 

For example, an algebraic set is a ringed space, the structure sheaf is by default taken to be the ring of regular functions. 

It is kink of obvious that if $X$ is a ringed space, then an open subset $U\subset X$ is also a ringed space, whose structure sheaf is that of $X$ restricted to $U$. 

In general, given a presheaf $\mathcal{F}$ on $X$ and an open subset $U\subset X$, The restriction of $\mathcal{F}$ to $U$ is given by 
$$
\mathcal{F} \mid _{U}(V) = \mathcal{F}(V)
$$
for all open $V\subset U\subset X$. The restriction of a presheaf is a presheaf and the restriction of a sheaf is a sheaf.

- - -

### Sheaves of Functions

Our goal is to define affine varieties as ringed spaces **isomorphic to the ringed spaces of algebraic sets**. To have a reasonable definition of isomorphism, we will restrict the notion of sheaves.

From now on, the sheaf $\mathcal{F}$ on a topological space $X$ is assumed to be a sheaf of $k$-valued functions. For all open subsets $U\subset X$, $\mathcal{F}(U)$ is supposed to be a sub ring of the ring of all $k$-valued functions $U\to k$, with pointwise addition and multiplication.

### Morphisms of Ringed Spaces

Let $(X,\mathcal{O} _ {X})$ and $(Y,\mathcal{O} _ {Y})$ be two ringed spaces, where $O_ {X}$ is the sheaf of regular functions on $X$, etc. Let $f: X\to Y$ be a **continuous** map. Let $U\subset Y$ be an open subset of $Y$, and $\phi: U\to k$ a function defined on $U$. Then we can use $f$ to pull back $\phi$, the pull-back $f^{\ast}\phi$ is the function 
$$
\phi\circ f: f^{-1} (U)\to k.
$$

Recall that $\phi$ is an element of a ring, namely the ring of regular functions defined on $U$, $\mathcal{O}_{Y}(U)$. Thus the pull-back  defines a ring homomorphism
$$
\boxed{f^{\ast }: \phi\mapsto \psi}, \quad \phi: U\to k,\quad\phi: f^{-1}(U)\to k.
$$

If we want to define the morphism between ringed spaces, the morphism map must respect both the topology of the spaces, and the structure ring on those spaces. To be specific,

**Definition.** A `morphism of ringed spaces` is a continuous map 
$$
f: X\to Y
$$
such that for each open $U\subset Y$, the pull-back of any $\phi \in\mathcal{O} _ {Y}(U)$ belongs to $\mathcal{O} _ {X}(f^{-1}U)$. This is possible since $f$ is continuous, meaning that $f^{-1}(U)$ is an open set on $X$, hence there exists a ring of functions $\mathcal{O}_ {X}(f^{-1}(U))$. This defines a ring homomorphism 
$$
f^{\ast }: \mathcal{O}_{Y}(U) \to \mathcal{O}_ {X}(U'), \quad U':=f^{-1}(U).
$$

Note the inverse direction between $f$ and $f^{\ast}$, $f$ points from $X$ to $Y$ and $f^{\ast}$ points from $\mathcal{O}_{Y}$ to $\mathcal{O}_ {X}$. In terms of category theory, the morphism is a contravariant functor.

Now we have the definition of morphism, we can go on and define isomorphism. A morphism $f$ of ringed spaces is an `isomorphism` if it is bijective and there exists the inverse $f^{-1}$, which is another morphism of ringed spaces. 

### Affine Varieties

Finally we can define what affine varieties are, in an intrinsic manner, without mentioning the embbedding space or anything like that.

**Definition.** An `affine variety` is a `ringed space` that is isomorphic to $(X,\mathcal{O}_ {X})$ of an algebraic space $X$, with the sheaf of functions $\mathcal{O} _ {X}$.