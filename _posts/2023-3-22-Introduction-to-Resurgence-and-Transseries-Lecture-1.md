---
layout:     post   				    # 使用的布局（不需要改）
title:     Introduction to Resurgence and Transseries			# 标题 
subtitle:   Lecture 1
date:       2023-3-22 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/mathArt15.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - Math
    - Transseries
    - Notes
---

### Motivation

Why do I want to spend time on this subject? Because they are super interesting!

But I should maybe say more about it, so that in the future if I were to apply for some research grant, when someone who knows absolutely nothing about resurgence and its application but who decides whether to give me the money, asks me why is this project important, what use does it have and, eventually, why should I give you the money, then I can come back here and just copy the answer. I would say that god knows I have already wasted too much time on grant applications... but thank god I am atheist. 

The following is an incomplete list of the potential applications of resurgence theory.
-   Normal forms for dynamical systems
-   Gauge theory of singular connections
-   Quantization of symplectic and Poisson manifolds
-   Floer homology and Fukaya categories
-   Knot invariants
-   Wall-crossing and stability conditions in algebraic geometry
-   Spectral networks
-   WKB approximation in quantum mechanics
-   **Perturbative expansions in quantum field theory (QFT)**

The most surprising result, at least for me, of resurgence theory in QFT is that one can uncover the non-perturbative results from perturbative expansion alone! Usually to find the non-perturbative results one need to use anything but perturbative results, such as the topology of the vacuum manifold, the homotopy of the solutions to the equation of motion (instanton solutions, etc.), on and on. But resurgence theory lets us to get the non-perturbative results, for instance the contribution of instantons, from analytical continuation of the perturbative results! On the one hand, it is like black magic; on the other hand, I guess I shouldn't be too surprised since if we know all the perturbative expansions then we know everything about the equation of motion, which eventually contains all the non-perturbative results, so in principal the perturbative expansion should be able to generate the non-perturbative results. But that is only in principal. It is still jaw-dropping to see it actually happen.

And I guess it is impossible to make sense out of perturbation theory **without** knowing some of the resurgence theory. After all, is we consider enough terms in perturbative expansion, the power series in coupling actually diverges, so why would it make any sense to just consider the first few terms? Claiming they give the dominant results would also be ridiculous. The answer lies in resurgence theory.

- - -

H. Poincare mentions the so-called "a kind of misunderstanding between geometers and astronomers about the meaning of the word convergence", He proposed a simple example, the two series
$$
\sum \frac{1000^{n}}{n!} \text{ and }\sum \frac{n!}{1000^{n}},
$$
Poincare says that for geometers, namely mathematicians in his time, the first one converges because at large $n$ the terms gets smaller and smaller. But for astronomers the first one is as good as divergent since the next terms doesn't get smaller until $n$ is larger than $1000$. For them the second series diverges because the first $1000$ terms decreases quickly. 

He then proposes to reconcile both points of view by clarifying the role that divergent series (in the sense of geometers) can play in the approximation of certain functions. This is the origin of the modern theory of asymptotic expansion. 

- - -

In this note we shall focus on `formal power series`, such as the Stirling series. Thus the previous example should be written as 
$$
\sum \frac{1000^{n}}{n!}t^{n} \text{ and }\sum \frac{n!}{1000^{n}}t^{n}
$$
where the first one has **infinite** **radius of convergence** while the second one has **zero radius of convergence**. For us, `divergent series` will usually mean a formal power series with zero radius of convergence.

First we will speak of the `Borel-Laplace sumamtion`, which obtains a function from a divergent formal series. The relation between the obtained function and the original power series is an example of `asymptotic expansion of Gevrey type`. We shall also introduce the phenomenon for which J. Ecalle coined the name  `resurgence` at the beginning of the 1980s.

- - -

### Analytic Continuation and Monodromy

`Formal power series` is a generalization of normal power series, or polynomial, in the sense that we consider a power series of infinite order and don't care if it is convergent or not. Provided a ring $R$, consider the set of formal power series in $X$, denoted by $R[[X]]$, is another ring, in the same sense that all the polynomials over $R$ forms another ring (for example, multiply one polynomial to another gives as another polynomial). It is called the **ring of formal power series in the variable $X$ over $R$**.

We say a complex-valued function $f:\Omega \to \mathbb{C}$ is `analytic` if $f$ is represented by a convergent power series expansion on a neighborhood around every point $a\in\Omega$. 

We say a complex-valued function $f:\Omega \to \mathbb{C}$ is `holomorphic` iff it satisfied Cauchy-Riemann relation, which is equivalent to $\partial f/\partial \overline{z}=0$ . If we regard $z$ and $\overline{z}$ as independent variables, a holomorphic function $f$ is only a function of $z$ not $\overline{z}$.

A differential manifold is a topological space (given by closed sets and all that stuff) with differential structure, which practically means that you can find a way to do derivatives on the manifold. A n-Dimensional real (Complex) manifold is locally homeomorphic to $\mathbb{R}^N (\mathbb{C}^n)$, plus the condition that the transition from one chart (coordinate system) to another is `homeomorphic (holomorphic)` and vice versa.

An `open disk` of radius $r$ around $z_0$ is the set of points $z$ on $\mathbb{C}$ that satisfies
$$
|z-z_0| < r.
$$
A **open deleted disk of radius $r$ around $z_0$** is the set of points with
$$
0 < |z-z_0| < r.
$$
a deleted disk is also called a punctured disk.

A `complex atlas` on a 2-dimensional manifold is a set of holomorphically compatible charts which cover the manifold. Two complex charts $\mathfrak{U}$, $\mathfrak{U}'$ are said to be `analytically equivalent` if any atlas in $\mathfrak{U}$ is holomorphically compatible with any other atlas in $\mathfrak{U}'$.

By a `complex structure` on a manifold, we mean an equivalent class of analytically equivalent complex atlases on the manifold. If we give a manifold a complex atlas, then we have given it a complex structure.

A Riemann surface is a pair $(X,\Sigma)$ where $X$ is a connected 2-dimensional manifold and $\Sigma$ is a complex structure on $X$. The simplest Riemann surface is the complex plane itself.

- - -

- $\mathbb{C} P^n$ Model: The (n+1)-tuple $z = (z^0,\cdots,z^n)$ defines a vector in space $\mathbb{C}^{n+1}$. Define a equivalence relation $\sim$ between two vectors,
  $$
(u^0,\cdots,u^n) \sim (v^0,\cdots,v^n) \text{ if } \exists \lambda\neq 0 \in \mathbb{C} \text{ so that } \mathbf{u} = \lambda \mathbf{}{v}
$$
then
$$
\mathbb{C} P^{n} \equiv (\mathbb{C}^{n+1}-\{0\})/\sim,
$$
and the $n+1$ numbers are call \emph{homogeneous coordinates} and is denoted by $[z^0,\cdots,z^n]$. We can make one of them constantly equal to 1, then only the rest are really coordinates, it is called `inhomogeneous coordinates`.

`Meromouphic functions` are functions holomorphic except at poles. 

A `domain` in $\mathbb{C}$ is a connected non-empty open subset of $\mathbb{C}$.

- - -
**Riemann Sphere**

There are two ways to think of $\overline{C} \equiv \mathbb{C} \cup \{\infty\}$, i.e. the complex plane compactified, by adding a point called infinity, $\infty$ is not included in $\mathbb{C}$.

- complex projective plane $\mathbb{C}P^1$.
- a 2D sphere $\mathbb{S}^2$. The coordinates is given by the stereographic projection, except for the north pole $N$, $\pi : \mathbb{S}^2-\{N\} \to \mathbb{C}$.

The space $\overline{\mathbb{C}}$ has the structure of e Riemann surface and it is called the `Riemann sphere`. We can introduce two charts on the Riemann sphere,
$$
\mathfrak{U}_1 = \mathbb{C},\quad \mathfrak{U}_2 = \mathbb{C}^\ast \cup \{\infty\}
$$
where $\mathbb{C}^\ast$ is the punctured complex plane, $\mathbb{C}^\ast \equiv \mathbb{C} - \{0\}$. 

**Theorem.** A function is meromorphic on $\mathbb{C}$ iff its restriction on $\mathbb{C}$ is a rational function.

By the restriction of a function, we mean that to restrict the domain so that the it is well defined, no singularities. For example, the function $f:x\to 1/x$ has a singularity at $x=0$, then if we want something which is just like $f$ but has no singularity, we can just restrict the domain to $\mathbb{R} - \{0\}$, which is said to be a restriction of $f$.

A `germ` of functions at a point $\mathbb{C}$ is a set of function defined in the neighborhood of $a$ which all have the same Taylor expansion. A more mathematical definition is as following.

Use $\mathcal{O}(a)$ to denote the set of functions which are defined in a neighborhood of $a$ and is holomorphic at $a$. Define an equivalence relation $\sim$ so that if $f\sim g$ for $f,g \in \mathcal{O}(a)$, then $f,g$ are identical on some neighborhood of a. The equivalence class is called a germ of holomorphic functions at $a$.

Intuitively, the germ of a function tells us how a function behaves locally at point $a$.

- - -

The `Fundamental Uniqueness Theorem (FUT)` for holomorphic functions:

**Theorem.** If $f,g$ are holomorphic functions on a domain $D\in\mathbb{C}$ and $f \sim g$ for some point $a\in D$, namely f and g are in the same germ at a, then f is identical to g on $D$.

The germ of $f$ will be denoted by $\overline{f}$, if there is no ambiguity about around which point it is defined.

- - -

**Analytic Continuation, Monodromy**

First we introduce the analytic continuation in a different way, more formal and more mathematical. We begin by defining `pairs`. The idea is that, a function is not only defined by the values but also the domain on which it is defined.

A `pair` $(U,f)$ is a non-zero open disk $U\subset \mathbb{C}$ (why does it has to be open? I don't know.) and a function, holomorphic on $U$, such that the radius of $U$ is the maximum radius of convergence of the series expansion of $f$. The center of the pair is the center of $U$. Usually $U$ will stop at some singular point.

Another concept is adjacency, two pairs $(U,f)$ and $(V,g)$ are said to be `adjacent` if $U\cap V \neq 0$ and $f \equiv g$ on $U\cap V$.

If there is a `finite` sequence of pairs $(U_i,f_i),\quad i = 0,1,\cdots, n$ so that for all $i$, $(U_i,f_i)$ is adjacent to $(U_{i\pm 1},f_{i\pm 1})$, then $(U_0,f_0)$ is said to be the analytical continuation of $(U_n,f_n)$.

We can define a analytical continuation along a curve $\gamma: [0,1] \to \mathbb{C}$. The definition is kind of intuitive so I will skip it here. Now the question is, is the analytical continued function $(U_n,f_n)$ dependent on the path? The answer is the monodromy theorem:

**Theorem.** If the two path are homotopic, then the analytical continuation results to the same functions.

If in any doubt, just think of the $\ln{z}$ function.

- - -

**Linear Differential System**

A `linear system` is short for a complex linear ordinary differential system. A linear system of order p is a system with p first order ordinary differential equations.

$$
\frac{dy(x)}{dx} = A(x) y(x),\quad y(x) =
  \begin{pmatrix}
    y_1(x)\\
    \vdots \\
    y_p(x)
  \end{pmatrix}
$$
where $y(x)$ is a column vector of functions, and $A$ is the $p\times p$ coefficient matrix. The system is referred to as $(S)$. 

We used $\mathbb{C}(x)$ to denote the field of complex rational functions, and $\mathscr{M}(D)$ the field of meromorphic functions on domain $D$, and $\mathscr{O}(D)$ the ring of holomorphic functions on domain $D$.

A `fundamental solution` of $(S)$ is a $p\times p$ matrix whose columns are $\mathbb{C}$-linear independent solutions to $(S)$.

The `Wronskian` for $n$ functions are defined to be
$$
W(f_1,\cdots, f_n)(x) \equiv
  \begin{vmatrix}
    f_1(x) & \cdots & f_n(x)\\
    f'_1(x)& \cdots & f'_n(x)\\
    \cdots \\
    f^{(n-1)}(x) & \cdots & f^{(n-1)}(x)
  \end{vmatrix}.
$$

Let $\Sigma= \{ a_1,\cdots,a_n \}\subset \overline{\mathbb{C}}$ be the set of singular points of $(S)$. Let $U_\Sigma \equiv \overline{\mathbb{C}}\backslash \Sigma$.

Recall a nice property of Wronskian:
Let $\mathscr{D}$ a domain in $U_\Sigma$, $W$ a $p\times p$ solution of $(S)$, the following are equivalent:
- W is a fundamental solution of $(S)$
- $\det{W(x)}\neq 0$ for some $x \in \mathscr{D}$
- $\det{W(x)}\neq 0$ for all $x \in \mathscr{D}$

In other words, the Wronskian is either nonzero on the entire domain, or identically zero.

- - -

**Differential Galois Theory**

A `differential field` $(k,\partial)$ is a field $k$ with derivation.
A \hl{differential homomorphism} $\phi:(k_1,\partial)\to(k_2,\partial)$ from $k_1$ to $k_2$ is a field homomorphism that commutates with $\partial$. A triple $(k_1, \phi, k_2)$ is called a differential extension. $k_2$ is also called a differential extension of $k_1$.

A differential system
$$
  \partial  y = A y
$$
where $A$ is a $p \times p$ matrix.

