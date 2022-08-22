---
layout:     post   				        # 使用的布局（不需要改）
title:      $C^*$-algebra and Finite Ring Extensions 	    # 标题 
subtitle:                               #副标题
date:       2022-08-22 				    # 时间
author:     Baiyang Zhang 				# 作者
header-img: img/mathArt1.png 	        #这篇文章标题背景图片
catalog: true 						    # 是否归档
tags:								    #标签
    - math
    - functional analysis
    - distribution
---

## $C^*$-algebra and Finite ring extensions

First we need to know what is a field extension. The definition is quite straightforward: if you can construct a new field $K$ from old field $k$ so that $k$ is a subset of $K$, then $K$ is an extension field over $k$, denoted as $K/k$.

If $K/k$ is a field, and element $y$ in K is said to be *algebraic* over $k$ if $y$ is the solution of some equation $k[x]=0$.

A polynomial $a_n y^n + \cdots + a_1 y + a_0$ is said to be *monic* if $a_n = 1$.

We have two different dependence relations:
- algebraic dependence relation: $f(y) = a_n y^n + \cdots + a_1 y + a_0 = 0,\quad f\in k[Y]$, and
- integral dependence relation: $f(y) = y^n + a_{n-1} y^{n-1}\cdots + a_1 y + a_0 = 0,\quad f\in A[Y]$, where $A$ is a ring.

So, similar to saying "y is algebraic over k", we can also say things like "y is integral over S, for $S\subset R$ is ring extension".

The following definition will be important.

- A Banach space is both a *vector space* and a *measure space*. 

Being a vector space means that one can add two elements in a Banach space together, but in general not multiply them. A vector space with a multiplicative structure is called an **algebra**, and if the space is a Banach space, and the multiplication satisfies $\lVert xy \rVert \le \lVert x \rVert \lVert y \rVert$ for any two elements, then it is called a **Banach algebra**.

A $C^*-$algebra is a Banach algebra with an involution, which means that for any elements x in the space, it is associated with another element $x^*$ that satisfies 
- $x^* =x$,
- $\lVert x^* \rVert = \lVert x \rVert$,
- $(x+y)^*=x^*+y^*$,
- $(xy)^*=y^* x^*$,
- the $C^*$-identity, $x^* x = \lVert x^2 \rVert$.

An example of $C^*-$algebra is the space of all the continuous linear maps on a Hilbert space, $B(H)$. For an element $T\in B(H)$, $T^*$ is defined to be $\langle x,Ty \rangle = \langle T^*x,y \rangle$ , and the norm is defined to be the smallest const M such that $\lVert Tx \rVert\leq M \lVert x \rVert$.

A fundamental theorem of Gelfand and Naimark states that every $C^*$-algebra can be represented as a subalgebra of $B(H)$ for some Hilbert space $H$. I don't know either how to prove it or the significance of it.

Let A be a ring, by definition, an A-algebra is a ring B with a given ring homomorphism $\phi:A\to B$. Let B be an A-algebra, 
- B is a finite A-algebra (or is finite over A) if it is finite as an A-module. Recall that we say B is a finite A-module, or finitely generated A-module if there exists finite $b_1,\dots,b_n, n\in N$ such that every element of B is an A-linear combination of the $b_i$, $b = x_1 r_1 + \dots x_n r_n, \, r_i \in A$.
- An element $y\in B$ is integer over A if there exists a monic polynomial $f(Y)\in A'[Y]$ such that $f(y)=0$. The A-algebra B is said to be *integral* over A if, as you can guess, all the elements are integral over A. Note that the terminology *integral domain* and *integral extension* are unrelated.

If B is an A-algebra, then we can naturally define $A \cdot B$, so B is automatically an A-module.

As an example, $k[X^2]$ is integral over $k[X]$.

---

If B is an A-algebra and $A \subset B$, then B is a ring extension of A. We have the following proposition.

- The subset of B, defined by $\tilde{A} = \{y\in B | y\text{ is integral over A}\}$, is a subring. Moreover, $\tilde{\tilde{A}}=\tilde{A}$.
$\tilde{A}$ is called the **integral closure** of A in B. If $A = \tilde{A}$ then A is said to be integral closed in B.

An integral domain is **normal** if it is integrally closed in its field  of fractions. That is, an integral domain A is normal if $A = \tilde{A} \subset F=\text{Frac} A$. For any integral domain A, the integral closure of A in $\text{Frac} A$ is also called the normalization of A.

As an important example, in algebraic number theory, a *number field* is a finite extension $\mathbb{Q}\subset K$ of the rational field, that is, $[K:\mathbb{Q}] = dim_{\mathbb{Q}}K < \infty$. Recall that notation $[K:F]$ denotes the extension field degree (or relative degree, or index) of K over F, namely the dimension of K as a vector space over F. 





