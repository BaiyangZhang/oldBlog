---
layout:     post   				    # 使用的布局（不需要改）
title:     Fiber Bundles and Principal Bundles		# 标题 
subtitle:   
date:       2023-07-09 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/background11.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - Geometry
    - Minkowski
    - Frankel
---

*Disclaimer: Nothing in this note is original.*

### Fiber bundles

The note is more of a review than introduction, so not so friendly for novices. 

Recall that a `fiber` (or `fibre`) `bundle` $E$ is a manifold consists of a base space $M$, a fiber $F$, with projection map $\pi: E \to M$. We demand that $E$ is locally production manifold of $F$ and some open patch $U$. This is realize by a *diffeomorphism*
$$
\phi_ {U}: F \times U \to \pi^{-1}(U).
$$

At the intersection of different patches we have the transition function that glues different patches together in a smooth fashion, let 
$$
\phi_ {U} = c_ {UV} \phi_ {V}
$$
where $\phi_ {U}$ can be regarded as bundle $\pi^{-1}(U)$, the same goes with $V$ patch. Of course the transition function is required to have the following two properties,
- $\phi_ {UV} = \phi^{-1}_ {VU}$
- $\phi_ {UV}\phi_ {VW}\phi_ {WX} = \phi_ {UX}$.

There is a hidden (well maybe not so hidden) group structure in the definition of fiber bundle: The set of diffeomorphisms of the fiber $F$. It need not be a Lie group. If all the maps (transition functions) $\phi_ {UV}$ lie in a **subgroup** $G$ of the group of all diffeomorphism of $F$, we say that $G$ is the `structure group`, sometimes just group, of the fiber bundle. For example, the structure group of a Mobius band is $\mathbb{Z}_ {2}$ group.

A (local) `cross section`, or just a section, is a map $s: U\to E$ such that $\pi \,\circ\, s=\mathbb{1}$. Again we can use the transition function to glue local sections together to form a global section.

- - -

Let $M$ be a $n$-dimensional manifold and let $FM$ (F for frame) be the collection of all *orthonormal* frames $\mathbf{f}_ {1,\dots,n}$ you could have on $M$. $\mathbf{f}$'s are defined point-by-point. The fiber $\pi^{-1}(p)$ where $p\in M$ is the collection of all the orthonormal frames at $p$. To be specific, given any frame $\mathbf{e}$ at $p$, then the most general frame is given by 
$$
\mathbf{f} = \mathbf{e}g,\quad  \text{i.e. } f_ {\beta} = e_ {\alpha} g^{\alpha}_ {\;\; \beta},\quad  g\in O(n).
$$
Thus, *after* a single frame $\mathbf{e}$ is chosen, $\pi^{-1}(p)$ can be identified with a Lie group $O(n)$, which is also the structure group. 

The local trivialization $U\times F\to\pi^{-1}(U)$ then becomes
$$
\phi_ {U} : U\times G\to\pi^{-1}(U)
$$
and assigns to each $p\in M$ and each $g \in G$ the frame
$$
\phi_ {U}(p,g) = \mathbf{e}_ {U}(p) \, g.
$$

In an overlap, $\mathbf{f}(p)$ would have another representation 
$$
f_ {p} = \mathbf{e}_ {V} (p) g_ {V}(p)
$$
which is connected to $\mathbf{e}_ {U}$ by 
$$
\mathbf{e}_ {V} = \mathbf{e}_ {U} c_ {UV}.
$$
Then
$$
\mathbf{f} = \mathbf{e}_ {U}g_ {U} = e_ {V}g_ {V} = e_ {U}c_ {UV}g_ {V}.
$$
The last relation can be interpreted both actively or passively. The action of $c_ {UV}$ on $F$ is the right action of $O(n)$.

**Principal bundle.** Given a bundle 
$$
\left\{ E\xrightarrow{\pi} M, F, G \right\}
$$
where $G$ is the structure group, it is called a principal bundle if the following two conditions are satisfied.
- The fiber $F$ is the same as the structure group, for example both of them could be $O(n)$,
- The *transition function* $c_ {UV}$ acts on the fiber as the left group action. Note here by "fiber" we mean the trivilization of it, in the example of the frame bundle we mean $g_ {U}$.

Return to our example of frame bundle, the frame bundle is the principal bundle `associated` with the tangent vector bundle $TM$. 

- - -

The principal bundles have a remarkable property that is not shared among fiber bundles in general: the structure group acts on the bundle in a natural way as a group of transformations. Take the frame bundle for example. Let $g\in G$ be a given matrix and $\mathbf{f}=(\mathbf{f}_ {1},\dots,\mathbf{f}_ {n})$ be a frame at $p\in M$, then $\mathbf{f}$ is nothing but a point the bundle $E=FM$. We can let $g$ send this point $\mathbf{f}$ to a new point $g(\mathbf{f})= g(\mathbf{f})$ by 
$$
g: \mathbf{f} \mapsto \mathbf{f}g.
$$
Note that $g$ now acts from the right, so it is consistent with the trivialization of the fibers. 

If we instead have a tangent (vector) bundle, things would not be so smooth and natural. Given a point in $TM$, that is a tangent vector $\mathbf{v}$ at $p\in M$, and given a matrix $g \in G$, what is the action of $g$ on $\mathbf{v}$? We can not have a column form of $\mathbf{v}$ without choosing a specific frame, and only after turning $\mathbf{v}$ into a column can we define the action of $g$ on $\mathbf{v}$! Choosing a specific frame is very unnatural, it ruins the abstractness, or free-of-option side of the tangent vector. 

For any principal bundle, we have

**Theorem.** The structure group $G$ of a principal bundle $P$ acts "from the right" on $P$,
$$
g: \mathbf{f} \mapsto \mathbf{f}\,g
$$
without fixed points when $g\neq e$, and preserved the fiber ($\pi(\mathbf{f}g)=\pi(\mathbf{f})$).

Note that the left translations in $G$ (say by $c_ {VU}$) commute with right translations (say by $g$). 

Let $A \in {\frak g}$ where ${\frak g}$ is the Lie-algebra of $g$. Introduce the $1$-parameter subgroup $e^{ tA }$, which is a $G$-valued thing, so can serve as an element of the structure group, acting on $\mathbf{f}$ from the right, by definition
$$
\mathbf{f} \mapsto \mathbf{f}e^{ tA }.
$$
Define the velocity vector field on $P$ 
$$
A^{\ast }(\mathbf{f}) := \frac{d}{d t}  (\mathbf{f}e^{ tA }){\Large\mid}_ {t=0} .
$$

On a patch $U$, $\mathbf{f}$ is parametrized by $\mathbf{e}_ {U}f_ {U}$ with some base point $\mathbf{e}_ {U}$ and the action is completely described by
$$
f_ {U} \to f_ {U} e^{ tA },
$$
whose velocity vector at $f_ {U}\in G$ is 
$$
\frac{d}{dt}  (f_ {U}e^{ tA }) {\Large\mid}_ {t=0} = f_ {U} A. 
$$
Recall that $f_ {U}$ is $g$-valued and $A$ ${\frak g}$-valued, $f_ {U}A$ is the left-translate of vector $A$. 

The vector field $A^{\ast}$, sometimes denoted as $A^{\sharp}$, is called the `fundamental vector field` associated to $A$.