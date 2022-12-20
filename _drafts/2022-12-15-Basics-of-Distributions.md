---
layout:     post   				    # 使用的布局（不需要改）
title:      Basics of Distributions 				# 标题 
subtitle:    #副标题
date:       2022-12-15 				# 时间
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

The most important operation for a function is *evaluation*. However, as we shall see, sometimes evaluation is not needed at all for certain purposes, especially when we are interested in "non-local" properties of functions. Non-locally is probably the wrong word, a more accurate one is non-pointwise. The best example might be the Lebesgue integral of a function on the real axis. We know that $\mu$-negligible sets are, as the name suggests, negligible in integral, however every point on the real axis is $\mu$-negligible, hence when talking about $\int dx \, fg$ where $f,g$ are two real-valued functions, if we change the value of $f$ at a single point $x_{0}$, it doesn't affect the result of the integral, however it entirely changes the value of the function evaluated at $x_{0}$!

One might argue that by changing the value of $f(x)$ at $x_{0}$ alone, we are messing up the function, for example the continuity of $f$ would be entirely destroyed. It is true that in physics we seldom need to deal with anything that is not continuous at a point, but in mathematics there is no reason why such weird function should be excluded from the beginning of the discussion. In general, among various kinds of functions, some might be smooth hence quite special, some very general but not smooth. Both should be included.

Next we give a real-life case where functions need not be defined pointwise. Let $L^2(\Omega)$ be the space of square-integrable functions on manifold $\Omega$. Surprisingly, *point-wise operations* are not necessary for test functions in $L^2(\Omega)$, such as point-wise multiplication or division or additions or subtraction, especially evaluation is not defined. 

More generally, the vector space of $\mu$-measurable function from some space $X$ to $\mathbb{R}$, such that $\left\lvert f \right\rvert^{p}$ is $\mu$-integrable for $1\leq p<\infty$, is denoted $\mathcal{L}_{\mu}^{p}(X)$. Next let's define a equivalence relation $f\sim g$ if $\int dx \, \left\lvert f(x)-g(x) \right\rvert=0$, namely $f(x)=g(x)$ [`almost everywhere`](http://www.mathlimbo.net/2022/10/02/Basic-Measure-Theory-Part-I/). The vector space 
$$
L^{p}(X) := \mathcal{L}^{p}(X) / \sim 
$$
is usually the functional space we are interested in. It reflects the spirit that when talking about integrals, we don't care what happens on the $\mu$-negligible sets. However, for evaluation to be well defined everywhere, we need to take into consideration the $\mu$-negligible sets.

Having that in mind, let us move to the definition of distributions.

### What are distributions?

Distribution is some physics books are also called "singular functions" or "generalized function", the latter was used a lot by Russian mathematicians. Consider probably the most famous example of distribution for physicist, the Dirac $\delta$ function (defined on $\mathbb{R}$):
$$
\delta(x) = 
\begin{cases}
0, \quad x\neq 0; \\
\infty,\quad x=0
\end{cases}\quad\text{ and }\quad \int_{-\infty}^{\infty} dx \, \delta(x)\phi(x)=\phi(0) .
$$
where $\phi(x)$ is a "well-behaving" function. Setting $\phi(x)=1$ on $\mathbb{R}$ we obtain the frequently seen expression:
$$
\int_{-\infty}^{\infty} dx \, \delta(x)= 1,
$$
mathematically it is wrong, wrong in the sense that it is incompatible with the Lebesgue measure theory, for $\delta(x)$, when regarded as a function, is only nonzero at $x=0$, which is just a point thus has measure zero. Then the integral of $\delta(x)$ must be zero.

First, some definitions.

**Definition.** A sequence of points $(x_{n})$ in a Hilbert space $\mathcal{H}$ is said to `weakly converge` to $x_{0}$ if for all $y\in\mathcal{H}$, we have 
$$
\lim_{ n \to \infty } \left\langle x_{n},y \right\rangle =\left\langle x_{0},y \right\rangle .
$$
Here $\left\langle x,y \right\rangle$ is the inner product of two vectors $x,y$ in $\mathcal{H}$. 

For example, $\sin(nx)$ on $[0,2\pi]$ weakly converges to $0$. If a sequence converges `strongly`, that is, it converges in norm, then it converges weakly, the converse is not true. 

Now, $\delta(x)$ can be defined as a weak limit of a sequence of functions, it is the limit of the below sequence of functions:
$$
f_{n} = \begin{cases}
n, \quad \left\lvert x \right\rvert \leq \frac{1}{2n}, \\
0, \quad \text{otherwise}.
\end{cases}
$$
It can be verified (as a homework) that the limit of the sequence of the functions satisfies all the properties.

Regarding the functions $f_{n}$ as points in the space of functions $L^{1}(\mathbb{R})$, we have a peculiar example of a space where the limit of a sequence of points is not in the space. This is similar to what happens at the boundary of an open set in $\mathbb{R}$. 

Since $\delta(x)$ is not itself a function, if we want to make meaningful the symbolic rules satisfied by the delta function, we need to define new mathematical objects, called distributions. we shall see that it turns out to be the `dual space` of the space of functions!

**Distribution associates a number to any well-behaved functions in a continuous fashion.** Or, following Laurent Schwartz, **distributions are continuous linear forms on a vector space of sufficiently regular function**.

The specific properties of distributions depends on what functional space they are defined on. For most applications it is sufficient to consider the vector space spanned by infinitely differentiable functions with bounded support, denoted by $C^{\infty}_{c}(\mathbb{R})$, c for compact probably. Recall that the `support` of a function, sometimes denoted by $\text{supp } f(x)$, is the *closure* of the set $\{ x\in \mathbb{R} \mid f(x)=0 \}$. 

Why should we care? Because distribution theory provides simple yet rigorous justifications for a number of manipulations often used in physics. In may areas of application, especially when dealing with differential equations, distribution theory supplies powerful tools that greatly simplifies the analysis.


- - -

### Test functions and distributions

In the theory of distributions $C_{c}^{\infty}(\mathbb{R})$ is usually denoted by $\mathcal{D}$ for simplicity. The elements of $\mathcal{D}$ are called `test functions`.

First we show that $\mathcal{D}$ is not empty, by giving some direct examples. Consider
$$
\phi_{a}(x) = 
\begin{cases}
\exp-\left( \frac{a^{2}}{a^{2}-x^{2}} \right) & \quad \left\lvert x \right\rvert \leq a,  \\
0  & \quad \text{otherwise},
\end{cases}
$$
where $a$ is a positive real number. $\phi_{a}$ has 1) a bounded support $[-a,a]$, 2) is differentiable at all orders. We can shou that for another element in $\mathcal{D}$, the convolution between $f$ and $\phi$ is also in $\mathcal{D}$.

Recall that a subset $A$ of a topological space is said to be `dense`, if any point of the topological space is either in $A$, or is a limiting point of $A$. For example, the set of rational numbers is a dense subset of the real numbers, which is a topological space with the usual topology. 

$\mathcal{D}$

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
Here we can not use the integrate by part trick since $\ln'x = \frac{1}{x}$ is not locally integrable. It shows that although $\ln \left\lvert {x} \right\rvert$ is a regular distribution, its derivative is not. To repeat, **the derivative of a regular distribution may not be a regular distribution**.

To find the derivative of $\ln \left\lvert {x} \right\rvert$ we shall use a technique due to Hadamard, which is widely used for singular distributions given by function that are not locally integrable. Given a divergent integral, the idea is to extract the finite part of this integral to define a *singular* distribution. 

First write
$$
\int dx \, \ln \left\lvert {x} \right\rvert \phi'(x) = \lim_{ \epsilon \to 0 } \int_{\left\lvert {x} \right\rvert \geq \epsilon} dx \, \ln \left\lvert {x} \right\rvert \phi'(x),
$$
the limit exists due to Lebesgue's dominated convergence theorem. 
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

- - -

**Example.** 

We know that $\frac{1}{x}$ is not locally integrable, however $\theta(x) x^{\alpha}, -1<\alpha<0$ is. It defines a regular distribution denoted by $x^\alpha_{+}$. The derivative of $x_{+}^\alpha$ is $x_{+}^{\alpha-1}$, which in general diverges when integrated against a test function. Nevertheless it defines a singular distribution, as we shall see. To determine this derivative we shall proceed as in the previous example, write
$$
\begin{align}
\left\langle \frac{d}{dx} (x_{+}^\alpha), \phi \right\rangle &:= \int_{-\infty}^{\infty} dx \, \left( \frac{d}{dx}   x_{+}^\alpha \right) \phi(x) \\
&:= - \int_{0}^{\infty} dx \,  x^\alpha \frac{d}{dx} \phi(x)  \\
&= -\lim_{ \epsilon \to 0 } \int_{\epsilon}^{\infty} dx \,  x^\alpha \frac{d}{dx} \phi(x),
\end{align}
$$
Note that by changing the integral domain we got rid of the plus sign in the subscript. 

Here comes the interesting part: we have secretly smuggled in a redundancy! In the last line we have
$$
-\lim_{ \epsilon \to 0 } \int_{\epsilon}^{\infty} dx \,  x^\alpha \frac{d}{dx} \phi(x),
$$
what happens is that we can substitute $\phi$ with $\phi+C$, where $C$ is any constant *a priori*, and nothing happens, because the differentiation $d / dx$ kills any constant! This naïve observation turns out to be quite useful. We can substitute $\phi$ with $\phi+C$ and integrate by part, which yields
$$
-\lim_{ \epsilon \to 0 } \int_{\epsilon}^{\infty} dx \,  x^\alpha \frac{d}{dx} (\phi(x)+C) =-\lim_{ \epsilon \to 0 }  \left\{ x^\alpha (\phi(x)+C)\mid _{\epsilon}^\infty - \int_{\epsilon}^{\infty} dx \,  (\phi(x)+C) \alpha x^{\alpha-1}
\right\} .
$$

Now, how can we make the integral on the right hand side finite? It can be achieved by setting  
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

More generally, for negative non-integer $\alpha$, the singular distribution $\text{Pf. }x_{+}^{\alpha}$ is defined by 
$$
\boxed{
\left\langle \text{Pf. }x_{+}^{\alpha}, \phi \right\rangle := \int_{0}^{\infty} dx \, x^{\alpha}\left[ \phi(x)-\phi(0)-x\phi'(0)-\cdots - \frac{x^{m}}{m!} \phi^{(m)} (0)\right]
}.
$$
where $-m-2<\alpha<-m-1$.

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
It would seem that we've just thrown away this divergence, even when $-2<\text{Re }\alpha<-1$, as the definition of the analytical continuation. In a sense, we have secretly renormalized the integral!  Let us **regard the last line in Eq.(1) as the defining expression** of $x_{+}^\alpha$. 

Taking into account the relation 
$$
\frac{1}{\alpha+k+1} = -\int_{1}^{\infty} dx \, x^{\alpha+k},\quad \text{Re }\alpha < -k-1, \quad k\in \mathbb{N} 
$$
which is valid if $\text{Re}(\alpha)<-k-1$, then this renormalization (Hadamard's method) amounts to
$$
\boxed{
\int_{0}^{\infty} dx \, x^\alpha \phi(x) \to \int_{0}^{\infty} dx \, x^\alpha [\phi(x)-\phi(0)],\quad -2<\text{Re }\alpha<-1.
}
$$

By the end of the day, we have analytically continued the original defining integral to a larger region. Now, don't forget the last term in Eq. (1) is not defined at $\alpha=-1$, so the new defining integral is meromorphic with singularity at $\alpha=-1$. 

This procedure can be repeated to get the linear form 
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
The choice of $1$ in $\theta(1-x)$ is kind of arbitrary, I don't see any reasons why it shouldn't be $0.9$ or $1.1$. It can be regarded as an arbitrary choice in the regularization, in separating finite part from the infinite. 

More generally, the linear form
$$
\begin{align}
\phi\mapsto &\int_{0}^{1} dx \, x^{\alpha}\left[ \phi(x)-\phi(0)-\dots-\frac{x^{m}}{m!}\phi^{(m)}(0) \right]  \\
&+\int_{1}^{\infty} dx \, x^{\alpha}\phi(x)+\sum_{k=0}^{m} \frac{\phi^{(k)}(0)}{k!(k+\alpha+1)} 
\end{align}
$$
is defined for $\text{Re}(\alpha)>-m-2$ and $\alpha \neq -1,-2,\dots,-m-1$. 

Since the function $\alpha\mapsto \left\langle \text{Pf. }x_{+}^{\alpha},\phi \right\rangle$ has poles at $\alpha=-1,-2,\dots$, in order to define the distribution $\text{Pf.}x_{+}^{n}$ where $n$ is an integer, we shall remove the divergent term when $\alpha\to-n$. 

We have discussed the situation where $x$ is positive, now let's turn to negative $x$. Similarly to $x_{+}$ we can define function
$$
x\mapsto \theta(-x) \left\lvert x \right\rvert ^\alpha
$$
which is locally integrable if $0>\alpha>-1$, in which case a regular distribution is defined,
$$
\left\langle x_{-}^\alpha , \phi(x) \right\rangle := \int_{-\infty}^{0} dx \, \left\lvert x \right\rvert ^\alpha \phi(x) =  \int_{0}^{\infty} dx \, \phi(-x)x^\alpha. 
$$

This can be generalized to negative non-integer $\alpha$, the pseudo-function $\text{Pf. }x_{-}^{\alpha}$ is defined by
$$
\left\langle \text{Pf. }x_{-}^{\alpha} , \phi \right\rangle := \int_{0}^{\infty} dx \, x^{\alpha} \left[ \phi(-x)-\phi(0)+x\phi'(0)-\dots- \frac{(-1)^{m}x^{m}}{m!} \phi^{(m)}(0) \right] ,
$$
where $m$ is such that $-m-2<\alpha<-m-1$. The idea is exactly the same as $\text{Pf. }x_{+}^{\alpha}$ where we used terms such as $\phi(0),x\phi'(0),$ etc. to cancel the divergence at $x=0$. With this definition we have 
$$
\frac{d}{dx} \text{Pf. }x_{-}^{\alpha} = -\alpha\, \text{Pf. }x_{-}^{\alpha-1},
$$
note the extra minus sign.

We could also define $\text{Pf. }x_{-}^{\alpha}$ as regarding $\alpha$ as a complex number, using analytical continuation and extract the divergent part at $\alpha \to -n$ for some positive integer $n$, as we did with $\text{Pf. }x_{+}^{\alpha}$. We shall not go into details

Now we can put $\text{Pf. }x_{+}^{\alpha}$ and $\text{Pf. }x_{-}^{\alpha}$ together when $\alpha = -n$ is a negative integer. According to the parity of $n$, $\text{Pf. }x^{-n}$ is defined by 
$$
\text{Pf. }x^{-n} := \begin{cases}
\text{Pf. }x_{+}^{-n}+\text{Pf. }x_{-}^{-n},\quad n\text{ is even, }  \\
\text{Pf. }x_{+}^{-n}-\text{Pf. }x_{-}^{-n},\quad n\text{ is odd. }
\end{cases}
$$

In particular, 
$$
\left\langle \text{Pf. } \frac{1}{x}, \phi \right\rangle= \int_{0}^{\infty} dx \, \frac{\phi(x)-\phi(-x)}{x},
$$
that is 
$$
\text{Pf. } \frac{1}{x} = \text{Pv. } \frac{1}{x}.
$$

We leave it to the readers to prove that 
$$
\left\langle \text{Pf. } \frac{1}{x^{2}}, \phi \right\rangle= \int_{0}^{\infty} dx \, \frac{\phi(x)+\phi(-x)-2\phi(0)}{x^{2}}.
\tag{2}
$$

- - -

In the above examples, we have used Hadamard's method to define singular distributions corresponding to certain nonlocally integrable functions. Next we shall give a more general definition of the finite part of a divergent integral and study briefly its main properties.

Let $f(x)$ be a function non-locally integrable on $[a,b]$ but locally integral on $[a+\epsilon,b]$, namely $x=a$ is a singular point of $f(x)$. Assume that $f(x)$ can be written as 
$$
f(x) = g(x) + \sum_{i=1}^{m} \frac{A_{i}}{(x-a)^{\lambda_{i}}},
$$
where $g(x)$ is locally integrable on $[a,b]$. Let the exponents are non-integers such that $\text{Re }\lambda_{i}\geq1$, for reasons will be clear later. The integral gives 
$$
\int_{a+\epsilon}^{b} dx \, f(x) = I(\epsilon)+F(a,b) 
$$
where 
$$
I(\epsilon) = \sum_{i=1}^{m} \frac{1}{\epsilon^{\lambda_{i}-1}} \frac{A_{i}}{\lambda_{i}-1}
$$
is the infinite part and 
$$
F(a,b) = \int_{a+\epsilon}^{b} dx \, g(x) - \sum_{i=1}^{m} \frac{1}{(b-a)^{\lambda_{i}-1}} \frac{A_{i}}{\lambda_{i}-1} 
$$
is the finite part, called the **Hadamard's finite part** of the divergent integral, denoted by 
$$
\boxed{
\text{Fp.} \int_{a}^{b} dx \, f(x) := F(a,b)
}
$$

The generalized integral has the following two important properties,
1. We can change variables to compute the finite part of a divergent integral, namely given $t=t(x)$ we have
$$
\text{Fp.} \int_{a}^{b} dx \, f(x) =  \text{Fp.} \int_{t(a)}^{t(b)}f(t) x'(t)dt.
$$
2. The finite part of a divergent integral is the the **analytical continuation** of an ordinary integral.

These considerations are valid if non of the exponents $\lambda_{i}$ are equal to $1$. If one of the $\lambda_{i}$ is equal to one, the advent of logarithmic function will ruin the argument.

The linear form
$$
\phi\mapsto \text{Fp.} \int_{a}^{b} dx \, f(x)\phi(x) 
$$
being continuous, defines the singular distribution $\text{Pf.}f$ namely the pseudofunction given by $f$.
 
- - -

Next we shall study in more detail the finite part of a divergent integral and its main properties. 

Let $f$ be a function nonlocally integrable on $[a,b]$ but integrable on $[a+\epsilon,b]$, where $\epsilon$ is positively infinitesimal. 






- - -

## Schwartz functions and tempered distribution. What are they and why we need them.

Mention Parseval's theorem.

Some functions are integrable, $\int dx |f(x)|<\infty$, but their Fourier transform are not, $\int dk \tilde{f}(k) \to \infty$. Give an example.

Introduce the space of Schwartz functions and tempered distributions.

Finally, as an example, we can understand better the equality $\frac{1}{1+i\epsilon} = \text{p.v.} \frac{1}{x}  - i\pi \delta(x)$.

