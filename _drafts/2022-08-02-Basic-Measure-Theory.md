---
layout:     post   				    # 使用的布局（不需要改）
title:      Basic Measure Theory 				# 标题 
subtitle:    #副标题
date:       2022-08-02 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/functionalAnalysis.png 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - math
    - functionalAnalysis
    - distribution
    - measureTheory
---

### Pointwise Convergence vs. Uniform Convergence

At the end of the 19th century, mathematicians extensively discussed weather you could take the limit out of the integral (Riemannian integral, to be exact), namely weather we have 
$$
\int_{-\infty}^{\infty} \lim_{ n \to \infty } f_{n}(x) \, dx 
=\lim_{ n \to \infty } \int_{-\infty}^{\infty} f_{n}(x) \, dx.
$$

Here $f_{n}$ is a **nonuniformly** convergent sequence of functions which are Riemann-integrable. Recall the meaning of uniformly convergence,

**Definition.** A sequence of functions $\left\{ f_{n}(x) \right\}$ is said to converge uniformly to $f$ on a set $S$ if for every $\epsilon > 0$ there exists an N such that for all $n>N$ we have 
$$
\text{sup}\left| f_{n}(x) - f(x) \right| < \epsilon \, \text{ for all } x\in S, 
$$

where sup is the supremum. Uniform convergence means that for a given $\epsilon$, one $N$ works for every $x$. You can regard $\left| f_{n}(x) - f(x) \right|$ as a set where each element is given by different $x$, then sup$\left| f_{n}(x) - f(x) \right|$ is the supremum of this set. 

*Uniform convergence* is in contrast to *pointwise convergence*. Pointwise convergence means that  $\lim_{ n \to \infty } f_{n}(x) = f(x)$ for every $x$ in the domain of $f$. Note that, this limit process is defined at each point, namely for every $x$, there exists $N(x)$ which depends on $x$, such that $\left| f_{n} - f \right|,\,n>N$ is smaller than a given $\epsilon$. This is different from the uniform convergence, where the $N$ is independent of $x$, once $N$ is given it must apply for all $x$ in the domain. 

Uniform convergence is a stronger condition than pointwise convergence, especially that uniform convergence preserves the **continuity**,

**Theorem** If the functions $f_{n}$ are continuous and they uniformly converges to $f(x)$, namely 
$$
\lim_{ n \to \infty } \text{sup} \left| f_{n}(x) - f(x) \right| = 0,
$$

Then $f(x)$ is also continuous on the domain.

Interested readers may find the proof somewhere else, but note that the proof uses the key important property that $N$ in the $\epsilon-N$ language is independent of $x$. 

On the other hand, pointwise convergence does not preserve continuity. We will give an example that is pointwise convergent (which is the weaker condition) but not uniformly convergent (which is the stronger condition). 

Consider function
$$f_{n}(x) : x \mapsto x^n$$

defined on $[0,1)$ . Since as long as $x<1$, there exists $N$ such that $x^n < \epsilon$, $f_{n}$ pointwise converges to step function $x \mapsto 0$ on $[0,1)$ and $f(1) = 1$. However, we know that that can't be the case for uniform convergence since $f_{n}(x)$ is continuous on $[0,1]$ but the step function is not, and uniform convergence must preserve the continuity. Indeed, given $N\in \mathbb{N}$, no matter how large it is, there exists $\delta$ small enough such that $(1-\delta)^N = f_{N}(1-\delta)$ is some value between 0 and 1. So, the set made by $f_{N}(x) - 0$ on $[0,1)$, namely $\{ f_{N}(x) - 0 \mid x \in [0,1)  \}$ is $[0,1)$ and the supremum of it is not zero everywhere, hence there is no uniform convergence. 

Anyway, after some close analysis of integrals, Lebesgue and others came up with their theory of integration. Lebesgue's integration is more general and better adapt to deal with limit processes.

The concept of **measure** plays a crucial role in Lebesgue's definition of the integral. A measure is a generalization of the concept of length, and there are more than one way to define measure, they all need to satisfy certain conditions, the so-called $\sigma$-algebra.

### Measure Functions