---
layout:     post   				    # 使用的布局（不需要改）
title:      Basic Measure Theory 				# 标题 
subtitle:    #副标题
date:       2022-10-9 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/mathArt15.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - math
    - functionalAnalysis
    - distribution
    - measureTheory
---

### Integral of Measurable Functions

In what follows, we suppose that all function are measurable and defined on the measure space $(X,\mathcal{A},\mu)$. 

First we define the integral with respect to some measure $\mu$,
**Definition** Let $\phi=\sum_{i=1}^n \alpha_{i} 1_ {A_{i}}$ be a simple function; then 
$$
\int \phi \, d\mu=\sum_{i-1}^n \alpha_{i} \mu(A_{i})
$$
is called the integral of $\phi$ with respect to the measure $\mu$. 

Recall that function is simple if it is measurable and takes finite number of values, such as the step function defined on $[-1,1]$.

The integral of $\mu$ with respect to $\mu$ is finite if and only if the measure of the set where $\phi(x) \neq 0$ is finite. In other words, the measure of the support of $\phi$ must be zero. 

This definition is quite intuitive, for example, if we want to know how expensive a bag of fruit is, we just count the number of certain kind of fruit (the measure of the set), multiply it by the price (value of the function on this set), and sum over all kinds of the fruits. 

Whatever properties for integrals certainly hold for integral with respect to measure $\mu$ as well, for example 
$$
\int (\phi_{1}+\phi_{2}) \, d\mu =  \int (\phi_{1}) \, d\mu + \int (\phi_{2}) \, d\mu,
$$
I am too lazy to list all of them here.

Now we need to generalize this concept to continuous functions, say $f(x)$. Starting from the simplest case, for now we will assume $f(x)\geq 0$.

**Definition** Let $f$ be a position measurable function, then the integral of $f$ with respect to the measure of $f$ is 
$$
\int f \, d\mu = \text{sup} \int \psi \, d\mu, 
$$
where the supremum is taken over all positive simple functions $\phi$ such that $\phi<f$ everywhere. This means we are limiting function $f$ from below. $f$ is said to be $\mu$ integrable if its integral is *finite*.

$f$ is only integrable if the the set 
$$
\{ x \mid f(x) = \infty \} 
$$
is $\mu$-negligible. Note that this condition is necessary but not sufficient. 

Next we give the monotone convergence theorem without proof.

**Theorem** Monotone convergence theorem. Let $(f_{n})$ be a sequence of positive measurable functions such that 
$$
f_{n}(x) < f_{n+1}(x) \quad \forall n\in \mathbb{N} \quad \forall x\in X
$$
and 
$$
\forall x\in X \quad \lim_{ n \to \infty } f_{n}(x) = f(x).
$$
Then 
$$
\lim_{ n \to \infty } \int f_{n} \, d\mu = \int f \, d\mu.  
$$

This theorem is also called the Beppo Levi theorem. 

The integral of a positive function is only zero if the function is zero almost everywhere.

What about functions that are not positive? The solution is rather intuitive: We separate positive and negative parts and treat them both as positive functions. Given a real-valued function $f$, define 
$$
f^+ = \begin{cases}
f(x)  &  f(x) >0  \\
0  &  f(x) < 0
\end{cases}
$$
and 
$$
f^- = \begin{cases}
-f(x)  &  f(x) < 0  \\
0  &  f(x) > 0
\end{cases}
$$
where both $f^{\pm}$ are positive functions. $f$ is said to be $\mu$-integrable if both $f^+$ and $f^-$ are integrable, and the integral of $f$ is 
$$
\int f \, d\mu = \int f^+ \, d\mu - \int f^- \, d\mu.   
$$

Quite intuitive, isn't it? For complex-valued functions, we just need to treat its real and imaginary part as real functions, everything follows from that of a real-valued function. 

The interesting thing is that, as far as integral is concerned, we can neglect the sets with zero measure. Traditionally, any function has an operation called evaluation which is defined pointwise, e.g. given a real-valued function $f(x)$, we can evaluate it at point $x = x_{0}$, which gives us a real number. However, a point has measure zero, so, again, as far as integral is concerned, evaluation is not needed. You could perfectly come up with a function which can't be evaluated at some point, for instance a function at $x=x_{0}$ might not be defined, but still the function could be integrable. To say a function is $\mu$-integrable just means that $f^{+,-}$ are $\mu$-integrable respectively. 

Two functions $f,g$ has the same integral if they equal to each other almost everywhere, and this is a equivalence relation. 

The sum of a convergent series is nothing but an integral on the counting measure. Recall that give an finite set $S$ and $A \subseteq S$ then the *cardinality* of $A$ is the number of elements in $A$, sometimes denoted by $\#(A)$. Then $\#$ regarded as a measure is called the counting measure. 

**Theorem** The set of all $\mu$-integral functions form a vector space, it is denoted by $\mathcal{L}_{\mu}^1$.

The superscript $1$ denotes the power of the function. $\mathcal{L}^2_{\mu}$ would mean the square of the functions are integrable. This theorem is easy to verify since addition, subtraction and number-production of an element in $\mathcal{L}_{\mu}^1$ is still in $\mathcal{L}_{\mu}^1$. 

**Theorem** If $f$ is $\mu$-integrable, so is $\lvert f \rvert$, and we have 
$$
\left\lvert \int f \, d\mu  \right\rvert \leq \int \left\lvert f \right\rvert  \, d\mu.  
$$

Recall that for $f$ to be $\mu$-integrable, by definition both $f^+$ and $f^-$ are required to be finite.

A measurable function is $\mu$-integrable if and only if $\left\lvert f \right\rvert$ is $\mu$-integrable. 

If a function is Riemann integrable on $[a,b]$ then it is also Lebesgue integrable on $[a,b]$, and the two results agree. Indeed, if $f$ is Riemann integrable then we can always find two limiting step functions sandwiching $f$ from above and below, 
$$
g_{\epsilon} \leq f \leq h_{\epsilon}
$$
where $g,h _{\epsilon}$ are step functions and 
$$
\int (g_{\epsilon} - h_{\epsilon}) \, d\mu < \epsilon. 
$$

Step function are always Lebesgue integrable, plus the function is bounded, thus $f$ is also Lebesgue integrable. To summarize we have 
$$
 \text{Riemann integrable} \implies \text{Lebesgue integrable}.
$$

The inverse, however, is not necessarily true. A famous example is the Dirichlet function, defined on $[0,1]$ and 
$$
f(x) = \begin{cases}
0  &  \text{if x is rational}, \\
1  &  \text{if x is irrational}.
\end{cases}
$$

Since $f=1$ almost everywhere, the Lebesgue measure is $1$. Recall that $f=1$ almost everywhere means that the set on which $f=0$ has measure zero, and this is true since $f(ratioanl)=0$ and rational numbers are countable, plus each point has zero measure, and countable many zeros are still zero. However, it is impossible to find two step function to sandwich Dirichlet function, thus it is not Riemann integrable. 

The class of Riemann integrable functions is quite restricted. Of course a continuous, bounded function on a finite interval $[a,b]$ is Riemann integrable, but being Riemann integrable actually requires less – any bounded function on $[a,b]$ which is continuous *almost everywhere* is Riemann integral. For example, the $\theta(x)$ function defined on $[-2,2]$ is continuous except at $x=0$, so it is continuous almost everywhere, thus Riemann integrable. 

E.g. The function 
$$
f: x \mapsto \frac{\sin x}{x}
$$
is not integrable with respect to the Lebesgue measure on $\mathbb{R}^+$ since $\left\lvert f \right\rvert$ is not integrable on $\mathbb{R}^+$.

We know that $\frac{\sin x}{x}$ is conditionally convergent, such notion does not exist in Lebesgue theory of integral. 

### Lebesgue's Dominated Convergence Theorem

According to my mathematical friends, the dominated convergence theorem is one of the most important results of Lebesgue's integration theorem. It tells us how to deal with the limit of a sequence of functions under the integral sign, and it might be trickier than some physicist might have thought.

To understand Lebesgue's theorem we need the following lemma.

**Fatou's lemma.** Let $(f_{n})$ be a sequence of functions which are nonnegative and measurable on $(X,\mathcal{A},\mu)$. Then
$$
\boxed{
\int \lim_{ n \to \infty } \text{inf } f_{n} \, d\mu \leq \lim_{ n \to \infty } \text{inf } \int f_{n} \, d\mu . 
}
$$

The equal sign is not surprising at all, what usually surprises people is the less than sign, for Fatou's lemma tells us that if you first take pointwise limit of a sequence of functions, then integrate the limit, what you get might be less than integrate each function in the sequence and take the limit later.

To have an intuitive feeling about the lemma, consider an example where the less-than-relation holds. Consider a sequence of functions $(f_{n}),\,n\in \mathbb{N}$ defined on $\mathbb{R}$ with Borel $\sigma$-set,
$$
f_{n}(x) = 
\begin{cases}
\frac{1}{n}  &  x\in (0,n), \\
0   &  \text{otherwise}.
\end{cases}
$$
This sequence uniformly converges to zero function on $\mathbb{R}$, Thus 
$$
\int  \lim_{ n \to \infty } \text{ inf } f_{n} \, d\mu = \int_{0}^n \lim_{ n \to \infty } \text{ inf }\frac{1}{n} \, d\mu = \int 0 \, d\mu = 0,  
$$
On the other hand, the integral of $f_{n}$ on $\mathbb{R}$ is always $1$, thus
$$
\lim_{ n \to \infty } \text{ inf } \int   f_{n} \, dx = \lim_{ n \to \infty } \text{ inf } \int_{0}^{n} \frac{1}{n} \, d\mu  = \lim_{ n \to \infty } \text{ inf } 1 = 1,
$$
and $0<1$. 

The integral of a function not only depends on its pointwise value, but also the support. In this context, taking the pointwise limit of a function might give you different results because the limit procedure might give you some function value which is qualitative different, for example $\frac{1}{n}$ is qualitatively different from $0$ because there is a number that multiplies $\frac{1}{n}$ could give you $1$ but there is no such number for $0$. By taking the limit under the integral sign, we might miss the information about the support of the function, while taking the limit of the integral will not. That's why these two results could be different. 

The condition that $(f_{n})$ being non-negative is also important, it is necessary for the $\leq$ sign to hold.

To prove the lemma, define
$$
g_{n} := \underset{k\geq n}{\text{ inf }} f_{k},
$$
then $g_{n}$ is 1)measurable since $f_{n}$'s are measurable, 2) non-decreasing and 3) $g_{n} \leq f_{n}$ by construction. Properties 2) and 3) are pointwise. We have 
$$
\lim_{ n \to \infty } \int g_{n} \, d\mu = \int \lim_{ n \to \infty } \text{ inf } f_{n} \, d\mu,  
$$
Where we have interchanged the order of $\lim_{ n \to \infty }$ and $\int  \, d\mu$. This is allowed since both sides are $<\infty$. Since $g_{n} \leq f_{n}$, we have 
$$
\int g_{n} \, d\mu \leq \int f_{n} \, d\mu \implies \lim_{ n \to \infty } \int g_{n} \, d\mu \leq \lim_{ n \to \infty } \int f_{n} \, d\mu = \lim_{ n \to \infty } \text{ inf } \int f_{n} \, d\mu.      
$$
The lemma follows.

**Theorem** Lebesgue's dominated convergence theorem. Let $(X,\mathcal{A},\mu)$ be a measure space, let $(f_{n})$ be a sequence of measurable functions from $X$ to $\mathbb{R}$ or $\mathbb{C}$ that converge to $f$ almost everywhere. If there exists $\mu$-integral function $g$ such that, for all positive integers $n$, $\left\lvert f_{n} \right\rvert \leq g$, then
$$
\lim_{ n \to \infty }  \int f_{n} \, d\mu = \int f \, d\mu. 
$$
Note the position of the limit, it is in front of the integral not under it, so information about the support of the function is already included in the integral. 

$f$ is measurable since $g$ is and
$$\left\lvert f_{n} \right\rvert \leq g \implies \left\lvert f \right\rvert \leq g.
$$
For the same reason $f$ is integrable. Since $\left\lvert f_{n} - f \right\rvert \leq 2g$, the sequence of functions 
$$
2g - \left\lvert f_{n}-f \right\rvert
$$
are non-negative. Then Fatou's lemma applies and yields 
$$
\int \lim_{ n \to \infty } \text{ inf } (2g-\left\lvert f_{n}-f \right\rvert ) \, d\mu \leq \lim_{ n \to \infty } \text{ inf } \int (2g-\left\lvert f_{n}-f \right\rvert ) \, d\mu.
$$
Since $\lim \text{ inf } f_{n} = f$, we have 
$$
2\int g \, d\mu \leq 2 \int g \, d\mu - \lim_{ n \to \infty } \text{ inf }\int  \left\lvert f_{n}-f \right\rvert  \, d\mu. 
$$
Since $\int g \, d\mu < \infty$, we can subtract it on both sides,
$$
\lim_{ n \to \infty } \text{ inf }\int  \left\lvert f_{n}-f \right\rvert  \, d\mu \leq 0,
$$
however the integral of a non-negative must be non-negative, thus 
$$
\lim_{ n \to \infty } \text{ inf }\int  \left\lvert f_{n}-f \right\rvert  \, d\mu = 0 \implies 
\boxed{
\lim_{ n \to \infty } \int f_{n} \, d\mu = \int f \, d\mu  
}.
$$

The $n$-independent function $g$ is said to *dominate* the sequence $(f_{n})$. Roughly speaking it provides some kind of an upper limit so the sequence of functions behave nicely under limiting procedure. 

There indeed exists functions that can not be dominated by other functions, such as our old friend $f_{n}: x \mapsto \frac{1}{n} 1_{[0,n]}$. To see that $f: x \mapsto \frac{1}{n} 1_{[0,n]}$ has no dominating function $g(x)$ we notice that the support of the function goes to $\infty$ as $n \to \infty$. Of course you can find a function so that $\left\lvert f_{n} \right\rvert \leq g$ for all $n$, such as $g = 1$ on $\mathbb{R}$, but then $g$ wouldn't be measurable. Thus dominated convergence theorem doesn't apply here. The theorem applies to function $f: x\mapsto x^n$ defined on $[0,1]$, since it is dominated by $1_{[0,1]}$. The takeaway is that, the support of a function matters!

In Riemann's integral theory there is something called the improper integral, such as infinite integral, or when the integrand is discontinuous. They generalize Riemann's integral theory. There is no such thing in Lebesgue's integral theory. 

**Example** Consider the sequence of functions defined on $[0,1]$,
$$
f_{n}: x \mapsto \frac{n^{3/2}x}{1+n^2 x^2}
$$
which tends to zero at large $n$. However, the convergence is not uniform since no matter how large $n$ is, there always exists a very small $x \sim \frac{1}{n}$ where $f_{n} \sim \frac{\sqrt{ n }}{2}$. Thus it is not clear that its Riemann integral is zero or not, 
$$
\lim_{ n \to \infty } \int_{0}^1 f_{n} \, dx  \overset{?}{=} 0.
$$
Here is where the dominated convergence theorem come to aid. We can find a measurable function $\frac{~1}{\sqrt{ x }}$ that dominates $f_{n}$, thus
$$
\lim_{ n \to \infty } \int_{0}^1  \, f_{n}dx = \int_{0}^{1} \lim_{ n \to \infty } f_{n} \, dx =0.
$$

The following results are important to study a function defined by an integral. Since summation is just a discrete form of integral, the results apply equally to functions defined by a series. 

**Theorem**  Let $(X,\mathcal{A},\mu)$ be a measure space and $(Y,d)$ be a metric space; if $f$ is a function defined on $X \times Y$ such that 
1. for all $y \in Y$, $x \mapsto f(x,y)$ as a function of $x$ is measurable,
2. for all $x\in X$, $y \mapsto f(x,y)$ as a function of $y$ is continuous at $y_{0}$,
3. there exists an integrable function $g$ on $X \times Y$ such that for all $x\in X$ and $y \in Y$, $\left\lvert f(x,y) \right\rvert\leq g$.

Then, for all $y\in Y$, $x \mapsto f(x,y)$ is integrable, and the function defined by integral 
$$
F: y \to \int f(x,y) \, d\mu
$$
is continuous at $y=y_{0}$.

The proof can be found in textbooks. The proof of course uses the Lebesgue's dominance convergence theorem. 

There is a similar theorem, 
**Theorem** let $(X,\mathcal{A},\mu)$ be a measure space and $\mathbb{I}$ an open interval of $\mathbb{R}$, if $f$ is a function defined on $X \times \mathbb{I}$ and satisfies 
1. $x \mapsto f(x,y)$ is integrable for all $x\in X$,
2. $y\mapsto f(x,y)$ is differentiable for $x$ almost everywhere, 
3. there exists a function defined on $X \times \mathbb{I}$ that dominates $f(x,y)$,

then for all $y \in \mathbb{I}$, the function 
$$
x \mapsto \frac{d}{dy} f(x,y)
$$
is integrable, and the function 
$$
F: y \mapsto \int f(x,y) \, dy
$$
is differentiable. 