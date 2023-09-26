---
layout: post
title: Introduction to Higher Form Symmetry
subtitle: Lecture 3
date: 2023-09-26
author: Baiyang Zhang
header-img: img/lib3.jpg
catalog: true
tags:
  - PureMath
  - Notes
---

For conventions used in this note, see my blog [here](http://www.mathlimbo.net/2022/07/17/Conventions-and-Formula/). 

In lecture 2 we have talked about classic symmetry and their re-interpretation using the language of differential (exterior) form. We have made the connection between the so-called symmetry defect operator (SDO) and a charged, point operator. In this note we try to generalized this concept to charged operators defined on manifolds of dimension more than zero, that is, a line, a surface, etc. 

Let's start with the ordinary symmetry once again. Recall that we have written the variation of the action as 
$$
\delta S = \int d^{D-1}x \, J^{\mu}\partial_ {\mu}\epsilon(x)
\tag{1}
$$
where $\xi$ is the parameter of the symmetry transformation, under which the charged operators transform as 
$$
\phi(x) \to \epsilon(x) \Delta \phi(x).
$$
In our convention, $\Delta$ stands for a small but finite change while $\epsilon(x)$ stands for an infinitesimal function. Eq. (1) can be regarded as the definition of the Noether current $J^{\mu}$, which tells us how much the action changed under the transformation in question. But, being a symmetry of the system, of course the action remains unchanged, hence the conservation of the charge 
$$
\partial_ {\mu}J^{\mu} = 0 \Longleftrightarrow d\star J=0.
$$

In the language of differential forms, we can regard $\epsilon$ as a $0$-form, which is (by definition) a function. Then the variation of action reads
$$
\boxed { 
\delta S = \int_ {M^{(D)}} (\star J)\wedge d\epsilon,
\tag{2}
}
$$
where $\star J$ is a $(D-1)$-form, $d \epsilon$ is a $1$-form (since $\epsilon$ is a zero form), hence their wedge product is a $D$-form, something can be integrated over $D$-dimensional manifold $M$, whose boundary is $\Sigma$, by the way. 

The advantage of Eq. (2) is that it can be generalized to higher forms. 