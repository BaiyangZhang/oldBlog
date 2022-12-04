---
layout:     post   				                 # 使用的布局（不需要改）
title:      The Poincare Lemma and Potentials I	 # 标题 
subtitle:   
date:       2022-11-10 				             # 时间
author:     Baiyang Zhang 						 # 作者
header-img: img/mathArt7.jpg 	                 # 这篇文章标题背景图片
catalog: true 						             # 是否归档
tags:								             # 标签
    - Math
    - Poincare Lemma
    - Potentials
    - Notes
    - TheodoreFrankel
---

### Review

Recall that there are three kinds of integrals, the indefinite, the definite signed and the definite unsigned. In this section we will only consider the signed integral and it's generalization to a manifold, namely the integral of forms. 

We are familiar with the notion of a multiple integral of a function $f$ over a region in $\mathbb{R}^p$, 
$$
\int_{U} \, du^1 \dots du^p f(u),
$$
it doesn't matter in what order the $du^i$'s appear. This definition also neglects information about the orientation of the manifold. So we generalize the above mentioned multiple integral to the integral of differential forms, $\alpha^p = a(u) du^1 \wedge \dots \wedge du^p$ over an **oriented** region $(U,o)\subset \mathbb{R}^p$, 
$$
\int _{(U,o)} \, \alpha = \int_{(U,o)} a(u) \,du^1 \wedge \dots \wedge du^p := o(U) \int _{U} a(u) \, du^1 \dots du^p
$$
where the last integral is the ordinary multiple integral of an ordinary function $a(U)$ over the region $U$, and $o(U)=\pm 1$ is the orientation of the region. 

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
$\sigma$ can be considered as a (almost-everywhere) p-dimensional subset of $M$, furthermore, it is parameterized and oriented. A differentiable map $\phi$ makes it possible to pull back forms defined on $W$ to $M$, and what is the integral of $\phi ^\ast\alpha$ over $\sigma$? Just that of $\alpha$ over the image of $\phi$! It is in spirit very similar to the definition of the action of pull-back forms on vectors, where $\phi ^\ast\alpha(X) = \alpha(\phi_{\ast} X)$, where $X\in T(M)$ is a vector in the tangent space of $M$. 

- - -

### Generalized Stokes's theorem

Let $V^p$ be a compact oriented manifold with or without boundary, which is also the sub manifold of $M^n$. Let $F: M^n \to W^m$ to be a smooth map, the image $F(V)$ in $W$ need not be a submanifold, for example it could intersect with itself or have other kinks of pathologies. Still, if $\beta \in \Omega^p(W)$ is a $p$-form on $W$, it makes sense to talk of the integral of $\beta$ over $F(V)$, and in fact
$$
\int_{F(V)} \beta = \int_{V} \, F^\ast \beta, 
$$
which is more or less the definition of pullback of forms. 

Recall that pullback and exterior derivative are commute, namely for a form $\alpha$ we have $df^\ast \alpha = f^\ast (d\alpha)$, thus
$$
\begin{align}
\int_{\partial F(V)} \beta=\int_{F(V)} d\beta  &= \int_{V} \, F^\ast d\beta =  \int_{V} \, d(F^\ast \beta) = \int_{\partial V} \, F^\ast \beta = \int_{F(\partial V)} \, \beta  
\end{align}
$$
And since this relations holds for any $V$ and $\beta$, we can conclude that
$$
\partial F(V) = F(\partial V).
$$
In other words, taking boundary and continuous map are commute. And since we have added an arbitrary continuous map into the Stokes's theorem, it is called 

**generalized Stokes's theorem**：
$$
\int_{F(V)} \, d\beta = \int_{\partial F(V)} \, \beta.  
$$
The only thing worth mentioning here is that $F(V)$ need not to be a manifold, as long as the integral makes sense. 

Actually one needs to integrate over the piecewise smooth manifolds, such as a solid cone.  

- - -

### Closed forms and exact forms

A form $\beta\in\Omega^p(M)$ is **closed** if $d\beta=0$. For instance,

- zero-forms are just scalar functions, a function $f$ is closed if $df=0=\partial f$, meaning $f$ is a constant;
- for 1-forms, $d\beta^1=0\implies(\partial_{i}\beta_{j}-\partial_{j}\beta_{i})=0$, hence $\beta$ as a vector is curl free;
- similarly, for 3-forms closeness implies divergence free.

A form $\beta$ is said to be **exact** if it is the derivative of some other forms, namely $\beta=d\alpha$ for some $\alpha\in\Omega^{p-1}(M)$.

It is important to recall that 
$$
d^{2}\equiv {0},\quad d(d(\text{anything}))=0.
$$
We present the following statements without proof, 
1. every exact form is closed;
2. the product of two closed forms is closed;
3. the product of a closed form and an exact form is exact, $\beta d\alpha=d(\beta \alpha)$ is $\beta$ is closed.
4. The integral of an exact form over an orientable **closed** manifold is zero;
5. The integral of a closed form over the **boundary** of an **oriented compact manifold** is zero. 

Some of them are obvious and all of them can be proved as an exercise.

The etymology is probably that people borrowed it from homology, we there is a close relationship between exterior forms and homology. Think of boundary operation when you see the exterior differentiation, $\partial\sim d$, then the terminologies start to make sense, for example,
1. A curve with zero boundary is closed, and we san a form with zero derivative is closed;
2. the boundary of a closed curve is zero, namely $\partial(\text{closed})=0$ $\Longleftrightarrow$ $d(\text{closed forms})=0$

We say that a differential is exact when $\partial_{i}\partial_{j}f = \partial_{j}\partial_{i}f$, this is what happens to an exact 2-form, justifying the use of terminology *exact*.

**A closed form is not always exact**, being exact is a much stronger condition. To fully understand it, it is useful to see an example:
$$
\boxed{
\beta=\frac{xdy-ydx}{x^{2}+y^{2}}
}
$$
which is closed as can be verified by direct evaluation. Note that it is not defined at the origin. Now the question is, is it exact? The "inverse derivative" of $\beta$ is 
$$
\arctan\left( \frac{y}{x} \right)
$$
It looks like it is exact, but it only looks like so. The problem is that, the original form is defined on $\mathbb{R}^{2}-0$, however the arctan function is not a single-valued function on this manifold! From complex analysis we know that $\arctan$ is single-valued only on one of the many branches of the Riemann plane. This is an example of differential forms that is exact **locally** but not globally. In general when we refer to a differential form as being exact, we mean globally. 

 



- - -

