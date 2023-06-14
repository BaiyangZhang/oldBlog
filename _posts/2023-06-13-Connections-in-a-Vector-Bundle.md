---
layout:     post   				    # 使用的布局（不需要改）
title:     Connections in a Vector Bundle			# 标题 
subtitle:   
date:       2023-06-13 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/background19.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - Geometry
    - Minkowski
    - Frankel
---

*Disclaimer: Nothing in this note is original.*

Let $E\xrightarrow{\pi}M$ be a vector bundle of rank $K$. A section $\sigma$ of $E$ assigns to each trivializing patch $U\subset M$ components $\sigma_ {U}$ such that 
$$
\sigma_ {V} = c_ {VU} \sigma_ {U}.
$$

A `vector-valued p-form` associated to each p-tuple of vectors another vector, similarly, an` $E$-valued p-form` associated to each p-tuple of vectors (all defined with respect to $x\in M$) an element of the bundle $\pi^{-1}(x)\subset E$. I guess you can also call it $F$-valued p-form, where $F$ is the fiber.

Component-wise, for a rank $K$ vector bundle, a section is a $K$-dimensional vector and an $E$-valued p-form is a tuple of $K$ p-forms, each element of the tuple takes $p$ vectors and spits out a component of the $K$-dimensional vector. For example, let $\alpha \in\Omega^{p}(M)$ and $\sigma$ a section of $E$, then 
$$
\psi:= \alpha \otimes \sigma
$$
is a p-form sector of $E$.

- - -

A `connection` $\nabla$ of $E$ is an operator taking sections $\sigma$ of $E$ into $E$-valued 1-forms $\nabla \sigma$ such that the Leibniz rule holds. It is a 1-form since $\nabla$ still needs to take a parameter vector $X$ to form our familiar covariant derivative $\nabla_ {X}: \sigma\to E$. The Leibniz rule says that, given a function $f$, we have
$$
\nabla(\sigma f) = (\nabla \sigma) f + \sigma\otimes df.
$$

Let $e=(e_ {1},\dots,e_ {K})$ be a frame of sections over $E$, namely $(e_ {1},\dots,e_ {K})$ expand the section over $E$. Then the connection acting on one of the components of $e$ is
$$
\nabla e_ {\alpha} = e_ {\beta}\otimes \omega^{\beta}_ {\;\;\alpha}=: e \otimes \omega
$$
 where $\omega$ is secretly a *1-form*, in its component form we have
 $$
\omega=\omega^{\alpha}_ {\;\; \beta} = (\omega^{\alpha}_ {\;\; \beta})_ {i}dx^{i}.
$$
We can think of it as a machinery that when given a vector, it spits out a matrix. We will try to use consistently the Greek letters or capitals Roman letters for fiber indices, and Roman lowercase for base-manifold indices. We shall also omit the tensor product sign, to make our lives as simple as possible. Here we are assuming that $x^{i}$ are the local coordinates of a trivializing patch $U\subset M$. 

Given any section expanded in basis of $e_ {\alpha}$ we have the Leibniz rule
$$
\nabla \psi = \nabla (e_ {\alpha}\psi^{\alpha})  = (\nabla e_ {\alpha}) \psi^{\alpha}+ e_ {\alpha}d\psi^{\alpha} = e_ {\beta}\omega^{\beta}_ {\;\; \alpha} \psi^{\alpha} + e_ {\alpha} d\psi^{\alpha},
$$
collected the terms w.r.t. basis we have 
$$
\boxed { 
\nabla (e\psi) := e \nabla \psi, \quad  \nabla \psi = (d+\omega)\psi.
} 
$$

Furthermore since $\nabla \psi$ are themselves $E$-valued, we require them to be `covariant`, namely
$$
\psi_ {V}=c_ {VU}\psi_ {U}\implies (\nabla \psi){\Large\mid}_ {V} = c_ {VU}(\nabla \psi){\Large\mid}_ {U} .  
$$
Recall that $c_ {VU}$ is a matrix in the Lie-algebra space,
$$
c_ {VU} = (c_ {VU})^{\alpha}_ {\;\;\beta}
$$
and we have 
$$
\omega_ {V} = c_ {VU} (\omega_ {U}+d) c_ {VU}^{-1},
$$
which looks just like the gauge transformation of the gauge field. 

Note that our convention is 
$$
e_ {V} = e_ {U} c_ {UV}.
$$

The `covariant derivative` is defined from the connection with a vector $X\in TM$. 
$$
\text{covariant derivative}:= \nabla_ {X} \psi = \nabla \psi(X) = e[X(\psi)+\omega(X)\psi]
$$
where 
$$
\omega(X) = (\omega^{\alpha}_ {\;\; \beta})_ {i}dx^{i}(X) = \omega^{\alpha}_ {\;\; \beta i} X^{i}.
$$
Then, the component form reads
$$
\nabla_ {X}(\psi)^{\alpha} = X^{i}\partial _ {i}\psi^{\alpha} + X^{i} \omega^{\alpha}_ {\;\; \beta i}\psi^{\beta}.
$$

We let $\nabla$ sends a $E$-valued $p$-form to $E$-valued $(p+1)$-form, called the `exterior covariant differential`. Let $\alpha$ be a $p$-form, then
$$
\nabla (\psi \otimes \omega) := (\nabla \psi)\wedge  \omega + \psi \otimes  d\omega
$$
namely $\nabla$ acts on the fiber and the form by the Leibniz law. 

It is a good exercise to see how $\nabla$ acts on $\nabla \psi$ which is a 1-form. we have 
$$
\nabla \psi = \nabla(e_ {\alpha}\psi^{\alpha} ) = (\nabla e_ {\alpha}) \otimes \psi^{\alpha} + e_ {\alpha}\otimes (d\psi^{\alpha}) = e_ {\beta}\omega^{\beta}_ {\;\; \alpha}\otimes \psi^{\alpha} + e_ {\beta}\otimes d\psi^{\beta}
$$
where $\omega$ is a 1-form, so $\nabla \psi$ is indeed a one form. Acting $\nabla$ on it again we have 
$$
\nabla^{2}\psi = \nabla[e\omega \otimes \psi+e\otimes d\psi]
$$
where we have neglected all the indices, 
$$
= [(\nabla e)\omega+e d\omega]\otimes \psi + e\otimes d^{2}\psi
$$
since $d^{2} = 0$ we have 
$$
= e\omega \wedge \omega \otimes \psi + ed\omega \otimes \psi = e(d\omega+\omega \wedge \omega) \psi.
$$

Curvature is introduced as 
$$
\nabla^{2}(e) = \nabla(e\otimes \omega) = e\otimes  \theta
$$
where 
$$
\theta = d \omega + \omega \wedge \omega=:d\omega+\omega^{2}
$$
and is connected with the Riemann curvature by 
$$
\theta^{\alpha}_ {\;\;\beta} = \frac{1}{2} R^{\alpha}_ {\;\beta ij} dx^{i}\wedge dx^{j}.
$$

There is no notion of torsion in a connection for a general vector bundle.

