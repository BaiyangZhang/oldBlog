---
layout:     post   				                    # 使用的布局（不需要改）
title:      Notes on (Anti-)de Sitter Space		# 标题 
subtitle:   
date:       2023-05-09 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/lib4.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - Math
    - Commutative Algebra
    - Notes
---

*Disclaimer: Nothing in this note is original.*

In this note we adopt the metric $\eta_ {\mu \nu}=\text{diag}(-1,1,\dots)$.

### De Sitter spacetime

The d-sphere, the maximally symmetric space, is defined by 
$$
(X^{1})^{2}+\dots+(X^{d+1})^{2}=L^{2},
$$
Similarly, let us define the d-dimensional `de Sitter space` with length scale $L$ in $(d+1)$-dimensional Minkowski space $M^{d,1}$ to be the set of points satisfying
$$
-(X^{0})^{2}+(X^{1})^{2}+\dots+(X^{d})^{2}=L^{2},\quad  \text{de Sitter space }dS^{d}
$$
which is like the counterpart of a sphere in Minkowski space. 

At a given $X^{0}$ we see that the rest of the coordinates form a $d$-sphere,
$$
(X^{1})^{2}+\dots+(X^{d})^{2}=L^{2} + (X^{0})^{2}
$$
thus the topology of $dS^{d}$ is isomorphic to $\mathbb{R}\times\mathbb{S}^{d-1}$. 

- - -

The question is, what is the isometry group (the symmetry group that leaves the metric invariant everywhere) of de Sitter space? Before answering it, let us first review some important concepts regarding the symmetry of a space-time. 

**Isometry**

Is the geometry at point $P$ is same as the geometry at $Q$, the two points $P,Q$ are said to be `isometric`. For example, any two points on a sphere are isometric. However, sometimes the isometry is not so evident from the metric, especially when the metric is poorly chosen. 

Suppose some *continuous transformation of coordinates* brings metric $g(x)$ to $g'(x')$ where the same transformation brings $x\mapsto x'$. If this transformation is a symmetry of the space, then the metric should be invariant under it, thus $g_ {\mu \nu}'(x)=g_ {\mu \nu}(x)$ (note there is no $x'$ anymore. $g'(x')=g(x)$ is true for any continuous change of coordinates, while $g'(x)=g(x)$ is only true for specific transformations. Our questions has turn to finding the solution of this tensor equation.

- - -

**Killing vectors**

Follow the German minister and mathematician Wilhelm Killing (1847–1923), we study two points infinitesimally closed to each other, $x' = x+\epsilon \xi$. Then, from the standard form of transformation of order-two covariant tensors, we find the relations that $\xi$ and $g_ {\mu \nu}$ must satisfy if the coordinate transformation were to be isometric. Such a $\xi$ is called a Killing vector field, or just a Killing vector for short. Roughly speaking, the Killing vector gives the direction in which the coordinate transformation leaves the metric unchanged, for example a static metric admits the Killing vector $(1,0,0,0)$ . This can be neatly summarized in an equation,
$$
\mathcal{L}_ {\xi} \,g(\mu \nu)=0
$$
where $\mathcal{L}_ {\xi}$ the the Lie derivative associated to vector field $\xi$.

Apparently, the linear combination of different Killing vectors is still a Killing vector. The number of linearly independent Killing vectors are of course independent of the choice of metric. 

*Example 1.* The 3-dimensional Euclidean space has three translational Killing vectors and three rotations Killing vectors (corresponds to three planes the rotation could happen). The corresponding Killing vectors would be $(1,0,0), (0,1,0)$ and $(0,0,1)$ for translations and $(y,-x,0),(0,z,-y)$ and $(-z,0,x)$ for rotations.

*Example 2.* Consider two-sphere $\mathbb{S}^{2}$. The Killing vectors correspond to three rotations, whose explicit expression in angular coordinates we will leave as a homework for the interested readers.

- - -

**Maximally symmetric spaces**

The question is, given a $D$-dimensional space, how many Killing vectors we could have at most? There will be $D$ translations and $D(D-1) / 2$ rotations thus the total number is 
$$
D + \frac{D(D-1)}{2} = \frac{2D+D^{2}-D}{2}=\frac{D(D+1)}{2}.
$$

Obviously $E^{3}$ has all the 6 possible Killing vectors. It might be a little surprising that $\mathbb{S}^{2}$ also has the maximal number, i.e. three, of Killing vectors, which is three rotations in 3D space which $\mathbb{S}^{2}$ is embedded, or one rotation and two translations if regarding $\mathbb{S}^{2}$ as itself a 2-Dimensional space. 

A $D$-dimensional Riemannian manifold with $2D(D + 1) / 2$ Killing vectors is said to be `maximally symmetric`. 

A maximally symmetric 
