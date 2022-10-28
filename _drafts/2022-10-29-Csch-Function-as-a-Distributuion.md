---
layout:     post   				    # 使用的布局（不需要改）
title:      Csch Function as a Distributuion 				# 标题 
subtitle:    #副标题
date:       2022-10-29 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/functionalAnalysis.png 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - math
    - functionalAnalysis
    - distribution
    - measureTheory
---


## $\frac{\sin x}{x}$ as a distribution

Sinc function, or sine cardinal function, also called the sampling function, is an important function in physics and engineering.  There are more than one definitions in common use, here we will adopt 
$$
\text{sinc}(x) = 
\begin{cases}
1  &  x=0 \\
\frac{\sin x}{x}  & x\in \mathbb{R}^\ast 
\end{cases}
$$
where $\mathbb{R}^\ast := \mathbb{R} \backslash \{ 0 \}$. Thanks to the insertion $1$ at $x=1$, sinc function is continuous and smooth on $\mathbb{R}$. 

The sinc function, like almost any other functions, defines a distribution, let's denote it by $T_{\text{sinc}}$. When acted on a function $f$ we have 
$$
\left\langle T_{\text{sinc}},f \right\rangle := \int_{-\infty}^\infty dx \, \text{sinc} (x)f(x)
$$
Everything is well defined. 

But what about $\frac{\sin x}{x}$ without putting by hand the value $1$ at $x=0$? The function is not defined at $x=0$ so when integrated against some function $f$ we should find a way to circumvent the origin. There are in general two ways to do that, first is by the principal value,
$$
\left\langle \frac{\sin x}{x},f(x) \right\rangle := \text{Pv.}\int_{-\infty}^{\infty} dx \, \frac{\sin x}{x}f(x) :=\lim_{ \epsilon \to 0 } \left( \int_{-\infty}^{\epsilon} +\int_{\epsilon}^{\infty}  \right)dx  \,   \frac{\sin x}{x}f(x).
$$
The other way is to adopt contour integral, the integration goes from $-\infty$ to $\rho$ which is infinitesimal, goes a half-circle above the origin, then goes from $\rho$ to $\infty$. Suppose the integral is zero on the upper infinite half-circle, then we can form a closed loop and the residual theorem can be applied. The contour is shown in the figure below.
![contour](img/contour.png)

Next we shall calculate the Fourier transform of $\sin x / x$ as an example of the two prescriptions. The Fourier transform is 
$$
\mathcal{F}\left\{ \frac{\sin z}{z} \right\} (\omega) = \int_{-\infty}^{\infty} dz \, \frac{\sin z}{z}e^{ -i\omega z },
$$
where we change the variable from $x$ to $z$ as a hint that the integral in carried out on the complex plane. Writing 
$$
\sin z = \frac{1}{2i} (e^{ iz }-e^{ -iz }), 
$$
we have 
$$
\begin{align}
\mathcal{F}\left\{ \frac{\sin z}{z} \right\} (\omega) &=  
\int_{-\infty}^{\infty} dz \, \frac{e^{ iz }-e^{ -iz }}{2iz}e^{ -i\omega z }  \\
&= \int_{-\infty}^{\infty} dz \, \frac{1}{2iz}e^{ -i(\omega-1) z} -\int_{-\infty}^{\infty} dz \, \frac{1}{2iz}e^{ -i(\omega+1) z}. 
\end{align}
$$
Let's try to calculate the first term in the last line using principal value method, then the contour integral.

- - -
### Principal value method

We want to evaluate
$$
\int_{-\infty}^{\infty} dz \, \frac{1}{2iz}e^{ -i(\omega-1) z},
$$
It can be regarded as a distribution defined by $\frac{1}{x}$ acting on a regular function $e^{ -i(\omega-1)z }$. Note that $e^{ -i(\omega-1)z }$ is NOT Borel integrable since $\lvert e^{ -i(\omega-1)z }\rvert=1$ is not Borel integrable (for details refer to the notes on measure theory) but it doesn't matter to us, not being Borel integrable only means that we need to be extra careful when applying, e.g., Fubini's theorem to the integral. 

The problem is that $\frac{1}{x}$ is not locally integrable, recall that a function is called locally integrable if, around every point in the domain, there is a neighborhood on which the function is integrable, which is clearly not the case for $\frac{1}{x}$ since it is not integrable in the neighborhood of $x=0$. 

the integral into
$$
\begin{align}
\text{Pv.}\int_{-\infty}^{\infty} dz \, \frac{1}{2iz}e^{ -i(\omega-1) z} &=\frac{1}{2i} \lim_{ \epsilon \to 0 } \int_{-\infty}^{\epsilon} dz \,  \frac{e^{ -i(\omega-1)z }}{z} + \frac{1}{2i} \lim_{ \epsilon \to 0 } \int_{\epsilon}^{\infty} dz \,  \frac{e^{ -i(\omega-1)z }}{z},
\end{align}
$$
on the RHS each integral blows up near $z=0$ but with different signs so they actually cancel each other. To 


Using [Jordan's Lemma](https://mathworld.wolfram.com/JordansLemma.html).