---
layout:     post   				    # 使用的布局（不需要改）
title:     Topological stacks			# 标题 
subtitle:   
date:       2023-05-13 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/background11.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - 
---

### Some group theory 

Mathematically, a symmetry of a set $S$ is a transformation that preserves it. All the symmetry transformations naturally form a group. It would be helpful to review some basic definitions of group theory here. A subgroup $H$ of $G$ is denoted $H<G$, if $H$ is a `normal` subgroup, meaning $GHG^{-1}=H$, then $H$ is denoted by $H\lhd G$. Given two groups $H,K$, the simplest way to construct a new group containing $H$ and $K$ as subgroup is by the means of direct product, $H\times K$. The elements of $H\times K$ are $(h,k)$ with multiplication given by $(h_ {1},k_ {1})\times(h_ {2},k_ {2})=(h_ {1}h_ {2},k_ {1}k_ {2})$. The copy of $H$ in $H\times K$ is simply $(H,1)$ and the copy of $K$ in $H\times K$ is $(1,K)$. We have the "recognition theorem" saying that if 1) $G$ can be written as form $hk$ and 2) $H\cap K$ is trivial and 3) elements in the copy of $H$ commutes with that in $K$ then we can write $G$ as a product of $H$ and $K$. However the last condition is not necessary for $G$ to be written as a direct multiplication of $H$ and $K$. 

Let $H,K$ be subgroups of $G$, the direct product $H\times K$ is not guaranteed to be a subgroup of $G$. It is because $h^{-1}kh$, the conjugate of $k$, may not be in $K$ again. If so, $K$ is a normal subgroup. The claim is that $K\times H$ is only a subgroup if one of them is a normal subgroup, for example if $K\lhd G$. How can we come up with a modified version of multiplication such that $H$ and $K$ always gives a group. 

Consider two groups $H,K$ *not* initially in a common group. Suppose $K$ defines an automorphism (which is isomorphism on itself) on $H$, that is, each element $k$ of $K$ defines an automorphism $\phi_ {k}$ on $H$. In other words, we have 
$$
\phi: K\to \text{Aut}(H),\quad k\mapsto \phi_ {k}.
$$

**Definition.** . For two groups $H$ and $K$ and an action $\phi: K\to \text{Aut}(H)$ of $K$ on $H$ by automorphisms, the corresponding semidirect product $H\rtimes K$ is defined as follows: as a set it is $\left\{ (h,k) \,\middle\vert\, h\in H,k\in K \right\}$. The group law on $H\rtimes K$ is
$$
(h_ {1},k_ {1})(h_ {2},k_ {2}):=(h_ {1}\phi_ {k}(h_ {2}),k_ {1}k_ {2}).
$$

The notation in $\rtimes$ has a small $\lhd$ in it, suggesting $H$ (or more precisely, the copy of $H$ in $H\rtimes K$) is a normal subgroup of $H\rtimes K$ whose elements are $(h,1)$. In some convention for semidirect product notation, the group being acted on always goes first in $H\rtimes K$, and the group doing the acting goes second. If we reversed this then the notation could be $K\ltimes H$ so the arrow still points to the normal subgroup.

### Symmetry groupoids

The symmetry represented by group action are in a sense `global` (don't confuse this with global and local gauge theory, which are both depicted by group actions), the symmetries of a structure (geometric or otherwise) always involve the whole structure. To be specific, a global symmetry is one that holds at all points of the spacetime, whereas a local symmetry is one with a different symmetry transformation at different points of the spacetime, that is, a local symmetry transformation is parametrized by the spacetime coordinates. Mathematicians have a local theory of symmetry, which is known as the theory of groupoids. 

The convention is usually that, if a symmetry acts on the space(-time) coordinates, then it is called spacetime symmetry, if not a local symmetry. Rotation is a spacetime symmetry while the gauge transformation is local. The familiar local gauge symmetry (gauge redundancy) is an example of local internal symmetry. But the local gauge symmetry can be regarded as a redundancy when describing the system thus not a symmetry at all. It is more like the equation of motions admits a class of solutions, any two elements in the solution class differ by a gauge transformation.

As an example of a different (from local gauge transformation) kink of local transformation, look at a two-sphere $\mathbb{S}^{2}$.  It is a maximal symmetric space, got all the symmetries you can think of, rotation, reflection, etc. Now, imagine we drill three holes on the two sphere, as shown in the figure below.
![](/img/3holes.png)
The three holes will mess up the symmetry of the $\mathbb{S}^{2}$ seriously, the only symmetry left now is the trivial one! However, if we look locally at points far from the holes, at least for small transformation, these points are not concerned about the holes far far away so some kind of "local" symmetry should still hold. Mathematically, denote the punctured $\mathbb{S}^{2}$ as a manifold $X$, the transformation $g$, then we can construct the direct product $X\times G$ where $G$ is the isometry group of $\mathbb{S}^{2}$. Let the elements of $X\times G$ be $R=(x,g)$, then $g$ can act on $x$ in the usual way. The problem is that $gx$ may not be in $X$ anymore, so we only consider pairs $(x,g)$ such that $gp$ is still in $X$. Then we can study the algebraic property of the set of $R$. For more details of this simple example, refer to the introductory paper by Angelo Vistoli.

The groupoid is usually defined to be a category where every arrow has an inverse. The usual group is just a groupoid with one object. In our context, a groupoid will assign to any two objects $m_ {0}, m_ {1} ∈ M$ a collection (possibly empty) of arrows from $m_ {1}$ to $m_ {0}$. the $m_ {0,1}$ are like objects and $M$ a Category. These arrows are thought of as ‘symmetries’, but in contrast to Lie group actions this symmetry need not be defined for all $m\in M$ – only pointwise. This corresponds to the state that not all pairs of objects need to have arrows. On the other hand, we require that the collection of all such arrows (with arbitrary end points) fit together smoothly to define a manifold, and that arrows can be composed provided the end point (target) of one arrow is the starting point (source) of the next. This reminds us of group structure.

The following note is taken from [this paper](https://www.ams.org/notices/199607/weinstein.pdf), including (some of) the notations. As an simple example, consider the tiling of the (infinite) Euclidean $\mathbb{R}^{2}$ by identical $2\times 1$ rectangles, specified by the set $X$ (idealized as 1-dimensional) where the grout between the tiles lies. To be specific, denote the horizontal grouts $H=(\mathbb{R},\mathbb{Z})$ and vertical grouts $V=(2\mathbb{Z},\mathbb{R})$, then $X=H\cup V$. The set of identical tiles is $\mathbb{R}^{2}-X$. The symmetry group of $X$ is denoted $G$, consisting of rigid translations, reflections and rotations. The normal subgroup of $G$ is the translation group. The lattice $\Lambda$ consists of the corner points of the tiles, $\Lambda=H\cap V=2\mathbb{Z}\times\mathbb{Z}$. 

Although the symmetry greatly constraints the space, there is something lost when going from the tiling of $\mathbb{R}^{2}$ to the symmetry group $G$, 
1. both $X$ and $\Lambda$ satisfy the same symmetry group $G$, even though they describe very different things, even the dimension is different;
2. $G$ contains no local details of the tiling, for example we could fill any color pattern that is symmetric under $G$;
3. If the size of $\mathbb{R}^{2}$ is finite, for example if we were tiling the bathroom floor, then the symmetry group shrinks greatly since most of the original symmetries, such as translation, will move the entire floor thus no longer a symmetry. However a repetition pattern of the floor is clearly visible, we say locally it is still the same tiling. 

Our first groupoid will enable us to describe the symmetry of the finite tiled rectangle. We first define the **transformation groupoid** of the action of $G$ on $\mathbb{R}^{2}$ to be the set 
$$
\mathcal{G}(G,\mathbb{R}^{2}):= \left\{ (x,g,y) \,\middle\vert\, x,y\in \mathbb{R}^{2},g\in G,x=gy \right\} .
$$



### Families and symmetry groupoids

We are interested in two ideas: symmetry and form, and their role in classification.

Consider a mathematical concept, for example *isosceles triangles*, together with a notion of isomorphism, for example *similarity*. This leads to the idea of symmetry. 

To capture the essence of form, in particular how form may vary, we consider families of objects, rather than single objects. For example, instead of just one isosceles triangle we can consider four triangles, three congruent isosceles triangles and one equilateral triangle.  