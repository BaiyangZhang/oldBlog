---
layout:     post   				    # 使用的布局（不需要改）
title:     What is a transseries? 			# 标题 
subtitle:   Some examples
date:       2023-07-05 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/background2.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - 
---

### Introduction

In history, formal power series are used extensively for finding the resolution of differential equations. If the resulting power series is convergent, it gives rise to a germ which can be analytically continued to (multi-valued) functions on a Riemann surface. However, very often, the power series we found from solving a differential equation is divergent, then it is not clear *a prior* how to attach reasonable sums to them.

The modern theory of `resummation` was developed systematically by Stieltjes, Borel and Hardy, who invented some resummation methods which *are stable under the common operators of analysis*. Later, Poincare established the equivalence between computations with formal power series and asymptotic expansions. Newton, Borel and Hardy were all aware of the systematic aspects of their theories and they consciously tried to complete their framework so as to capture as much of analysis as possible. The great unifying theory nevertheless had to wait until the late 20-th century and Ecalle’s work on transseries and Dulac’s conjecture. 

- - -

Define a ordered group ${\frak G}$ (frak G) of transmonomials. Define a differential field $\mathbb{T}$ of `transseries`. Transmonomials are generalizations of monomials in polynomials, by including exponential and logarithmic. In this note and that follows, we will consider the limit where $x\to \infty$. 

Let's start with exponents first.

**Log-free transmonomials.** They are of form 
$$
x^{b}e^{ L },\quad  b\in \mathbb{R},\; L \in \text{large log-free transseries.} 
$$

For example, the following are all log-free transmonomials,
$$
x^{-1},\; x^{\pi}x^{x^{\sqrt{ 2 }}-3x},\; e^{ \sum_ {i}x^{-1}e^{ x } },etc.
$$

The multiplication is defined in the obvious way. The group identity is just $1$. 

We define a binary relation $\gg$, read "far larger than". Keep in mind that we are assume $x\to \infty$. So how does this "far larger than" work? We compare the exponents $e^{ L }$ first, whichever with the largest exponent $L$ is far larger than others; if they have same exponents, then we compare the power of $x$, namely $x^{b}$, whichever with larger $b$ is far larger then others. To be specific,
$$
x^{b_ {1}}e^{ L_ {1} } \gg  x^{b_ {2}}e^{ L_ {2} }\quad  \text{ if } L_ {1} > L_ {2} \;\lor\; (L_ {1}=L_ {2}\;\land\; b_ {1}>b_ {2} ),
$$
where $\lor$ is logic or. For example, $x^{-5}\gg x^{20}e^{ -x }$ since $x^{-5}=x^{-5}e^{ 0 }$ and $0>-x$. 

**Log-free transseries.** A log-free transseries $T$ is a formal sum of log-free monomials ${\frak g}$,
$$
T = \sum_ {i} c_ {i} {\frak g}_ {i},\quad  c_ {i} \in \mathbb{R} .
$$
We require the order of transmonomials be such that, each ${\frak g_ {i}}$ is far smaller than all previous terms, namely they appear in descending orders. This is similar to the case of regular polynomials where we usually put the highest powers at first. 

The transseries $T$ is said to be `purely large` if all transmonomials ${\frak g}_ {i}$ are far larger than $1$ (not $0$), namely ${\frak g_ {i}}\gg_ {1} \;\forall i$. $T$ is said to be `small` if all ${\frak g}_ {i}\ll 1$. The largest (in the sense of far larger than) transmonomial is called the `dominant term`, let's call it $c_ {0}{\frak g}_ {0}$. If the dominant term has positive coefficients, $c_ {0}>0$, then $T$ is said to be positive. This enables us to compare the size of two transseries $S,T$, we say $S>T$ if $S-T>0$. So we just need to compare their dominant terms.

- - -

We consider only transmonomials and transseries of “finite exponential height”. For example, we don't want
$$
e^{ x^{x^{x\dots}} }.
$$

The `differentiation` of $T$ with respect to $x$ is defined the usual way. 

- - -

Next let's include logarithmic. $\log$ acting $m$ times is denoted $\log_ {m}x$, namely
$$
\log_ {m}x = \log \dots \log x,\quad  m\; \log .
$$

A general transseries is obtained by substitution of some $\log_ {m}x$ for $x$ in a log-free transseries. 

*Every nonzero transseries has a multiplicative inverse.* This is similar to formal power series. 

*A lot of functions can now be regarded as a transseries*. For example, e hyperbolic sine is a two-term transseries.

In the next note, we will talk about formal constructions of transseries. Then in the third, I will show some applications and close this topic. 





