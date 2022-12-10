---
layout:     post   				    # 使用的布局（不需要改）
title:      Basics of Distributions 				# 标题 
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


## Distributions against Test function in $l^n$ and $L^n$


Classically, function are defined set-theoretically, I quote from Wiki:

>In mathematics, a function from a set X to a set Y assigns to each element of X exactly one element of Y. The set X is called the domain of the function and the set Y is called the codomain of the function. Functions were originally the idealization of how a varying quantity depends on another quantity. For example, the position of a planet is a function of time. Historically, the concept was elaborated with the infinitesimal calculus at the end of the 17th century, and, until the 19th century, the functions that were considered were differentiable (that is, they had a high degree of regularity). The concept of a function was formalized at the end of the 19th century in terms of set theory, and this greatly enlarged the domains of application of the concept.
>
>A function is most often denoted by letters such as $f$, $g$ and $h$, and the value of a function f at an element $x$ of its domain is denoted by $f(x)$; the numerical value resulting from the function evaluation at a particular input value is denoted by replacing $x$ with this value; for example, the value of $f$ at $x = 4$ is denoted by $f(4)$. When the function is not named and is represented by an expression $E$, the value of the function at, say, $x = 4$ may be denoted by $E\rvert_x=4$. For example, the value at $4$ of the function that maps $x$ to $(x+1)^{2}$ may be denoted by $\left.(x+1)^{2}\right\rvert _{x=4}$ (which results in 25).
>
>A function is uniquely represented by the set of all pairs (x, f (x)), called the *graph* of the function, a popular means of illustrating the function. When the domain and the codomain are sets of real numbers, each such pair may be thought of as the Cartesian coordinates of a point in the plane.

The most important operation for a function is *evaluation*.

Two evaluations are not defined for test functions in $L^2(\Omega)$. First is the evaluation. *Evaluation is not important for test functions*! Second is the *point-wise operations between two functions*, such as point-wise multiplication or division or additions or subtraction, precisely because evaluation is not defined!

There are various kinds of functions, they could be very smooth hence quite special, or very general but don't have any of the nice properties such as smoothness or continuity.

So what is Dirac $\delta$ function? It's better to consider it as an abstract things that, when given a function, it spits out a real or complex number.

First explain the name, why are they called distributions. Then introduce it as the dual space of test functions. 

Distributions can also be treated as the weak limit of functions. Explain what is weak limit and strong limit in a vector space. Example 1, $\sin(nx)$ on $[0,2\pi]$ weakly converges to $0$. In this sense, the inner product is degenerate, it's not a pseudo-Riemann space.

## Differentiation

A function being locally integrable doesn't guarantee that it is differentiable at all points, sometimes it is not differentiable at all. On the contrary, a distribution is always differentiable by construction, and its derivative is a distribution. 

The definition is suggested by the integral by part of two differentiable function, let $f$ be a locally integrable function which is differentiable everywhere, let $\phi$ be a test function, an integration by part yields
$$
\int dx \, f'(x)\phi(x) = - \int dx \, f(x)\phi'(x).  
$$
The differentiation of distribution is defined similarly.

**Definition** Let $T$ be a distribution, its derivative $T'$ is the distribution defined by 
$$
\left\langle T',\phi \right\rangle := \left\langle T,-\phi' \right\rangle.
$$
In the sense of distributions this definition is unique except for on $\mu$-negligible sets, which is irrelevant anyway when talking about integrations.

The following properties follow that from differentiable function,
$$
\frac{ \partial^{2} T }{ \partial x_{i} \partial x_{j} }  = \frac{ \partial^{2} T }{ \partial x_{j} \partial x{i} }.
$$

**Example** Let $\psi$ be an infinitely differentiable function and also the distribution defined by the function $\psi$, we have 
$$
(\psi T)' = \psi'T + \psi T',
$$
Interested readers can try to prove it by yourself. 

**Example** Let $\theta$ be the Heaviside step function, defined by 
$$
\theta(x) = 
\begin{cases}
0 & x<0 \\
1 & x\geq 0
\end{cases}
$$
then it defines a regular distribution $T_{\theta}$, whose action on a function is
$$
\left\langle T_{\theta},\phi \right\rangle  = \int_{0}^{\infty} dx \, \theta(x)\phi(x).
$$
What's the derivative of $\theta$ then? We know from textbooks that its derivative is Dirac-$\delta$ function, but it has always been a little fishy to me, since the step function is not even continuous at $x=0$, let alone differentiable. It feels much better to treat the step function as a distribution. By definition we have
$$
\left\langle \partial_{x}T_{\theta},\phi \right\rangle =-\left\langle T_{\theta},\partial_{x}\phi  \right\rangle = - \int_{-\infty}^{\infty} dx \, \theta(x)\partial_{x}\phi = - \int_{0}^{\infty}  \,  d\phi(x)= \phi(0)
$$
for all test functions $\phi$, hence
$$
\frac{d}{dx} T_\theta(x) = \delta(x).
$$
Similarly, we can prove that 
$$
  \frac{d^{2}}{d\theta^{2}}T_{\theta} = \delta'(x) = -\delta(x)\frac{d}{dx} \bullet 
$$
where the bullet is a place holder to be replaced by whatever is been acted on.

- - -

Bellow we give an example for the application of derivative of distributions. Consider function $x\mapsto \ln \left\lvert {x} \right\rvert$, it is locally integrable (note that $\int_{0} dx \, \ln x$ is finite). This function defines a regular distribution and its derivative must be a distribution as well, but what exactly is it? Let us act its derivative on a test function, following the definition we have
$$
\left\langle (\ln \left\lvert {x} \right\rvert)' , \phi(x) \right\rangle  
= -\left\langle \ln \left\lvert {x} \right\rvert ,\phi'(x) \right\rangle 
= -\int_{-\infty}^{\infty} dx \,  \ln \left\lvert {x} \right\rvert \phi'(x),
$$
Here we can not use the integrate by part trick since $\ln'x = \frac{1}{x}$ is not locally integrable. It shows that although $\ln \left\lvert {x} \right\rvert$ is a regular distribution, its derivative is not. To repeat, the derivative of a regular distribution

To find the derivative of $\ln \left\lvert {x} \right\rvert$ we shall use a technique due to Hadamard, which is widely used for singular distributions given by function that are not locally integrable. Given a divergent integral, the idea is to extract the finite part of this integral to define a singular distribution. 

First we write
$$
\int dx \, \ln \left\lvert {x} \right\rvert \phi'(x) = \lim_{ \epsilon \to 0 } \int_{\left\lvert {x} \right\rvert \geq \epsilon} dx \, \ln \left\lvert {x} \right\rvert \phi'(x),
$$
for readers who are after mathematical rigor, above relation holds due to Lebesgue's dominated convergence theorem. 
$$
\int_{\left\lvert {x} \right\rvert \geq \epsilon} dx \, \ln \left\lvert {x} \right\rvert \phi'(x) = \int_{-\infty}^{-\epsilon} dx \, \ln \left\lvert {x} \right\rvert \phi'(x)
+\int_{\epsilon}^\infty dx \, \ln \left\lvert {x} \right\rvert \phi'(x),
$$
now we can integrate by part, for instance
$$
\int_ {\epsilon}^\infty dx \, \ln \left\lvert {x} \right\rvert \phi'(x) = - \int_ {\epsilon}^\infty dx \, \ln' \left\lvert {x} \right\rvert \phi(x)+\ln(\epsilon)\phi(\epsilon),
$$
we have 
$$
\begin{align}
\left\langle (\ln \left\lvert {x} \right\rvert)' , \phi(x) \right\rangle  
&= \ln(\epsilon)(\phi(\epsilon)-\phi(-\epsilon)) - \left( \int_{-\infty}^{-\epsilon} dx \, \ln' \left\lvert {x} \right\rvert \phi(x)+\int_{\epsilon}^\infty dx \, \ln' \left\lvert {x} \right\rvert \phi(x) \right) \\
&= \ln(\epsilon)(\phi(\epsilon)-\phi(-\epsilon)) - \left( \int_{-\infty}^{-\epsilon} dx \, \frac{\phi(x)}{x}+\int_{\epsilon}^\infty dx \, \frac{\phi(x)}{x} \right) 
\end{align}
$$
where the limit $\epsilon\to 0$ is understood. Since $\phi$ is continuous at $x=0$, we have 
$$
\lim_{ \epsilon \to 0 } \,\ln(\epsilon)[\phi(\epsilon)-\phi(-\epsilon)] = 0
$$
since $\phi(\epsilon)-\phi(-\epsilon)$ is of order $\mathcal{O}(\epsilon)$. We have eliminated the divergent part! 

Finally we have 
$$
\left\langle (\ln \left\lvert {x} \right\rvert)' , \phi(x) \right\rangle   = \lim_{ \epsilon \to 0 } \int_{\left\lvert {x} \right\rvert \geq\epsilon} dx \, \frac{1}{x }\phi(x) = \text{Pv.}\int_{-\infty}^{\infty} dx \, \frac{1}{x}\phi(x),
$$
where the symbol $\text{Pv.}$ denotes the Cauchy principal value. This result is usually written as 
$$
\boxed{
\frac{d}{dx} \ln \left\lvert {x} \right\rvert  = \text{Pv.} \frac{1}{x}
}.
$$
or
$$
\frac{d}{dx} \ln \left\lvert {x} \right\rvert  = \text{Pf.} \frac{1}{x}
$$
where the symbol $\text{Pf}$ is read pseudofunction. Note that $\text{Pv.} \frac{1}{x}$ is NOT a regular distribution, instead a singular distribution. It is called a singular distribution because it can't just integrating a function against some test function, but some extra operations needs done, like taking the Cauchy principal value. Next we will meet more singular distributions. 

**Example.** Recall that the principal branch of the logarithm function is defined to be 
$$
\ln z = \ln \left\lvert {z} \right\rvert +i \text{ arg}(z), \quad \text{arg}(z)\in(-\pi,\pi)
$$
Apply this to $\ln(x+i\epsilon)$, from now on $\epsilon$ will be assumed to be infinitesimal unless said otherwise, we have 
$$
\ln(x+i\epsilon) = 
\begin{cases}
\ln(x)+i\pi & x<0 \\
\ln(-x)+0  & x\geq0
\end{cases}
= \ln(\left\lvert {x} \right\rvert ) + i\pi \theta(-x), \quad x\in \mathbb{R}.
$$
What about $d \ln(x+i\epsilon) / dx$? Compare to $d\ln(\left\lvert {x} \right\rvert) / dx$, there is a new term, 
$$
\frac{d}{dx} i\pi \theta(-x) = -i\pi \delta(x).
$$
This suggests that, the derivative of $\ln(x+i\epsilon)$ defines a singular distribution which is 
$$
\boxed{
\frac{d}{dx}\ln(x+i\epsilon) = \ln \left\lvert {x} \right\rvert -i\pi \delta(x) 
}.
$$
If you want, you can follow the procedure as before and arrive at the same conclusion. 

Changing $i$ in $-i$, we have 
$$
\boxed{
\frac{d}{dx}\ln(x-i\epsilon) = \ln \left\lvert {x} \right\rvert +i\pi \delta(x) 
}.
$$

We know that $\frac{1}{x}$ is not locally integrable, however $\theta(x) x^{\alpha}, -1<\alpha<0$ is. It defines a regular distribution denoted $x^\alpha_{+}$. The derivative of $x_{+}^\alpha$ is $x_{+}^{\alpha-1}$, which in general diverges when integrated against a test function. Nevertheless it defines a singular distribution. To determine this derivative we shall proceed as in the previous examples, write
$$
\begin{align}
\left\langle \frac{d}{dx} (x_{+}^\alpha), \phi \right\rangle &= \int_{-\infty}^{\infty} dx \, \left( \frac{d}{dx}   x_{+}^\alpha \right) \phi(x) \\
&= - \int_{0}^{\infty} dx \,  x^\alpha \frac{d}{dx} \phi(x)  \\
&= -\lim_{ \epsilon \to 0 } \int_{\epsilon}^{\infty} dx \,  x^\alpha \frac{d}{dx} \phi(x),
\end{align}
$$
Note that by changing the integral domain we got rid of the plus sign in the subscript. 

Here comes the interesting part, we have secretly smuggled in a redundancy! Look at the term 
$$
-\lim_{ \epsilon \to 0 } \int_{\epsilon}^{\infty} dx \,  x^\alpha \frac{d}{dx} \phi(x),
$$
what happens if we substitute $\phi$ with $\phi+C$, where $C$ is any constant *a priori*? Nothing! Because the differentiation $d / dx$ kills any constant! This naïve observation turns out to be quite helpful. We can substitute $\phi$ with $\phi+C$ and integrate by part, which yields
$$
-\lim_{ \epsilon \to 0 } \int_{\epsilon}^{\infty} dx \,  x^\alpha \frac{d}{dx} (\phi(x)+C) =-\lim_{ \epsilon \to 0 }  \left\{ x^\alpha (\phi(x)+C)\mid_{\epsilon}^\infty - \int_{\epsilon}^{\infty} dx \,  (\phi(x)+C) \alpha x^{\alpha-1}
\right\} ,
$$
now, how can we make the integral on the right hand side finite? It can be achieved by setting  
$$
C = -\phi(0)
$$
so that 
$$
\lim_{ \epsilon \to 0 } \int_{\epsilon}^{\infty} dx \,  (\phi(x)+C) \alpha x^{\alpha-1} 
= \lim_{ \epsilon \to 0 }  \int_{\epsilon}^{\infty} dx \,  (\phi(x)-\phi(0)) \alpha x^{\alpha-1}
=  \alpha \int_{0}^{\infty} dx \, x^{\alpha-1}(\phi(x)-\phi(0)) 
$$
and 
$$
\lim_{ \epsilon \to 0 } x^\alpha (\phi(x)+C)\mid_{\epsilon}^\infty = x^\alpha (\phi(x)-\phi(0))\mid_{0}^\infty = 0-0=0.
$$
The result is written 
$$
\frac{d}{dx} x^\alpha_{+} = \alpha \text{ Pf.} x^{\alpha-1}_{+}.
$$
Again, this pseudo function defines a singular distribution, singular in the sense that his distribution is not written as the integral of $x^{\alpha-1}_{+}$ against a test function, but extra operation is needed, in our case subtract $\phi(x)$ by $\phi(0)$.

- - -

There is an alternative way to look at the pseudofunction $x_{+}^\alpha$. We can regard it as a function of $\alpha$ instead of $x$, that is 
$$
x_{+}^\alpha: \alpha \mapsto \int_{0}^{\infty} dx \, x^\alpha \phi(x), 
$$
The integral is analytic in the complex half-plane $\text{Re }\alpha>-1$. If we write the integral under the form 
$$
\begin{align}
\int_{0}^{\infty} dx \, x^\alpha \phi(x) &=  \int_{0}^{1} dx \, x^\alpha \phi(x) +  \int_{1}^{\infty} dx \, x^\alpha \phi(x)  \\
&= \int_{0}^{1} dx \, x^\alpha [\phi(x)-\phi(0)+\phi(0)] +  \int_{1}^{\infty} dx \, x^\alpha \phi(x) \\
&= \int_{0}^{1} dx \, x^\alpha [\phi(x)-\phi(0)] +  \int_{1}^{\infty} dx \, x^\alpha \phi(x) +\int_{0}^{1} dx \, x^\alpha \phi(0) \\
&= \boxed{\int_{0}^{1} dx \, x^\alpha [\phi(x)-\phi(0)]} +  \int_{1}^{\infty} dx \, x^\alpha \phi(x) + \frac{\phi(0)}{\alpha+1}
\end{align}
\tag{1}
$$
Here comes the interesting part: the integral in the box is analytic not in $\text{Re }\alpha>-1$, but in $\text{Re }\alpha>-2$! To see that, note
$$
\begin{align}
\int_{0}^{1} dx \, x^\alpha [\phi(x)-\phi(0)] & = \int_{0}^{1} dx \, x^\alpha \left( \phi(0) + x \frac{d}{dx} \phi(0) + \mathcal{O}(x^2) - \phi(0)\right) \\
&= \int_{0}^{1} dx \, x^\alpha \left(x \frac{d}{dx} \phi(0) + \mathcal{O}(x^2)\right) \\
&= \int_{0}^{1} dx \, x^{\alpha+1} \left( \frac{d}{dx} \phi(0) + \mathcal{O}(x)\right) 
\end{align}
$$
which is well defined at $0^+$ if $\alpha+1>-1 \implies \alpha>-2$.

However, there is something fishy about our derivation: we have used the relation 
$$
\int_{0}^{1} dx \, x^\alpha \phi(0) = \left. \frac{\phi(0)}{\alpha+1} 
 x^{\alpha+1}\right\rvert_{0}^1 = \frac{\phi(0)}{\alpha+1} 
 \lim_{ \epsilon \to 0 }  (1-\epsilon^{\alpha+1}), 
$$
where the limit is $1$ only if $\text{Re }(\epsilon+1) > 0 \implies \text{Re }\epsilon>-1$. If $\text{Re }\epsilon<-1$, say, $\epsilon = -1.5$, we would get 
$$
\lim_{ \epsilon \to 0 } \epsilon^{-0.5} = \lim_{ \epsilon \to 0 } \frac{1}{\epsilon^{0.5}}=\frac{1}{0}.
$$
Nevertheless, we just throw away this divergence anyway even when $-2<\text{Re }\alpha<-1$, as the definition of the analytical continuation. We have secretly renormalized the integral! 

Taking into account the relation 
$$
\frac{1}{\alpha+k+1} = -\int_{1}^{\infty} dx \, x^{\alpha+k},\quad \text{Re }\alpha < -k-1, \quad k\in \mathbb{N} 
$$
then this renormalization amounts to
$$
\int_{0}^{\infty} dx \, x^\alpha \phi(x) \to \int_{0}^{\infty} dx \, x^\alpha [\phi(x)-\phi(0)],\quad -2<\text{Re }\alpha<-1.
$$

So, by the end of the day, we have analytically continued the original defining integral to a bigger region! Now, don't forget the last term in Eq. (1) is not defined at $\alpha=-1$, so the new defining integral is meromorphic with singularity at $\alpha=-1$. 

This procedure can be repeated to get linear form 
$$
\phi \mapsto \int_{0}^{\infty} dx \, x^\alpha \phi(x) 
$$
defined on larger and larger domain. 

Coming back to $x^\alpha_{+}$, recall that we defined the continuation
$$
\int_{0}^{\infty} dx \, x^\alpha \phi(x) = \int_{0}^{1} dx \, x^\alpha [\phi(x)-\phi(0)] +  \int_{1}^{\infty} dx \, x^\alpha \phi(x) + \boxed{\frac{\phi(0)}{\alpha+1}}
$$
where we still have a divergent term, namely that the boxed term is divergent at $\alpha=-1$. In a sense we have regularized the integral, namely we have separated it into finite and infinite parts. Now we can continue to "renormalize" it, by simply discard the boxed term. Therefore, we shall define 
$$
\begin{align}
\left\langle x^{-1}_{+}, \phi(x) \right\rangle & := \int_{0}^{1} dx \, x^\alpha [\phi(x)-\phi(0)] +  \int_{1}^{\infty} dx \, x^\alpha \phi(x)\\ 
&= \int_{0}^{\infty} dx \, x^\alpha [\phi(x)-\phi(0)\theta(1-x)] .
\end{align}
$$
The choice of $1$ in $\theta(1-x)$ is kind of arbitrary, I don't see any reasons why it shouldn't be $0.999$ or $1.001$. It can be regarded as an arbitrary choice in the regularization, in separating finite part from the infinite. 

Using 
$$
\left\langle \frac{d}{dx} T, \phi(x) \right\rangle = -\left\langle T, \frac{d}{dx} \phi(x) \right\rangle
$$
we have 
$$
\frac{d}{dx} \text{Pf. }x^{-1}_{+} = -\text{Pf. }x_{+}^{-2}.
$$


We have discussed the situation where $x$ is positive, now let's turn to negative $x$. Similarly to $x_{+}$ we can define function
$$
x\mapsto \theta(-x) \left\lvert x \right\rvert ^\alpha
$$



In the above examples, we have used Hadamard's method to define singular distributions corresponding to certain nonlocally integrable functions. 



- - -

Next we shall study in more detail the finite part of a divergent integral and its main properties. 

Let $f$ be a function nonlocally integrable on $[a,b]$ but integrable on $[a+\epsilon,b]$, where $\epsilon$ is positively infinitesimal. 






- - -

## Schwartz functions and tempered distribution. What are they and why we need them.

Mention Parseval's theorem.

Some functions are integrable, $\int dx |f(x)|<\infty$, but their Fourier transform are not, $\int dk \tilde{f}(k) \to \infty$. Give an example.

Introduce the space of Schwartz functions and tempered distributions.

Finally, as an example, we can understand better the equality $\frac{1}{1+i\epsilon} = \text{p.v.} \frac{1}{x}  - i\pi \delta(x)$.

