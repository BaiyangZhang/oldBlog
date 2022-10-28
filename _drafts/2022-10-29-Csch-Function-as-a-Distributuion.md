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
where we change the variable from $x$ to $z$ as a hint that the integral could be carried out on the complex plane. 

Let's try to calculate the first term in the last line using principal value method, then the contour integral.

- - -
### Principal value method

We want to evaluate
$$
\mathcal{F}\left\{ \frac{\sin z}{z} \right\} (\omega) =\text{Pv.} \int_{-\infty}^{\infty} dz \, \frac{\sin z}{z}e^{ -i\omega z },
$$It can be regarded as a distribution defined by $\frac{1}{x}$ acting on a regular function $\sin(z) e^{-i\omega z}$. Note that $\sin(z) e^{-i\omega z}$ is NOT Borel integrable since $\lvert  \sin(z) e^{-i\omega z} \rvert$ is not Borel integrable (for details refer to the notes on measure theory) but it doesn't matter to us. Not being Borel integrable only means that we need to be extra careful when applying, e.g., Fubini's theorem to the integral. 

The problem is that $\frac{1}{x}$ is not locally integrable, recall that a function is called locally integrable if, around every point in the domain, there is a neighborhood on which the function is integrable, which is clearly not the case for $\frac{1}{x}$ since it is not integrable in the neighborhood of $x=0$. 

We can simplify the above integral as follows,
$$
\mathcal{F}\left\{ \frac{\sin z}{z} \right\} (\omega) = \text{Pv.}\int_{-\infty}^{\infty} dz \, \frac{\sin z}{z} [\cos(\omega z)-i\sin(\omega z)] 
=\text{Pv.} \int_{-\infty}^{\infty} dz \, \frac{\sin z}{z} \cos(\omega z)
$$
since $\sin z / z$ is even, cosine is even and sine is odd. Then the Cauchy principal value is 
$$
\text{Pv.} \int_{-\infty}^{\infty} dz \, \frac{\sin z}{z} \cos(\omega z)
= \lim_{ \epsilon \to 0 } \left( \int_{-\infty}^{-\epsilon} +\int_{\epsilon}^{\infty} \right) dz \, \frac{\sin z}{z} \cos(\omega z) = 2 \lim_{ \epsilon \to 0 } \int_{\epsilon}^{\infty} \frac{\sin z}{z} \cos(\omega z),
$$
which can be calculated using Feynman's trick. This trick involved taking derivatives under the integral notation. It goes as follows.

We define a new integral with an extra parameter $\lambda$, 
$$
H(\lambda) = 2 \lim_{ \epsilon \to 0 } \int_{\epsilon}^{\infty} \frac{\sin z}{z} \cos(\omega z)e^{ -\lambda z },
$$
clearly $H(\lambda)$ goes to zero if $\lambda$ goes to infinity. We can not calculate $H(\lambda)$ directly but we can calculate the derivative of it with respect to $\lambda$, that is why we defined $H(\lambda)$ as we did. Writing $\cos x$ as $(e^{ ix }+e^{ -x }) / 2$
, we have
$$
H(\lambda) = 2 \lim_{ \epsilon \to 0 } \int_{\epsilon}^{\infty} \frac{\sin z}{z} \frac{1}{2}(e^{ i\omega z }+e^{ -i\omega z }) e^{ -\lambda z }:= H_{I}(\lambda) + H_{I I}(\lambda)
$$
where
$$
\begin{align}
H_{I}(\lambda) &= 2 \lim_{ \epsilon \to 0 } \int_{\epsilon}^{\infty} \frac{\sin z}{z} \frac{1}{2}e^{ i\omega z } e^{ -\lambda z }, \\
H_{I I}(\lambda) &= 2 \lim_{ \epsilon \to 0 } \int_{\epsilon}^{\infty} \frac{\sin z}{z} \frac{1}{2}e^{ -i\omega z } e^{ -\lambda z } = H_{I}(\lambda)^\ast. 
\end{align}
$$
Finally, let's take the derivative of $H(\lambda)$ w.r.t. $\lambda$, we obtain
$$
\begin{align}
\frac{d}{d \lambda}H(\lambda) &= 2 \frac{d}{d \lambda}  \lim_{ \epsilon \to 0 } \int_{\epsilon}^{\infty} \frac{\sin z}{z} \cos(\omega z)e^{ -\lambda z }  \\
&= 2  \lim_{ \epsilon \to 0 } \int_{\epsilon}^{\infty}\frac{d}{d \lambda}  \frac{\sin z}{z} \cos(\omega z)e^{ -\lambda z } \\ 
&= -2  \lim_{ \epsilon \to 0 } \int_{\epsilon}^{\infty} \sin z \cos(\omega z)e^{ -\lambda z } \\
&= -2  \lim_{ \epsilon \to 0 } \int_{\epsilon}^{\infty} \sin z \frac{1}{2}(e^{ i\omega z } + e^{ -i\omega z })e^{ -\lambda z } \\
&= -  \lim_{ \epsilon \to 0 } \int_{\epsilon}^{\infty} \sin z (e^{ i\omega z -\lambda z} + e^{ -i\omega z -\lambda z}).
\end{align}
$$
Writing
$$
\frac{d}{d \lambda}H(\lambda) = \frac{d}{d \lambda}H_{I}(\lambda) + \frac{d}{d \lambda}H_{I I}(\lambda),
$$
we just need to calculate one of them since they are complex conjugate to each other. Let's calculate $d H_{I} / d \lambda$, With the help of $\sin x = (e^{ ix } - e^{ -ix }) / 2i$, we have 
$$
\begin{align}
\frac{d}{d \lambda}H_{I}(\lambda) &= -\frac{1}{2} \lim_{ \epsilon \to 0 } \int_{\epsilon}^{\infty} dz \, \frac{1}{2i} (e^{ iz }-e^{ -iz })e^{ i\omega z }e^{ -\lambda z } \\
&= \frac{i}{4}  \lim_{ \epsilon \to 0 } \int_{\epsilon}^{\infty} dz \, 
 \left\{ e^{ z[i(\omega+1)-\lambda] } - e^{ z[i(\omega-1)-\lambda] } \right\}  \\
&=  \frac{i}{4}  \lim_{ \epsilon \to 0 }  
\left. \left( \frac{e^{ z[i(\omega+1)-\lambda] }}{i(\omega+1)-\lambda} - \frac{e^{ z[i(\omega-1)-\lambda] }}{i(\omega-1)-\lambda} \right) \right\rvert_{\epsilon}^\infty \\
&= -\frac{1}{2} \frac{1}{(i\omega-\lambda)^{2}+1},
\end{align}
$$
Note that we have taken the $\epsilon \to 0$ limit. What we want to know is the value of $H_{I}(\lambda=0)$, which can be obtained from the identity
$$
H_{I}(0) + \int_{0}^{\infty} d\lambda \, \frac{dH_{I}(\lambda)}{d\lambda} = H_{I}(\infty)=0.  
$$
However, here is where the troublesome begins, it is actually nontrivial to calculate the definite integral! I will just throw at your face the useful result,
$$
\int_{-\infty+i\omega}^{\infty+i\omega} \frac{ dz }{1+z^{2}}= 
\begin{cases}
0 & \lvert\text{Im}(z)\rvert>1, \\
\pi & \lvert\text{Im}(z)\rvert<1, \\
\frac{1}{2} & \lvert\text{Im}(z)\rvert=1.
\end{cases}
$$
To obtain this result we need to use the contour integral, then why don't we use the contour integral at the first place, right? It makes no sense... 

Anyway, we have already marched this far and for the sake of completement, let me just write down the result for $H_{I}(0)$. When $\left\lvert \omega \right\rvert<1$, we have 
$$
H_{I}(0) = \frac{\pi}{2} + \text{arctan}(i\omega) = \frac{\pi}{2} + \text{arctanh}(\omega).
$$
By substitute $\omega\to -\omega$ we have $H_{I I}$, putting them together we find the arctanh$(\omega)$ term cancels and we have 
$$
\mathcal{F}\left\{ \frac{\sin x}{x}(\omega) \right\} = \pi \text{  for  } \left\lvert \omega \right\rvert <1
$$
while 
$$
\mathcal{F}\left\{ \frac{\sin x}{x}(\omega) \right\} = 0 \text{  for  } \left\lvert \omega \right\rvert > 1
$$
and
$$
\mathcal{F}\left\{ \frac{\sin x}{x}(\omega) \right\} = \frac{1}{2} \text{  for  } \left\lvert \omega \right\rvert = 1.
$$
The last part is not important at all, since it is defined on $\omega = \pm 1$ which are just two points, they are $\mu$-negligible so don't contribute anything in the $\int d \omega$ integral.

- - -

### Contour integral method

Writing 
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


Using [Jordan's Lemma](https://mathworld.wolfram.com/JordansLemma.html).