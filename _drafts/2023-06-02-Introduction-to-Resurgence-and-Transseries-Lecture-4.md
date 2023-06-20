---
layout:     post   				    # 使用的布局（不需要改）
title:     Introduction to Resurgence and Transseries 4			# 标题 
subtitle:   The formal Borel transform and the space of 1-Gevrey formal series
date:       2023-06-02 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/mathArt2.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - PureMath
    - CategoryTheory
    - Notes
---

### Introduction

This part follows from a lecture by Maxim Kontsevich.

There are roughly speaking three perspectives of resurgence,
- Borel plane,
- Exponential integrals,
- Ray-crossing in the complex plane.

**Simple resurgence package.** Consists of 
1. A discrete subset of complex plane, $\left\{ z_ {\alpha} \right\}\in\mathbb{C}$, finite countable. 
2. Formal power series, 
3. A collection of integers $n_ {\alpha \beta}\in\mathbb{Z}$, called Stokes integers, usually anti-symmetric, $n_ {\alpha \beta}=-n_ {\beta \alpha}$.

There is an axiom. Consider function $\phi_ {\alpha}(\zeta)$, 
$$
\phi_ {\alpha}(\zeta) := \sum_ {k\geq 0} \frac{c_ {\alpha,k}}{k!} (\zeta-z_ {\alpha})^{k}.
$$
It is analytic germ at $z_ {\alpha}$, Meaning it converges at some small disk centered at $z_ {\alpha}$. This extends analytically to star-shaped domain 
$$
\mathbb{C} - \bigcup_ {\alpha \neq \beta} (z_ {\beta} + \mathbb{R}_ {+}(z_ {\beta}-z_ {\alpha})).
$$
This is hard to explain it with words but I am too lazy to draw a picture and include it to my note. The best way to describe it is to regard $z_ {\alpha}$ as the sun, radiating heat and light, and consider $z_ {\beta}$ as planets, all lying on the complex plane, then the star-shaped manifold is the area where the light from $z_ {\alpha}$ reaches. And we want to describe how the functions jumps at the ray of shades. 

The jumps are controlled by the numbers $n_ {\alpha \beta}$, in the following fashion. The function of interested $\phi_ {\alpha}$ is not holomorphic at $z_ {\beta}$'s, but it can be separated into holomorphic and singular part, roughly as 
$$
\phi_ {\alpha}(\zeta){\Large\mid}_ {z_ {\beta}}  = \text{holomorphic part} + \frac{n_ {\alpha \beta}}{2\pi i} \log(\zeta-z_ {\beta})\times \text{something}.
$$

- - -

A `formal series` is an infinite formal sum that is considered independently from any notion of *convergence*, and can be manipulated with the usual algebraic operations on series, such as addition, multiplication, division, partial sum, etc.

A `formal power series` is a special case of formal series, whose terms are of form $ax^{n}$ where $n\in\mathbb{Z}^{+}$ is the power of the variable $x$. $a$ is the coefficient of that term. They can be viewed as a generalization of polynomials, where the number of terms is allowed to be finite, with no requirement of convergence. One of the biggest difference between *formal* power series and power series is that the operation `evaluation` is not defined for formal power series but is for regular power series, which can thus be identified as a function, at least within the radius of convergence. In formal power series, in a term such as $a x^{5}$, $x^{5}$ is merely a position holder, used to tell the position of $a$ is a tuple of coefficients. 

It is the fact that we don't need to bother about convergence that made the ring of formal power series so useful in our discussion. Doing arithmetic is actually simpler with formal power series, since you can just pretend it is a power series without worrying about *absolute, conditional* and *uniform convergence*.

In the previous notes we have introduced the (complex) formal power series of $z^{-1}$ without constant term, denoted
$$
z^{-1}\mathbb{C}[[ z^{-1} ]].
$$

The `formal Borel transformation` is defined to be a linear map from $z^{-1}\mathbb{C}[[ z^{-1} ]]$ to $\mathbb{C}[[\zeta]]$ as 
$$
\mathcal{B}: \tilde{\phi} = \sum_ {0}^{\infty} a_ {n} z^{-n-1} \mapsto \hat{\phi} = \sum_ {0}^{\infty } \frac{a_ {n}}{n!} \zeta^{n}
$$

The reason for this definition is that we hope the introduction of extra $1 / n!$ factor in the coefficients can turn the original formal power series into a convergent power series, which we can then identify to a function. The change of variable from $z^{-1}$ to $\zeta$ seems out of nowhere, like, where does this $\xi$ came from? One way to explain it, without mathematical rigor but quite intuitive, is to say that it comes from writing the power of $z$ to the integral form, 
$$
x^{n+1} = \frac{1}{n!} \int_{0}^{\infty} d\xi \, \xi^{n} e^{ -\xi / x } , \quad  x=\frac{1}{z},
$$
which is a generalized form of the Euler integral. Substitute it to $\tilde{\phi}$ and re-arrange the order of integral and summation (which is not allowed! But we do it anyway) we find the mysterious $\xi$.

For the formal power series in $\mathbb{C}[[z^{-1}]]$ (note that we have put constant terms back in to make the case most general) which are actually convergent at infinity ($z\to \infty$) with positive radius of convergence, we denote the collection of them
$$
\mathbb{C}\left\{ z^{-1} \right\} 
$$
and the ones without constant terms are again denoted 
$$
z^{-1}\mathbb{C}\left\{ z^{-1} \right\} .
$$

**Lemma 1.** Let 
$$
\tilde{\phi}\in z^{-1}\mathbb{C}[[z^{-1}]],
$$
then 
$$
\tilde{\phi}\in z^{-1}\mathbb{C}\left\{ z^{-1} \right\} 
$$
iff its formal Borel transform 
$$
\hat{\phi}=\mathcal{B}\tilde{\phi}
$$
has infinite radius of convergence and defines an entire function (functions that are finite except at infinite points) of bounded exponential type, i.e. there exists $A,c>0$ such that 
$$
\left\lvert \hat{\phi}(\zeta) \right\rvert \leq A e^{ c\left\lvert \zeta \right\rvert  } \text{ for all } \zeta.
$$
**Proof.** Let 
$$
\tilde{\phi}=\sum_ {n\geq 0}a_ {n}z^{-n-1}.
$$
It is convergent iff there exists $A,c>0$  such that $\left\lvert a_ {n} \right\rvert\leq Ac^{n}$ for all $n\in\mathbb{N}$. If it is so, then
$$
a_ {n}\zeta^{n} / n! \leq  \frac{A}{n!} \left\lvert  c\zeta\right\rvert^{n}
$$
and the conclusion follows.

The converse can be proofed with the help of Cauchy inequality, which we will not list here.

