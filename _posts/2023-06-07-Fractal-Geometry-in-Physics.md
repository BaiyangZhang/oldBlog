---
layout:     post   				    # 使用的布局（不需要改）
title:     Fractal Geometry in Physics 			# 标题 
subtitle:   Basied on a 2000 paper by H. KroKger
date:       2023-06-07 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/background5.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - 
---

### Introduction

A fractal is defined as an object with two properties: 
1. self-similarity;
2. its fractal dimension being different from its topological dimension. 

In the theory of phase transition we have two notions quite similar to it:
1. the system is scale-invariant at the critical point;
2. there exists non-integer critical exponents at the critical point.

Two examples of fractals are 
1. Koch's curve, obtained from a segment of a straight line, by repeating a pattern that gives the line an angle, see the figure below. It is self-similar by construction, the length goes to infinity by a power law as $n\to \infty$.
![KochCurve](/img/KochCcurve.png)

2. Another example is the coastal line of England, whose length $L(\epsilon)$ depends on the length $\epsilon$ of the yardstick, assumed to have the power law form,
$$
L(\epsilon)\sim ~L_ {0}\epsilon^{-\alpha}.
$$
The power-law behavior reminds us with the critical exponents near the critical point, for example the magnetization of a ferromagnet near the critical temperature. The fractal dimension $d_ {\text{frac}}$ of the coastal line is defined to be 
$$
\alpha=d_ {\text{frac}}-d_ {\text{top}}
$$
where $d_ {\text{top}}$ is the topological dimension of the coastal line which is $1$. If the measured length does not dependent on the length of the yardstick $\epsilon$, then $\alpha=0$ and $d_ {\text{frac}}=d_ {\text{top}}$. In our case we have roughly (by actual measurement)
$$
d_ {\text{frac}}\sim 1.25.
$$

- - -

How should we think of the dimension of a fractal? Consider some regular geometric object, such as a regular two dimensional square $\square$. If we double the size of it, its area is multiplied by $2^{d}$ where $d$ is the dimension. In general, if the size of an object is multiplied by a factor $\lambda$, its area, or length, or whatever quantity that measures the "content" of the object, should be multiplied by a factor $\lambda^{d}$, where $d$ can be regarded as (one of the many) definitions of dimension.

Let's try to apply this definition to Koch's curve. It is self-similar, if we shrink it by a factor of $3$, then it reduces to one of its four "components". This component should have length that is one quarter of the original one. In other words, if we multiply Koch's curve by factor $\lambda=\frac{1}{3}$, then the length should be multiplied by $\frac{1}{4}$, the before-mentioned definition of dimension should give
$$
\text{new length}=\text{new size}^{d}\implies \frac{1}{4}=\left( \frac{1}{3} \right)^{d}\implies d\sim 1.26.
$$

It is very closed to the fractal dimension of the coastal line of England, is it a coincidence? Plus, I don't see the connection between above definition of dimension and the dimension given for the coastal line of England. In the case of Koch's curve, if we assume that each iteration requires a finer ruler to measure the total length, since a rule must be able to see all the zig-zags. We can set the needed ruler's length to be the length of the shortest line segment in the Koch's curve. Then the ruler's length decrease to $\epsilon=\frac{1}{3^{n}}L_ {0}$ in the n-th iteration, where $L_ {0}$ is the original length. Then the total length of the curve approaches infinity not according to the power law, but rather
$$
L(\epsilon) \sim \left( \frac{4}{3} \right)^{-\ln\epsilon},\quad  \epsilon\to 0.
$$

Clearly something is off here.

- - -

There exists various different definitions of dimension of a fractal, and applied on the same set they give different results. However, when applied on a perfectly self-similar fractal, such as the Koch's curve, they should all give the same result.

The fractal dimension is used to quantify this roughness and complexity. The higher the dimension, the higher the roughness, the higher the complexity. 

- - -

### Brownian motion

It seems that, in Brownian motion, the momentum change of a molecule at a collision depends only upon the last collision. It is a Gaussian stochastic process. 

Consider a lattice in $D$ dimension, with space and time discretization $\Delta x$ and $\Delta t$. Supposed the molecule of study can only hop from one site to the neighbor site, with direction chosen at random. One can then ask for the probability
$$
P(x_ {1},t_ {1};x_ {0},t_ {0}) = \text{molecure move from }(x_ {0},t_ {0}) \text{ to } (x_ {1},t_ {1}).
$$
The probability should satisfy three conditions,
1. If $t_ {0}=t_ {1}$ then the particle does not move, $P=\delta(x_ {0},x_ {1})$.
2. The total probability is normalized to one.
3. At successive times, it can arrive only from neighbor sites.

The last conditions gives us the dynamics of the particle, it tells how the particle must move. Using the discretized Laplace operator, we can turn the last condition into an equation. Then we can go to the continuum limit by setting $\Delta t\to 0$ and $\Delta x\to 0$. This limit is well defined under the condition that $\Delta t \propto (\Delta x)^{2}$. 

It shouldn't surprise us that at the continuum limit, the probability distribution adopt a Gaussian form.

The probability naturally satisfies the so-called `Kolmogorov equation`, 
$$
\int d^{d}x_ {1} \,  P(x_ {2},t_ {2};x_ {1},t_ {1})P(x_ {1},t_ {1};x_ {0},t_ {0})=P(x_ {2},t_ {2};x_ {0},t_ {0}).
$$
**This will give us a path-integral interpretation of the probability.**

