---
layout:     post   				    # 使用的布局（不需要改）
title:     Wigner-Weyl Calculus		# 标题 
subtitle:   
date:       2023-04-25 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/background17.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - Wigner-Weyl
---

*Disclaimer: Nothing in this note is original.*

The Hamiltonian formulation of classical mechanics live on `phase space`, the Lagrangian formulation live on configuration space. Geometrically, the phase space is a symplectic manifold of dimension $\mathbb{R}^{2d}$. The coordinates in the phase space are positions and conjugate momenta. Observables are given by functions on phase space. 

The time evolution is controlled by the `Hamiltonian` $H(p,x)$ through Hamilton's equation
$$
\dot{x}=\partial _ {p}H, \quad \dot{p}=-\partial _ {x}H
$$
and the `Poisson bracket` of two observables $A,B$ are defined to be
$$
\left\{ A,B \right\} :=\partial _ {p}A \times  \partial _ {x}B - (A\leftrightarrow B).
$$
Hamilton's equation can be written in terms of the Poisson bracket
$$
\dot{x}=\left\{ H,x \right\} ,\quad \dot{p}=\left\{ H,p \right\} 
$$
in fact for any observable the time evolution is given by 
$$
\dot{A} = \left\{ H,A \right\} .
$$

The time evolution in phase space can be regarded as a flow $\phi^{t}$ parametrized by time $t$, if the initial position is given by $p(0),x(0)$ the the flow is denoted by $\phi^{t}(p_ {0},x_ {0})$ where $p_ {0}:=p(0)$. It is indeed a flow since $\phi^{t}$ form a one-parameter group. 

- - -

### Weyl quantization

The question we wanna ask is, given a classical observable as a function of $x$ and $p$, how can be get the quantized version of it? We know how to quantize $x$ and $p$, by making then into operator $\hat{x},\hat{p}$ which satisfy the commutation relation $[\hat{x},\hat{p}]=i$. We have chosen the natural units. What about a general operator $A(x,p)$ then? Since now $\hat{x},\hat{p}$ are not commutative anymore, we need to be careful about the ordering when quantizing $A(x,p)$. A possible (good) choice is to take symmetrised products of $\hat{x}$ and $\hat{p}$, 
$$
xp \to \frac{1}{2} (\hat{x}\hat{p}+\hat{p}\hat{x}),
\tag{1}
$$
this is called the `Weyl ordering`.

In the following we will only consider 1-dimensional case, as it can be trivially generalized to arbitrary dimension $d$. 

Let $A(x)$ be a **classical operator** depending on $x$ alone, not on $p$. The motivation is that, we can use a somehow weird form of "$\delta$ function" to replace $x$ with $\hat{x}$, if we define something like $\delta(x-\hat{x})$, and integrate over $x$,
$$
\hat{A}(\hat{x}) := \int dx \, \delta(x-\hat{x})A(x).
$$
But what is this delta function between a c-number and a q-number? To make sense of it, we further write it using the Fourier transform,
$$
\delta(x-\hat{x}) = \int \frac{dp}{2\pi} \, e^{ ip(x-\hat{x}) } 
$$
and 
$$
\hat{A} := \frac{1}{2\pi}\int dx dp \,   e^{ ip(x-\hat{x}) } A(x),
$$
here the operator $\hat{x}$ appears in the exponent and in principal we know how to deal with it, for example with the help of Baker-Campbell-Hausdorff formula. 

If the operator depends on both $x$ and $p$, we can introduce another "delta function", bring the operator $\hat{p}$ to the exponent using a Fourier transform. As a possible choice, we **define** the two "delta functions" together are like
$$
\delta(x-\hat{x})\delta(p-\hat{p}) := \int \frac{d\xi}{2\pi} \frac{dy}{2\pi} \,  e^{ iy(p-\hat{p})+i\xi(x-\hat{x}) }.
$$
Note that this is just one of many possible definitions, it is by no means determined from the first principals. 

For future convenience, let's define an operation $\text{Op}$
$$
\hat{A} := \text{Op}[A(x,p)] := \int \frac{d\xi}{2\pi} \frac{dy}{2\pi} dx dp \,  e^{ iy(p-\hat{p})+i\xi(x-\hat{x}) } A(x,p).
$$
The integral over $\xi$ and $y$ are not surprising, however the integral over $p$ and $x$ could appear unexpected to people who see it for the first time. To rewrite the definition of $\text{Op}$ in a more comfortable (for myself) form where $dp$ is always divided by $2\pi$, I prefer  
$$
\hat{A} := \text{Op}[A(x,p)] := \int \frac{d\xi}{2\pi} \frac{dp}{2\pi} dx dy \,  e^{ iy(p-\hat{p})+i\xi(x-\hat{x}) } A(x,p).
$$
The legitimacy of this choice mostly come from the fact that it agrees with the Weyl ordering in Eq. (1). To see that, just apply it to $xp$ and you'll see that they indeed agree to each other. 

This is called the` Weyl quantization`. $A(p,x)$ is called the `Weyl symbol` of quantum operator $\hat{A}$.

To fully understand the physical meaning of the symbol, we go to the Schrodinger representation and see what the symbol does to wave functions. Notice that 
$$
\left\langle z \middle\vert  e^{ i\xi \hat{x} }\psi \right\rangle = \psi(i\xi z)
$$
and 
$$
\left\langle z \middle\vert e^{ iyp } \right\rangle =\psi(z-y)
$$
we can calculate (though the calculation is long and tedious) $\left\langle z \middle\vert \hat{A}\psi \right\rangle$, eventually we could get rid of the hatted operators in the exponent and arrive at 
$$
\boxed { 
\left\langle z \middle\vert \hat{A}\psi \right\rangle =\int \frac{dp}{2\pi}dy \, A\left( p,\frac{z+x}{2} \right)  e^{ ip(z-x) } \psi(x)
} 
$$
which is usually referred to as the definition of `Weyl quantization`.