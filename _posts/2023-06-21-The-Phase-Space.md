---
layout:     post   				    # 使用的布局（不需要改）
title:     The Phase Space 			# 标题 
subtitle:   A geometric perspective
date:       2023-06-21 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/background18.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - phaseSpace
    - quantization
---

The first step to understand quantization fully, especially the geometric quantization, is to understand the familiar phase space but from a more geometric point of view.

### The Phase Space in Mechanics

Let $M$ be the n-dimensional `configuration space` of a dynamical system, with local coordinates $q^{1},\dots,q^{n}$ which are the generalized coordinates. The Lagrangian is a function of $q$ and $\dot{q}$, which are the generalized velocity. For example $q$ would be an angle and the generalized velocity would be the angular velocity. We have 
$$
L = L(q,\dot{q}).
$$

But there is a more beautiful way to say the same thing, if you are familiar with tangent bundles $TM$, then you see that the *Lagrangian is nothing but a real-valued function defined on the tangent bundle to $M$*. A point in the tangent bundle is given by a $2n$-tuple, consisting of a $n$-tuple $q^{i}$, which pinpoint a position on the base space, and another $n$-tuple of generalized velocity $\dot{q}$, which gives as an element of the fiber at that point. In face $\dot{q}$ in this sense should be written as 
$$
\dot{q} = \frac{dq}{dt} \partial _ {q}, \quad  \dot{q}(f) = \frac{df}{dt} = \frac{dq}{dt} \partial _ {q}(f),
$$
then it is obvious that $\dot{q}$ is a tangent vector to $M$. 

In summary 
$$
L : TM \to \mathbb{R}.
$$

Note that $q$ and $\dot{q}$ are regarded us two *independent variables*. When given a specific path $q(t)$ then we can connect $\dot{q}$ with $q$ by the time derivative. 

Now consider the transition from the Lagrangian to the `Hamiltonian formulation` of dynamics. Hamilton defined the functions, so-called `canonical momenta` or `generalized momenta`
$$
p_ {i}(q,\dot{q}) := \frac{\partial L}{\partial \dot{q}^{} {i}},
$$
note that the position of indices are balanced on both sides. This is **not** merely a change of basis of $TM$, one way to see it is to notice that $p^{i}$ has an upper index but $p_ {i}$ has a lower index, they got different transition functions. $p_ {i}$ actually live in the `cotangent space`, the $n$-tuple $p_ {1},\dots,p_ {n}$ form a `covector`! When put together, the $p$s and $q$s are the local coordinates of a *cotangent bundle to $M$*. The construction of canonical momentum can be regarded as a map
$$
p: TM \to T^{\ast }M.
$$

This space $T^{\ast}M$ in mechanics is called the `phase space` of the dynamical system. A short summary:

- $M$, the $n$-dimensional base space, is the `configuration space`;
- $TM$, the `tangent bundle` to $M$, is the space of all the generalized velocities at all the point of $M$, is called the tangent bundle. The Lagrangian is a $\mathbb{R}$-valued functions on $TM$;
- $T^{\ast}M$, the `cotangent bundle` to $M$, is called the `phase space`. The Hamiltonian can be regarded as a $\mathbb{R}$-valued function on the phase space, similar to the Lagrangian.

$M$ and $T^{\ast}M$ exist as soon as the base manifold $M$ exists, but the identification between vectors (elements of $TM$) and covectors can not be done without introducing the Lagrangian $L$, since $p := \partial L / \partial \dot{q}$. We usually call the Lagrangian the dynamics. 

Since we have lower and upper indices, a natural question to ask is, what can be used to lower or raise the indices? Recall that for a generic manifold with vectors and covectors, the `metric` $g_ {ij}$ or its inverse $g^{ij}$ can be used to do that, then we can guess there also exists some kinds of metric on the configuration space $TM$. Indeed, some simple mathematical manipulations show that the metric can be read off from
$$
p_ {i}=g_ {ij} \dot{q}^{j} \implies g_ {ij} = m \delta_ {ij}\text{ provided } L = \frac{1}{2} m \dot{q}^{2}.
$$
The Lagrangian can also be written in terms of the metric
$$
L = T - V = \frac{1}{2} g_ {ij}\dot{q}^{i}\dot{q}^{j}-V.
$$
In short, the metric is given by the mass matrix. 

For massless particles, there is a clever way to write down the Lagrangian, but it is out of the scope of this note, interested readers can refer to A. Zee's book on general relativity.

In general, given a manifold $M$, both the tangent bundle $TM$ and the cotangent bundle $T^{\ast}M$ comes for free. However there is no natural way to identify a vector with a covector. For this identification, we need some extra structure, namely the metric or the dynamics, a.k.a. the Lagrangian.

### The Poincare $1$-form

There are geometric objects that live naturally on $T^{\ast}M$, not on $TM$. Before introducing a metric, or Lagrangian, such things will only exist on $T^\ast M$, not $TM$.

Recall that $1$-form is simply another name for covector. We now think of $T^\ast M$, the entire cotangent bundle as a $2n$ dimensional manifold. This is quite a change of view, for $T^\ast M$ consists of a base space $M$ with local coordinates $(q^{1},\dots,q^{n})$, and on each point of $M$ is glued another space which is all the covectors at that point, with bases $(dq^{1},\dots,dq^{n})$; however we have introduced $p_ {i}$'s, which function as bases of the the cotangent space as well, for they are linear independent covectors. A generic point in $T^\ast M$ is locally given by $2n$-tuple $(p_ {1},\dots,p_ {n},q^{1},\dots,q^{n})$. A covector in this space is spanned by bases 
$$dp_ {1},\dots,dp_ {n}, dq^{1},\dots,dq^{n}, 
$$
but for Poincare form we need only half of these bases.

**Poincare 1-form.** It is a globally defined 1-form $\lambda$ on every cotangent bundle $T^\ast M$. In local coordinates $(p,q)$ it is given by 
$$
\boxed{ 
\lambda = \sum_ {i} p_ {i} dq^{i}
},\quad  \lambda \in  \Omega^{1}(T^\ast M).
$$
Just ignore the second part if it does not make any sense to you. You can show that $\lambda$ is indeed well-behaved on an overlap of local coordinate patches, hence making it globally well defined. It can also be guess from the fact that all the indices are contracted in the definition.
