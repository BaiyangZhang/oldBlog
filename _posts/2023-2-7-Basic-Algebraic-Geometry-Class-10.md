---
layout:     post   				                    # 使用的布局（不需要改）
title:      Basic Algebraic Geometry Class 10		# 标题 
subtitle:   Algebraic Prevarieties
date:       2023-2-7 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/mathArt6.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - Math
    - Commutative Algebra
    - Notes
---

### Algebraic Varieties

Let's take a look back at what we have talked about so far. Algebraic geometry is the study of various things defined by polynomial functions. To start with, we introduced algebraic varieties as a subspace of affine spaces. But this definition is external, since in order to talk about the variety we first need to know what it is imbedded in. We would like to study varieties intrinsically, without mentioning the embedding space, by studying the functions that could be defined on it, namely the coordinate rings.  

But the problem of affine varieties is that they don't capture the whole picture. For example, for complex numbers, one can show that bounded sets are not affine variety, so how do you study Riemann sphere? So we want to come up with an idea that generalized affine varieties, and that is exactly what `algebraic varieties` are. They are the main actors in algebraic geometry.

A topological/differential manifold is a reasonable topological space cover by open balls, or things similar to open balls, similar in the sense of homeomorphism. Manifolds are also equipped with their structure sheaves.

Something similar goes with varieties. Recall that open subsets of affine varieties are unions of principal open sets, which are themselves affine varieties (in a higher dimensional space). Also affine varieties comes with structure sheaves, since they are ringed spaces.

Thus, one would guess that algebraic varieties should be nice ringed spaces covered by open sets, which are isomorphic to affine varieties.

**Definition.** An (algebraic) `prevariety` is a ringed space $X$ which can be covered by finitely many affine varieties, 
$$
X = U_{1}\cup U_{2}\cup\dots \cup U_ {n}.
$$

Note that the **cover by affine open subsets** is not part of the definition. 

For example, the open subset $\mathbb{A}^{2}-0$ where $0$ is the origin, is a prevariety that is not affine.

In general, any open subsets of an affine variety is a prevariety.

More generally, affine varieties and other prevarieties can be glued (patched) together to form new prevarieties.

### Gluing 

Given finitely many prevarieties 
$$
\left\{ X_ {i} \,\middle\vert\, i\in I, I \text{ an index set} \right\} 
$$
with open subsets
$$
U_ {i,j}\subset X_ {i},\quad U_ {j,i}\in X_ {j}
$$

and `isomorphism` 
$$
f_ {i,j}: U_ {i,i}\to U_ {i,j} \;\forall\; \, i,j\in I.
$$
In other words, we can glue different prevarieties together along $U_ {i,j}$. The gluing isomorphism should satisfy
$$
f_ {i,j}^{-1}=f_ {j,i},\quad f_ {k,j} \;\circ\; f_ {j,i}=f_ {k,i},
$$
where the last condition means the compatibility of gluing when more than two prevarieties are to be glued together at some point.

For any ringed spaces, there must be a topological space and a structure sheaf, the same is true for the glued bigger prevarieties, let's get started to define them.

Consider the set glued together by different prevarieties, let
$$
X = \bigsqcup_ {i} X_ {i} / \sim , \sim \text{ the equivalence equation defined by } f_ {i,j}.
$$
This also gives us the natural map from the original prevarieties to the glued together prevariety,
$$
\iota_ {i}: X_ {i} \to X, \quad x\mapsto [x]
$$
where $[x]$ is the equivalence class of an element in $X_ {i}$. 

Then we topologize $X$ by indulging it the quotient topology, namely we declare a set $U\subset X$ open if $\iota_ {i}^{-1}(U)$ is open in $X_ {i}$ for all $i$.

Finally we want to `ring` $X$ by introducing a structure sheaf $\mathcal{O}_ {X}$ on $X$. To do it,  given some open set $U\subset X$, we need to specify what the regular functions are on $U$. To start with, U must be make of a bunch of $X_ {i}$ glued together, and we already know what regular functions are on $X_ {i}$s since they are well-defined prevarieties with structure sheaf. We also know how to turn a function on $X$ to a function on $X_ {i}$: by pull-back $\iota^{\ast}$. Thus, we can define a function of $U$ to be regular, if the pull back of the function to $X_ {i}$ that makes up $U$ are regular on every and each $X_ {i}$. Hence the following definition:
$$
\mathcal{O}_ {X}(U) := \left\{ \phi:: U\to k \,\middle\vert\, \;\forall\; i: \iota_ {i}^{\ast }\phi \in \mathcal{O}_ {X_ {i}}(\iota^{-1}(U)) \right\}.
$$
The definition looks pretty messy but the key idea is quite direct.

$X$ is then the prevariety obtained by gluing $X_ {i}$s along $f_ {i,j}$.

Let's look at an example, a generalized version of Riemann sphere. Let $X_ {1,2}$ be two affine lines $\mathbb{A}^{1}$ and $U_ {1,2}$ be two open subsets defined by $\mathbb{A}^{1} - 0$ on $X_ {1,2}$ respectively, namely $X_ {1,2}$ themselves but with the origin removed. We can glue them together along the gluing function
$$
f_ {1,2}: x\mapsto \frac{1}{x}.
$$
It is hard to see the final result without drawing the picture, but I am too lazy to do it here, interested readers should try by themselves. Convince yourself that the resulting prevariety is a circle. The ideal is similar to adding a point at infinity to an affine line, and compactify it into a circle. 

The prevariety we got has a name, called the `projective line` $\mathbb{P}^{1}$.

### Morphisms

As morphisms of prevarieties one takes all of them to be the morphisms of ringed spaces. In other words, prevarieties form a `full subcategory` of the category of ringed spaces. Recall that a subcategory is said to be full if the arrows (morphisms) are fully passed on to the objects in the subcategory.

So let's review the gluing properties of morphisms for ringed spaces. Given two ringed spaces $X$ and $Y$ and a continuous map $f: X\to Y$. Say $X$ is glued together by an open cover $U_ {i}\subset X$. Then $f$ is a global morphism from $X$ to $Y$ if $f$ restricts to local morphisms on each and every open patch of $X$, namely 
$$
f \mid_ {U_ {1}} : U_ {1}\to Y
$$
is a morphism of ringed spaces. 

- - -

The gluing of prevarieties is of key importance in the study of global properties. However, there are good gluing and bad gluing. Consider the gluing of two $\mathbb{A}^{1}$ to the projective line $\mathbb{P}^{1}$ again, which is an example of good gluing. One can construct easily a bad gluing by identity gluing function,
$$
X_ {1} \to X_ {2}, \quad x \mapsto x \text{ instead of } x\mapsto \frac{1}{x}.
$$
The final result is an affine line but with **two origins**! One from $X_{1}$ and one from $X_ {2}$. This is bad since the solution of some polynomial functions may not be closed anymore, such as the identity function
$$
X_ {1} \to X_{2}, X_ {2} \to X_ {1}
$$
glued to 
$$
g: X \to X
$$
has fixed point sets
$$
\left\{ x \in X \,\middle\vert\, g(x)=x \right\} = X - \left\{ 0,0 \right\} 
$$
which is not closed.

### Subprevarieties

Recall that a prevariety is roughly speaking a ringed space cover by affine varieties. Just like groups, rings and manifolds, there exist subprevarieties. Different from groups, rings and manifolds, there are two types of subprevarieties, `open` and `closed`.

The `open subvarieties` are easier to define since any open cover of the whole prevariety $X$ also openly covers the sub manifold, and the structure sheaf can be inherited automatically. In mathematical language, let $X = (X,\mathcal{O}_ {X})$ be a prevariety, any open set $U\subset X$ is a prevariety with structure sheaf 
$$
\mathcal{O}_ {U} = \mathcal{O}_ {X} \mid_ {U},
$$
this works since sets that are open in $U$ are also open in $X$. 

The `closed subvarieties`, on the other hand, are harder to construct, since the open sets in the whole space and in the subspace might be different. We go on to define it anyway.

Let $Z\subset X$ be a closed subset of $X$, we can endow the structure sheaf 
$$
\mathcal{O}_ {Z}(U) = \left\{ \phi: U\to k \,\middle\vert\, \phi \text{ is locally regular at each }x \in U \right\}.
$$

Here $\phi$ is locally regular at each $x \in U$ is there exists some open neighborhood of $x$ on which $\phi$ is regular.

- - -

Let $f: X\to Y$ be a prevariety morphism.

- **Inverse images.**  If $U$ is an open subvariety of $Y$ then $f^{-1}(U)$ is an open subvariety of $X$, the same goes for closed subvarieties.
- **Direct images.** If $W$ is an open subvariety of $X$, or a closed subvariety of $X$, then the direct image $f(W)$ is in general neither.

There is no general notion of subvarieties that are not open (or closed), for example, the union of one open subvariety and one closed subvariety.

### Products: affine varieties

First recall the products of algebraic sets. If $X\subset\mathbb{A}^{m}$ and $Y \subset\mathbb{A}^{n}$ are algebraic sets, then their product $X \times Y\subset \mathbb{A}^{m+n}$ is an algebraic set. It is an affine variety under the Zariski topology. The projection map $\pi_ {X}: X\times Y\to Y$ and $\pi_ {Y}: X\times Y\to Y$ are morphisms.

We can generalize it to affine varieties. Let $X$ and $Y$ now be affine varieties. Then the claim is that $X\times Y$ is truly a product in the categorical sense. Recall that in category theory, product is define by a universal properties. Let $A ,B\in \mathcal{A}$ be objects in category $A$ and assume there exits an arrow $A\to B$, then we call the image of the arrow an `element of shape` $A$ in $B$. The universal property for product says that $X\times Y$ (now regarding $X,Y$ as objects in some category) is the unique object (up to isomorphism) in the category that there exists map $X\times Y\to X$ and $X\times Y \to Y$ which holds for elements of all possible shapes. For a more conventional definition, refer to textbooks on category theory. In our case, it can be shown that in the category of affine varieties, for any affine variety $Z$  and morphism $Z \to X$ and $Z\to Y$ there is a unique morphism 
$$
f_ {X}: Z\to X
$$
and 
$$
f_ {Y}: Z\to Y
$$
such that 
$$
f_ {X} = f \;\circ\;\pi_ {X},\quad f_ {Y} = f\;\circ\;\pi_ {Y}.
$$

We can further generalize products to prevarieties.

**Proposition.** Let $X,Y$ be prevarieties, Then there is a product prevariety $X\times Y$ with morphism $\pi_ {X}: X\times Y\to X$ and $\pi_ {Y}: X\times Y\to Y$ satisfying the universal property of products. It is unique up to a isomorphism. 

The construction works in a more or less intuitive way hence we will omit it. 

- - -

Finally let us return to the "bad gluing" of two varieties $\mathbb{A}^{1}$, resulting in a line with two origins. We want to exclude them from the construction, is there a way?

In topology, the manifold is supposed to be Hausdorff. This excludes the line with two origins, since these two origins can not be separated by two open neighborhoods. 

Unfortunately we don't have usual topology in prevarieties, what we have is Zariski topology, so the original definition of Hausdorff space is not applicable. However, there is a variant of Hausdorff criterion. The original definition for spaces being Hausdorff is equivalent to say that the diagonal
$$
\Delta_ {X} := \left\{ (x,x) \,\middle\vert\, {x \in X} \right\}
$$
is closed under the product topology. We can adopt the same definition but substitute Zariski topology for product topology.

**Definition.** A prevariety $X$ is `separated` if the diagonal 
$$
\Delta_ {X} = \left\{ (x,x) \,\middle\vert\, x \in X \right\}
$$
is closed in $X\times X$. A separated prevariety is called an `(algebraic) variety`. Varieties are also called curves, surfaces or hypersurfaces according to its dimension.

**Proposition.** $X$ is separated if for every topological space $Y$ and a pair of morphisms
$$
p,q: Y\to X
$$
the set
$$
\left\{ y \in Y \,\middle\vert\, p(y)=q(y) \right\} \subset Y
$$
is closed. It is each pair of morphism $p,q$ lifts to 
$$
(p,q): Y \to X \times X,\quad y \mapsto(p(y),q(y)) \in  X\times X.
$$
thus 
$$
\left\{ y \in  Y \,\middle\vert\, p(y)=q(y) \right\} = (p,q)^{-1} (\Delta_ {X})
$$
where $(p,q)^{-1}$ should be regarded as a map inverse, which is continuous. Since $\Delta_ {X}$ is closed, the above set should also be closed.

In the following are some examples.

- Any affine variety is a variety.
- Any open or closed sub prevariety of a variety is a variety.
- The line with two origins (doubled origin line) is not a variety, since it is not `separated`. This can be proved by the proposition we mentioned before. Or notice that the image of $\Delta_ {X}$ only contains two out of the four origins in $X \times X$, thus is not closed.