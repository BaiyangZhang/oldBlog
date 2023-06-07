---
layout:     post   				    # 使用的布局（不需要改）
title:     Basic Category Theory 			# 标题 
subtitle:   Adjoints
date:       2023-06-04 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/background4.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - 
---

### Adjoints

Let $F: \mathcal{A}\to \mathcal{B}$ and $G: \mathcal{B}\to \mathcal{A}$ be a pair of functors in opposite direction. We say that $F$ is `left adjoint` to $G$, and $G$ is right adjoint to $F$, and write 
$$
F \dashv G
$$
if for all $A \in  \mathcal{A}$ and $B \in\mathcal{B}$ we have 
$$
\text{Mor}(F(A),B) \cong \text{Mor}(A,G(B))
$$
*naturally*.

If $f$ is an arrow and $\overline{f}$ its counterpart under adjointion, we call $\overline{f}$ the `transpose` of $f$.

For example, let $\text{Vect}_ {k}$ be the category of vector spaces and $\text{Set}$ the category of sets. Let $U$ be the forgetful functor ($U$ for underlying set) and $F$ the free functor. Then we have 
$$
F\dashv U,\quad  \text{Free functor} \dashv \text{Forgetful functor}.
$$

- - -

**Algebraic theory.** Consider a group $G$, it has multiplication, inverse and identity element defined. They can be considered as 
$$
\text{multiplication: } G\times G\to G,\;\text{inverse: } G\to G,\; \text{identity: } \star\to G
$$
where $\star$ is a singleton group. They can further be denoted by 
$$
\text{multiplication: } G^{2}\to G,\;\text{inverse: } G\to G,\; \text{identity: } G^{0}\to G.
$$

This inspires the definition of an algebraic theory. An algebraic theory consists of two things, 1) a collection of operations of specified arity (number of inputs) and 2) a collection of equations. For example, the theory of group has an operation of arity $2$, one of arity $1$, one of arity $0$. An `algebra` or `model` of an algebraic theory consists of a set $X$ together with a specified map $X^{n}\to X$ for each operation of arity $n$, such that the equations hold everywhere. For example, an algebra for the theory of groups is exactly a group.

In a nutshell, the main property of algebras for an algebraic theory is that the operations are defined everywhere on the set, and the equations hold everywhere too. This is why the theories of groups, rings, and so on, are algebraic theories, but the theory of fields is not, where the axiom for multiplicative inverse can not be written as an equation that holds for every element in the underlying set, since the zero elements has no inverse.

The category of fields seems to behave poorly, in comparison to the category of groups or vector spaces. We'll say more about it later. 

- - -

**Initial and terminal objects.** An object $I$ in category $\mathcal{A}$ is `initial` is for every $A\in\mathcal{A}$, there exists *exactly one map* $I\to A$. Similarly, an object $T$ is `terminal` if for every $A\in\mathcal{A}$ there exists exactly one map to it, $A\to T$.

For example, the empty set $\emptyset$ is initial in $\text{Set}$, the trivial group is initial in $\text{Grp}$, and $\mathbb{Z}$ is initial in $\text{Rings}$. The one-element set is terminal in $\text{Set}$, the trivial group is terminal (as well as initial) in $\text{Grp}$, and the trivial (one element) ring is terminal in $\text{Ring}$. The terminal object of $\text{CAT}$ is the category $\mathbb{1}$ containing just one object and one map (necessarily the identity on that object).

A category need not have an initial object, but if it does, it is unique up to isomorphism. The proof uses the fact that there exists *only one* map from $I$ to itself.

Initial and final objects can be regarded as special functors, or more precisely the images of functors, but here we don't extinguish them. Still let $\mathbb{1}$ be the category with only one objects and one identity map, note that we treat $\mathbb{1}$ not as an object in $\text{CAT}$ but itself a category, so we can talk about functors from it or to it. After some calculation we see that *the initial objects can be regarded as the left adjoints of the functor $A\to \mathbb{1}$* and the terminal object the right adjoint of $A\to \mathbb{1}$.

- - -

Let $F: \mathcal{A}\to \mathcal{B}$ be the left adjoint of $G: \mathcal{B}\to \mathcal{A}$, namely $F \dashv G$. They have to satisfy the `naturality requirement`, which means that as $A$ varies in $\mathcal{A}$ and $B$ varies in $\mathcal{B}$, the isomorphism between the set of $(F(A),B)$ and $(A,G(B))$ are compatible with all the structure already in place. 

We ask: what is the transpose of identity maps? Given $A\in\mathcal{A}$, functor $F$ sends it to an object $F(A)$ in $\mathcal{B}$, which must have identity map $\mathbb{1}_ {F(A)} = (F(A)\to F(A))$, which is also the image of $\mathbb{1}_ {A}$ under $F$,
$$
\mathbb{1}_ {F(A)} = F(\mathbb{1}_ {A}).
$$
Since $F$ is the left adjoint of $G$ we can move $F$ on the left to $G$ on the right, obtaining 
$$
\mathbb{1}_ {F(A)}: (F(A)\to F(A))\cong(A\to GF(A)),
$$where the rhs is now a map in category $\mathcal{A}$, call it $\eta_ {A}$.  Similarly for $B\in\mathcal{B}$. This defines two *natural transformations*
$$
\eta: \mathbb{1}_ {\mathcal{A}} \to G\,\circ\,F, \quad  \epsilon: F\,\circ\,G\to \mathbb{1}_ {\mathcal{B}}.
$$
$\eta$ is called the `unit` of the adjunction, $\epsilon$ called the `counit`.

Note that unit consists of maps in the codomain of the left adjoint functor, counit the domain of the left adjoint functor.

The `triangle identity` of $\eta$ and $\epsilon$ says that the two arrows from $F(A)$ to itself,
(1). $$
\mathbb{1}_ {F(A)}: F(A) \to F(A)
$$
and 
(2). 
$$
F(\eta_ {A}): F(A) \to FGF(A) \text{ followed by } \epsilon_ {F(A)}: FGF(A)\to F(A)
$$
are the same. 

**Theorem.** Take categories and functors $F: \mathcal{A}\to \mathcal{B}$ and $G: \mathcal{B}\to \mathcal{A}$, there is a one-to-one correspondence between
1. adjunctions between $F$ and $G$, denoted $F\dashv G$ and 
2. pairs $\eta: \mathbb{1}_ {\mathcal{A}}\to GF$ and $\epsilon: FG\to \mathbb{1}_ {\mathcal{B}}$ of natural transformations satisfying the triangle identities.

### Adjunctions via initial objects

**Comma category.** Define three categories and two functors
$$
\mathcal{A} \xrightarrow{P} \mathcal{C} \text{ and } \mathcal{B}\xrightarrow{Q}\mathcal{C}
$$
the `comma category`, denoted $P\Rightarrow Q$ or $P\downarrow Q$ is the category defined as follows:
- objects are triples $(A,h,B)$ with $A\in\mathcal{A},B\in\mathcal{B},h: P(A)\to Q(B)$ in $\mathcal{C}$,
- maps $(A,h,B)\to(A',h',B')$ are pairs $(f: A\to A',g: B\to B')$ such that in category $\mathcal{C}$, the two ways from $P(A)\to Q(B')$ give the same results.

Note that although there is a double arrow in $P\Rightarrow Q$, the comma category is *not* a natural transformation between functors $P$ and $Q$ since $P,Q$ has different codomains.

Comma category is a category constructed from three categories and two functors, with appropriate naturality conditions.

**Slice category.** Let $A\in\mathcal{A}$, the slice category of $\mathcal{A}$ over $A$, denoted by $\mathcal{A} / A$, is the category whose objects are maps into $A$, i.e. the things "seen from $A$", and the maps are commutative triangles. More precisely, the objects are pairs $(X,h)$ where $X\in\mathcal{A}$ and $h: X\to A$, and a map $(X,h)\to(X',h')$ in $\mathcal{A} / A$ is a map 
$$
f: X\to X'\text{ such that }X\xrightarrow{f}X' \xrightarrow{h'}A \text{ is the same as } X\xrightarrow{h}A.
$$

Slice categories are a special case of comma categories. Recall that functors $\mathbb{1}\to\mathcal{A}$ are just objects in $\mathcal{A}$. We fix the image of $F(1)=A$ where $1\in\mathbb{1}$ is the only object in category $\mathbb{1}$. The comma category constructed with $\mathbb{1}_ {\mathcal{A}}: \mathcal{A}\to\mathcal{A}$ and $F: \mathbb{1}\to\mathcal{A}$, denoted $\mathbb{1}_ {\mathcal{A}}\Rightarrow A$ or sometimes $\mathbb{1}_ {\mathcal{A}}\downarrow A$, is essentially the same as the slice category of $\mathcal{A}$ over $A$, 
$$
\mathcal{A} / A \cong (1_ {\mathcal{A}}\Rightarrow A).
$$

Even though the comma category is not itself a natural transformation, it does need to meet the requirements of naturality, in the sense that if there exist more than one way to construct arrows from one object to another, they should be essentially the same. Consider category $\mathbb{1}, \mathcal{A},\mathcal{B}$ and functors
$$
A: \mathbb{1}\to\mathcal{A},\quad G: \mathcal{B}\to\mathcal{A}
$$
and the comma category
$$
A\Rightarrow G \text{ with objects } (h,B) \text{ where }B\in \mathcal{B},\;h: A\to G(B).
$$
A map in $A\Rightarrow G$ is a map $(h,B)\to(h',B')$ is also a map $q: B\to B'$ in $\mathcal{B}$ making the triangle
$$
f': A\to G(B') \text{ and } A\xrightarrow{f} G(B)\xrightarrow{G(q)}G(B')
$$
commute.

