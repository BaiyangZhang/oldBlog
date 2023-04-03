---
layout:     post   				    # 使用的布局（不需要改）
title:     Introduction to Resurgence and Transseries 			# 标题 
subtitle:   Lecture 2
date:       2023-04-01 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/mathArt1.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - PureMath
    - CategoryTheory
    - Notes
---

### An example by Poincare

To get some feeling about resurgence, let's start with an example first given by Poincare. This example shows **how an divergent series emerges from a function.** 

Fix $w\in \mathbb{C}$ and $\left\lvert w \right\rvert<1$. Consider the series of functions of the complex variable $t$,
$$
\phi_ {k}(t) := \frac{w^{k}}{1+kt},\quad  \phi(t):= \sum_ {k\geq 0} \phi_ {k}(t).
$$
This series is uniformly convergent on
$$
U:=C^{\ast } - \left\{ -1,-\frac{1}{2},-\frac{1}{3},\dots \right\} .
$$
Hence the sum $\phi$ is `holomorphic` in $U$. Actually $\phi$ is meromorphic on $\mathbb{C}^{\ast}$ (not on $\mathbb{C}$ since the origin would be a limiting point of the poles) with simple poles at $1 / \mathbb{N}$.

We now show how this function $\phi$ gives rise to a divergent formal series when $t$ approaches $0$. The idea is to expand each $\phi_ {k}$ first in terms of $t$. For each $k \in \mathbb{N}$, we have a *convergent* Taylor expansion at $t=0$,
$$
\phi_ {k}(t) = w^{k}\sum_ {n\geq 0}(-1)^{n}(kt)^{n}, \quad  \left\lvert t \right\rvert< \frac{1}{k} .
$$

One might be tempted to recombine the (convergent) Taylor expansion of $\phi_ {k}$ to give $\phi(t)$. It amounts to considering the well-defined **formal series**
$$
\tilde{\phi}(t) := \sum_ {n\geq 0}(-1)^{n} b_ {n} t^{n}, \quad b_ {n}:= \sum_ {k\geq 0}k^{n} w^{k}.
$$
We see that $b_ {n}$ is convergent since
$$
\lim_{ k \to \infty } \frac{(k+1)^{n}w^{k+1}}{k^{n}w^{k}} = w <1 \text{ by construction}.
$$

However, it turns out that **this formal series is divergent!**

To see this, make the substitution $w = e^{ s }$. Then, since $\text{Re }w <1$, we have 
$$
b_ {0}=(1-w)^{-1} = (1-e^{ s })^{-1}
$$
and
$$
b_ {n} = \left( w \frac{d}{dw}  \right)^{n}b_ {0} = \left( \frac{d}{ds} \right)^{n} b_ {0}.
$$
There is an easy way to tell if a series has non-zero radius of convergence, by some kind of a "dominance criterion". If the series of study $a_ {n}$ is dominated by $AB^{n}$ where $A,B$ are real and $A,B>0$, namely for all but finite $n$ we have $\left\lvert a_ {n} \right\rvert \leq AB^{n}$. Then the formal series 
$$
F(\xi) := \sum(-1)^{n} a_ {n} \frac{\xi^{n}}{n!}
$$
would have infinite radius of convergence. **$F$ can be seen as a map of the formal series to a function of $\xi$, note that we have inserted a factor of $1 / n!$ into the sum to make is more convergent**. In our case of $b_ {n}$, we see that 
$$
F(\xi) = \sum(-1)^{n} b_ {n} \frac{\xi^{n}}{n!} = \sum(-1)^{n} \frac{\xi^{n}}{n!}\left( \frac{d}{d s}  \right)^{n} b_ {0}(s) = b_ {0}(s-\xi) = \frac{1}{1-e^{ s-\xi }} .
$$
This functions has finite radius of convergence, since the last expression in the equation above diverges at $\xi=s+2\pi i \mathbb{Z}$. The radius of convergence is not infinite! Thus $\tilde{\phi}$ must have zero radius of convergence.

- - -

Now the question is to understand the relation between $\tilde{\phi}$ and $\phi$. We shall see in this note that the `Borel-Laplace` summation is a way of going from the divergent formal series $\tilde{\phi}$ to the finite function $\phi$. $\tilde{\phi}$ is actually the `asymptotic expansion` of $\phi(t)$  at $t=0$. We shall explain what it means next. 

We can already observe that the moduli of the coefficients $b_ {n}$ satisfy
$$
\left\lvert b_ {n} \right\rvert <AB^{n}  n! ,\quad  n \in \mathbb{N}
$$
for some $A,B>0$. Such inequalities are called `1-Gevrey estimates` for the formal series $\tilde{\phi}(t)=\sum b_ {n}t^{n}$. 

We remark that, since the original function $\phi(t)$ is not holomorphic (nor meromorphic) in any neighborhood of 0, because of the accumulation at the origin of the sequence of simple poles $- \frac{1}{k}$. Thus it would be very surprising to find a positive radius of convergence for $\tilde{\phi}$.

- - -

Resurgence theory can also be used to study power series of the form 
$$
\sum_ {i} \left( \sum_ {j} a_ {ij}t^{j} \right) e^{ -c_ {j} / t }
$$
note that the variable $t$ appears at two places, once in the series and once in the exponent. The exponent term is the small correction that is invisible to Taylor expansion at $t=0$, and the formal series in the parenthesis diverges. 

There are many examples of such series in physics. For example, the series could represent the solution of an ordinary differential equation, or the value of some integral, or the perturbative results. In the below is a list of where you might find series like this:
- Normal forms for dynamical systems 
- Gauge theory of singular connections
- Quantization of symplectic and Poisson manifolds
- Floer homology and Fukaya categories
- Knot invariants
- Wall-crossing and stability conditions in algebraic geometry
- Spectral networks
- WKB approximation in quantum mechanics
- Perturbative expansions in quantum field theory (QFT).

There has been some recent work in the physics literature suggesting the possibility that the divergent series obtained from the perturbative expansion may have more information about the true nature of the QFT that one might naively expect.

In the next note we will dive into the details of resurgence theory, beginning with the differential algebra $(\mathbb{C}[[1 / z]],\partial)$. 

