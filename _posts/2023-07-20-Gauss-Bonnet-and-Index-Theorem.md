---
layout:     post   				    # 使用的布局（不需要改）
title:     Gauss-Bonnet Theorem and Index Theorem 			# 标题 
subtitle:   
date:       2023-07-20 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/background16.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - 
---

### A connection in the frame bundle of a surface

Let $M$ be a 2-dimensional, oriented manifold with a Riemannian metric. Its tangent bundle is a $\mathbb{R}^{2}$ bundle with structure group $SO(2)$. We have seen that we can turn this $\mathbb{R}^{2}$ bundle into a $\text{dim}_ {\mathbb{C}}=1$ complex line bundle. We will work with this complex line bundle in  this section.

Let then $E=TM$ be the complex tangent line bundle to $M$. The structure group is then $U(1)$, that is, the complex numbers $e^{ i\alpha }$ of absolute value $1$. A frame at point $p\in M$ is simply a tangent vector of length $1$, or a complex number of module $1$, denoted by $\mathbf{e}$. Let $FM$ be the frame bundle as usual, with fiber and structure group the circle $G = U(1)$. 
$$
G = U(1), \quad  g = e^{ i\alpha }.
$$

Let $\mathbf{e}_ {U}$ be a frame on patch $U$, that is the same as saying $\mathbf{e}_ {U}$ is a section of $FM$ on $U$. Recall that the `connection` is a 1-form defined on the base space $M$, 
$$
\nabla \mathbf{e}_ {U} = \mathbf{e}_ {U}\otimes \omega_ {U} = \mathbf{e}_ {U}\omega_ {U},
$$
where $\omega_ {U}$ is the connection on $U$. 

Since we require the parallel transport to preserve the length of vector, as a result the connection is pure imaginary. To see that, let 
$$
x=x(t)
$$
be a curve in $U$ starting at point $x_ {0}:=x(0)$. Parallel transport $\mathbf{e}_ {U}(x_ {0})$ along the curve, then get a field defined on the curve, call it $\mathbf{\hat{e}}(t)$. We can use $\mathbf{e}_ {U}$ as some kind of basis, then $\mathbf{\hat{e}}(t)$ is give by the basis and coordinates as 
$$
\mathbf{\hat{e}}(t) = \mathbf{e}_ {U}(x_ {t}) g(t)
$$
for some $g(t)\in U(1)$. $g(t)$ can be regarded as the coordinates of $\mathbf{\hat{e}}$. But then, by the definition of parallel transport we have 
$$
\begin{align}
\nabla \mathbf{\hat{e}} = 0 &= \nabla_ {t}\,\mathbf{\hat{e}(t)} = \nabla_ {t}\, \mathbf{e} g +\mathbf{e}\nabla_ {t}\,g \\
&= e  \omega\left( \frac{d\mathbf{x}}{dt} \right) g + e \frac{dg}{dt}.
\end{align}
$$

and so 
$$
\omega\left( \frac{dx}{dt} \right) =- \frac{dg}{dt} g^{-1}.
$$
But in our particular case 
$$
g = e^{ i\alpha }
$$
thus 
$$
\omega\left( \frac{dx}{dt} \right) = -\frac{id\alpha(t)}{dt}g g^{-1} = -i \frac{d\alpha}{dt} \in  {\frak g} = {\frak u}(1).
$$

We have shown that the connection $\omega$ in our case is pure imaginary. In fact we can generalized this conclusion to general bundles, assume the structure group is $G$ whose Lie algebra is ${\frak g}$, then the connection is a ${\frak g}$-valued 1-form. However, the question is, the connection is a one form on which manifold? Naively it is a 1-form defined on the base manifold, but we will see that we can actually pull it back to the bundle, using the projection $\pi^{\ast}$ (what other choices do we have?).

In our particular case, the complex line bundle, the Riemannian condition demands that the connection $1$-form $\omega$ takes value in the Lie algebra of the structure group.

In general, for a vector bundle $E$, the connection $\omega$ allows us to differentiate a section *with respect to a tangent vector of the base space $M$*. In other words, $\omega$ is a *local* 1-form on $M$. We will show that we can take a step further and define a **global** 1-form on not $M$ but the entire $E$! Take the complex line bundle for example, the base space is a 2-dimensional manifold (with coordinates $(x,y)$) while the bundle is a 3-dimensional manifold (with coordinates $(x,t,\alpha)$).

Let $\mathbf{e}_ {U}$ be a frame over $U$, that is a section of $FM$ over $U$. We will use it as the basis. Let $\mathbf{f}$ be another section of $FM$. Then we can write
$$
\mathbf{f} = \mathbf{e}_ {U}(x) g_ {U}(x), \quad  g_ {U} \in U(1).
$$
Apparently this decomposition of $\mathbf{f}$ into $e_ {U}$ and $g_ {U}$ is local, as the subscript $U$ suggests. The local coordinates of $\mathbf{f}$ is then $(x,\alpha)$ where $g = e^{ i\alpha }$. The covariant derivative of $\mathbf{f}$, after some manipulations reads
$$
\nabla \mathbf{f} = \mathbf{f}\otimes  g_ {U}^{-1}(\omega+d)g_ {U}.
$$

Substitute $g = e^{ i\alpha }$ we have 
$$
\nabla \mathbf{f} = f\otimes (\omega + id\alpha).
$$

Since $\alpha$ can be seen as the local coordinates on the fiber, $d\alpha$ can be regarded as a local 1-form on the fiber, hence on the bundle $\pi^{-1}U$. $\pi^{\ast}\omega$ is also a local 1-form on the bundle, however we usually don't distinguish between $\pi^{\ast}\omega$ and $\omega$. Thus we can define a local 1-form on $\pi^{-1}U$
$$
\omega_ {U} ^\ast  := \omega_ {U} + id\alpha. 
$$

Personally I think this notation to be quite misleading, $\omega ^\ast$ is not *just* the pullback of $\omega$ but with an extra piece, namely an extra 1-form in the fiber direction. But this is the notation adopted in Frankel's book and I intend to stick to his conventions. 

Note that since $\omega_ {U}$ is pure imaginary, the whole thing $\omega ^\ast_ {U}$ is also pure imaginary and an element of ${\frak u}(1)$. 

Notice something remarkable: the connection $\nabla$ has a geometrical meaning that is independent of the specific open cover chosen, independent of the frame chosen. It tells us how to parallelly transport a section, which is independent of the frame. Then the following should not come as a surprise. 

**Theorem.** On an overlap of two coordinates patches $U \cap V$, we have 
$$
\omega ^\ast _ {U} = \omega ^\ast _ {V}.
$$
Thus it makes sense to regard $\omega ^\ast$ as a **global** 1-form defined on the entire bundle $E$. The collection $\left\{ \omega ^\ast \right\}$ define a ${\frak u}(1)$-valued 1-form on all of the principal bundle $FM$.

$\omega ^\ast$ is called the `connection form` on the frame bundle $FM$. 

To prove it, let $\mathbf{e}_ {V}$ be a section over $V$. With our convention we have 
$$
\mathbf{e}_ {V} = \mathbf{e}_ {U} c_ {UV}, \quad  c_ {VU} = e^{ i\beta }.
$$

Then a section $\mathbf{f}$ has two representations 
$$
\mathbf{f} = \mathbf{e}_ {V} g_ {V} = \mathbf{e}_ {U} g_ {U}.
$$

Now we just need to calculate $\omega ^\ast_ {U}$ and $\omega ^\ast_ {V}$, and show they agree with each other, with the help of the formula
$$
\omega_ {V} = c_ {UV}^{-1}(\omega_ {U}+d)c_ {UV}.
$$
This is left as an exercise. 

Then the curvature 
$$
\theta ^\ast := d\omega ^\ast  = \pi^{\ast }d\omega = \pi ^\ast \theta
$$
is also globally defined. We shall call this the `curvature form` of the frame bundle $FM$. Chern's observed that 
**Theorem.** The lift
$$
\pi ^\ast \theta = d \omega ^\ast .
$$

Namely $\theta ^\ast$ is globally exact! Whereas $\theta$ is usually not exact.

### The Gauss-Bonnet-Poincare Theorem

**Theorem.** Let $M$ be a closed (compact and without boundary) Riemannian surface and let $\mathbf{v}$ be a vector field on $M$ with finitely many singularities $p_ {1},\dots,p_ {N}$. Then 
$$
\frac{1}{2\pi} \int \int _ {M} \, K \sigma^{1}\wedge \sigma^{2} = \sum_ {\alpha}j_ {\mathbf{v}} (p_ {\alpha}).
$$

$K$ is defined through the curvature 1-form
$$
\theta ^\ast  = \pi ^\ast \theta_ {12} = \pi ^\ast iK\sigma^{1}\wedge \sigma^{2},
$$
where we have switch back to $\mathbb{R}^{2}$. $j_ {v}$ is the index at some singularity.

This theorem gives us a relation between the total curvature and the sum of indices of the vector field. 

Since the right-hand side is independent of the metric, so must be the left-hand side,
$$
\int_ {M} \, KdA \text{ must be independent of the metric.} 
$$

This is the Gauss-Bonnet theorem. 

The following proof given by Chern shows the equality of the integral with the index sum. 

**Proof.** We shall prove the theorem when $M$ is orientable. If it is not, we can regard it as an embedding of a orientable two-sheeted manifold. 

First let's remove the singularities, by removing small disks $D_ {\alpha}$ centered around the singularities. Then define 
$$
\mathbf{f} = \mathbf{v} / \left\lvert v \right\rvert
$$
which is a unit vector field. It is more helpful to regard it as a frame bundle
$$
M-\sum_ {\alpha}D_ {\alpha} \to FM
$$
which is also very useful in higher dimensional generalizations.

Let 
$$
\Sigma = \mathbf{f}\left( M-\sum_ {\alpha}D_ {\alpha}  \right) \subset FM
$$
be the image of the puncture $M$ under the section $\mathbf{f}$. Then, since $\omega ^\ast$ (not $\omega$) is globally defined, we have 
$$
i \iint_ {M-\cup D_ {\alpha}} \, KdA =  \iint_ {\pi \Sigma}KdA = \iint_ {\Sigma}\pi ^\ast (iKdA) = \iint_ {\Sigma}d\omega ^\ast
$$
Using the Stokes theorem we have 
$$
=\iint_ {\partial \Sigma}\omega ^\ast = \int_ {\partial \Sigma} \, (\pi ^\ast \omega-d\alpha). 
$$

It can be shown that the first term in the integral vanishes as $D_ {\alpha}$ goes to zero (for details see Frankel), what we left is the contribution from the second part. 
$$
\int_ {\partial \Sigma}\, id\alpha =  \oint_ {\mathbf{f(\partial D_ {\alpha})}}d\alpha = \sum\text{indices.}
$$

### Gauss-Bonnet as an index theorem

Recall that the Euler characteristic is expressible in terms of the genus of the manifold
$$
\chi = 2-2g.
$$
The Euler characteristic is also connected with the Betti numbers
$$
\chi = b_ {0}-b_ {1}+b_ {2}.
$$
Finally we write the Gauss-Bonnet theorem in the term
$$
\frac{1}{2\pi}\iint_ {M} KdA = b_ {0}-b_ {1}+b_ {2}.
$$

Recall from Hodge's theorem that $b_ {p}(M)$ is also the dimension of the Harmonic p-forms, which is nothing but the dimension of the kernel of the Laplace operator 
$$
b_ {p}(M) = \text{dim} \text{ ker }\Delta, \quad  \Delta: \Omega^{p}(M)\to\Omega^{p}(M).
$$

In physics, the space of the kernel of an operator is called the space of `zero modes`.Thus, basically, the integral of the curvature of an surface is related to the number of zero modes of some differential operators constructed from the bundle. This is the first and most famous example of the so-called `index theorem.` 