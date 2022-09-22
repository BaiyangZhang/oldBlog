---
layout:     post   				    # 使用的布局（不需要改）
title:      The Poincare Lemma and Potentials			# 标题 
subtitle:   Based on the book by Theodore Frankel
date:       2022-09-10 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/mathArt7.jpg 	# 这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								# 标签
    - Math
    - Poincare Lemma
    - Potentials
    - Notes
    - TheodoreFrankel
---

### A More General Stokes's Theorem

Recall that there are three kinds of integrals, the indefinite, the signed and the unsigned. In this section we will only consider the signed integral. We are familiar with the notion of a multiple integral of a function $f$ over a region in $\mathbb{R}^p$, 
$$
\int_{U} \, du^1 \dots du^p f(u),
$$
it doesn't matter in what order the $du^i$'s appear. This definition also neglects information about the orientation of the manifold. So we generalize the above mentioned multiple integral to the integral of differential forms, $\alpha^p = a(u) du^1 \wedge \dots \wedge du^p$ over an **oriented** region $(U,o)\subset \mathbb{R}^p$. 
$$
\int _{(U,o)} \, \alpha = \int_{(U,o)} a(u) \,du^1 \wedge \dots \wedge du^p := o(U) \int _{U} a(u) \, du^1 \dots du^p
$$
where the last integral is the ordinary multiple integral of an ordinary function $a(U)$ over the region $U$, disregarding the orientation, and $o(U)=\pm 1$ is the orientation of the region. 

Next, some terminologies. We define an **oriented parameterized p-subset** of a manifold $M^n$ to be a pair $(U,o;F)$ consisting of an oriented region $(U,o)$ in $\mathbb{R}^p$ and a diffeomorphism 
$$
F:U\to M^n.
$$
We shall also call the point set $F(U) \subset M^n$ a $p$-subset. Note that the map is from p-dimensional space to n-dimensional space, hence the name p-subset. A parameterized p-subset is kind of like a generalized coordinate patch of manifold $M^n$. When $p=1$, we simply have a parameterized curve in $M^n$.  Again, we make no requirements on the rank of the diffeomorphism $F$, for example, for $p=1$ the 1-subset in $M$ is a curve, say $\phi(t)$, and it doesn't need to have rank 1, meaning the curve could have a vanishing tangent vector. In other words, the p-subset $F(U)$ need not have dimension p everywhere, that's why we don't use p-dimensional subset but rather p-subset. Although in the most important cases, the induced map $F_{\ast}$ will have rank p almost everywhere, for example, the polar coordinates of a $\mathbb{S}^2$ defined by $F(\theta,\phi) = (\sin \theta \cos\phi, \sin\theta \sin\phi,\cos\theta)$ gives a parameterized 2-subset or $\mathbb{R}^3$ that covers the unit sphere, however $F_{\ast}$ is rank 2 everywhere except at the poles. 

Using the language of category theory, a p-subset $F(U)$ of manifold $M$ is a $U$-shaped element in $M^n$. Recall that, simply put, in category theory, given a morphism between  The integral $\int _{(U,F)} \, \alpha$ on M is the integral of form $\alpha$ on the element of shape $U$. 

If we are further give a field of differential p-forms $\alpha^p$ on $M$, then we can use $F^\ast$ to pull-back $\alpha^p$ to $U$ and use this to **define** the integral of $\alpha^p$ on $F(U)\subset M$, 
$$
\boxed{
\int _{(U,o;F)} \, \alpha^p := \int _{(U,o)} \, F^\ast \alpha^p.
}
$$
I hope you are comfortable with pull-back maps by now. 

Let 
$$
U \xrightarrow{ F } M^n \xrightarrow{ \phi } W^r
$$
where $F$ is a parameterized p-subset of $M$ and $\phi$ a smooth map. $U$ can be used to parameterized both a p-subset of $M$ and $W$, connected by $\phi$, namely we can construct a new map 
$$
\widetilde{F} = \phi \circ F
$$
so that $(U,\widetilde{F})$ is a parameterized p-subset of $W$. 

Now, given a p-form on $W$, denoted by $\alpha \in \Omega^p(W)$, we can construct the pull-back form on $M$, namely $\phi^\ast \alpha$. The integrate $\alpha$ over $\widetilde{F}(U)$ is 
$$
\int _{(U,\widetilde{F})} \, \alpha = \int_{U}  \, \widetilde{F}^\ast \alpha  
$$
which is nothing but the definition of integral on a p-subset. Write $\widetilde{F}$ as a composition of $\phi$ and $F$, we have 
$$
\int _{(U,\widetilde{F})} \, \alpha = \int_{U}  \, \widetilde{F}^\ast \alpha   = \int_{U}  \, (\phi\circ F)^\ast \alpha = \int_{U}  \, (F^\ast \circ \phi^\ast)  \alpha = \int_{(U,F)}  \, \phi^\ast  \alpha
$$
 We shall write briefly $\sigma \equiv F(U)$, then $(U,\widetilde{F})$ is simply written as $\phi(\sigma)$. This allows us get rid of the manifold $U$ and focus on $M,W$ only. Given $\phi:M \to W$, we then have the **general pull-back formula** 
 $$
\boxed{
\int _{\phi(\sigma)} \, \alpha = \int_{\sigma}  \, \phi^\ast \alpha 
}.
$$
How to understand this formula? Well, $\sigma$ can be considered as a (almost-everywhere) p-dimensional subset of $M$, furthermore, it is parameterized (roughly speaking, given coordinates) and oriented. A differentiable map $\phi$ makes it possible to pull back forms defined on $W$ to $M$, and what is the integral of $\phi ^\ast\alpha$ over $\sigma$? Just that of $\alpha$ over the image of $\phi$! It is in spirit very similar to the definition of the action of pull-back forms on vectors, where $\phi ^\ast\alpha(X) = \alpha(\phi_{\ast} X)$, where $X\in T(M)$ is a vector in the tangent space of $M$. But I have to say the general pull-back formula is not as symmetric, hence, beautiful. 