---
layout:     post   				    # 使用的布局（不需要改）
title:     Theodore Frankel			# 标题 
subtitle:   From 2D real vector space
date:       2023-06-18 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/background14.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - Geometry
    - Minkowski
    - Frankel
---

### The Structure Group of a Bundle

For  line bundles, the transition function $c_ {UV}$ is realized by general linear groups $GL(n)$. In a general bundle, it *may be* possible to choose the transition function $c_ {VU}$ such that they all lie in a specific *Lie group* $G$, 
$$
c_ {UV}: U\cap V \to G
$$
we then say that $G$ is the `structure group` of the bundle. 

Let $M$ be an oriented Riemannian surface ($\text{dim}_ {\mathbb{R}}=2$ manifold), $U,V$ be different patches which support *orthonormal, oriented* frame $e_ {U},e_ {V}$ of tangent vectors. Then the transition functions reduce to $SO(2)$ matrices. We say that *the orthonormal frames have allowed us to reduce the structure group from $GL(N)$ to $SO(N)$.*

### Complex Line Bundles

We have seen that the matrix $J$ resembles the imaginary unit $i$ in many ways, such as $J^{2}=-1$. Given a two dimension real vector space, $J$ actually allows us to turn it into a one-dimensional complex vector space. We will try to apply this idea in the context of vector bundles. 

Given an *oriented surface* $M$, and let $M_ {p}$ be the `tangent plane` at $p$ of the surface, and $e_ {1,2}$ be the frames of $M_ {p}$. Define the action of $J$ on the plane as rotating it by a right angle in the positive sense, namely
$$
J: M_ {p} \to M_ {p}, \quad \; e_ {1}\to e_ {2},\; e_ {2}\to-e_ {1}
$$
then naturally $J^{2}=-1$. $J$ is globally defined, because it makes sense in an overlapping region $U \cap V$, since if the frames in $U$-coordinates and $V$-coordinates are connected by some transition function $c_ {UV}$, then rotating all the coordinates by the right angle preserves the same transition function. Thus, $J$ **allows us to consider each fiber in $TM^{2}$ as a complex line**, the first component of the frame,
$$
e_ {1} \in  M_ {p} \approx   \mathbb{R}^{2} 
$$
can be considered as a complex basis vector
$$
e:= e_ {1} \in M_ {p}^{2}\approx \mathbb{C}^{1}
$$
and the action of pure imaginary number $i$ is given by 
$$
i e := J e_ {1} = e_ {2}.
$$

In term of the complex bases, the complex coordinates can be chosen as 
$$
e^ {U} = e^{U}_ {1}, \quad e^{V} = e^{V}_ {1}, \quad etc. 
$$
The transition function at point $p$ is now given by 
$$
c_ {UV}(p) = e^{i\alpha(p)}. 
$$

*The tangent bundle to an oriented Riemannian surface can be considered as a complex line bundle! The structure group of this bundle is now $U(1)$, the unitary group in one variable!*

The next natural question to ask is, what is the *connection* of the complex line bundle. It should be uniquely given by the connection of the two dimensional real vector space. In terms of the orthonormal frames $e^{U},e^{V},$ etc., we have 
$$
\nabla  e_ {i} =e_ {j} \otimes \omega^{j}_ {\;\;i} = e_ {j} \otimes \omega_ {ji},\quad \text{Euclidean metric}.
$$
Recall that $\omega_ {ij}$ is anti-symmetric. We have
$$
\nabla e_ {1}=e_ {2}\omega_ {21}.
$$

The connection for a complex line bundle should be a complex-number-valued 1-form, we will denote it by $\omega$ too. Let $e$ (without the index) be the complex line bundle connection, we have 
$$
\nabla e = e \omega, \quad  \omega \in \mathbb{C}^{1}.
$$

Since $e_ {2}=ie_ {1}$, we have 
$$
\nabla e = \nabla e_ {1} = e_ {2}\otimes \omega_ {21}=ie_ {1}\omega_ {21}=e_ {1} i\omega_ {21}= e \otimes (i\omega_ {21}). 
$$

Thus we have $\omega = i\omega_ {21}$. 

One last thing. For $\omega=i\omega_ {21}$ be truly a connection of the complex line bundle (defined by the 2D real vector field), $\nabla$ defined by $\omega$ should commute with any constant number, namely
$$
\nabla c \psi = c \nabla \psi, \quad  c = \text{const}.
$$
This is of course true for any *real* constant, but we have a special constant, namely $i$, which is given by $J$ in the 2D real vector version. To check it, we just need to make sure this property holds for the basis,
$$
\nabla i e = i \nabla e.
$$
This is much easier to check, we have
$$
\nabla ie = \nabla i e_ {1} = \nabla e_ {2} = e_ {1} \omega_ {12} = i e \otimes i\omega_ {21} = i \nabla e.
$$

Next natural question to ask is, what is the curvature of the complex line bundle? We have 
$$
\theta = d\omega+\omega \wedge \omega = d\omega = d(-i\omega_ {12}) = -id\omega_ {12} = -i\theta_ {12}.
$$
To be specific, 
$$
\theta = -i\theta_ {12} = -i K \sigma^{1}\wedge \sigma^{2}
$$
where $K$ is the Gauss-Riemann curvature $R^{12}_ {\;\;\;12}$ of $M^{2}$. 

