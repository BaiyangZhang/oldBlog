---
layout:     post   				    # 使用的布局（不需要改）
title:      Basics of Distributions 				# 标题 
subtitle:    #副标题
date:       2022-12-26 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/functionalAnalysis.png 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - math
    - functionalAnalysis
    - distribution
    - measureTheory
---

## Preliminaries

Let $X$ be a metric space, and $\left\{ x _ {n} \right\}$ be a sequence of points in $X$. We say that $\left\{ x_ {n} \right\}$ is a `Cauchy sequence` if for all $\epsilon$, there exists $N\in\mathbb{N}^{+}$ so that for any $i,j>N$ we have $d(x_{i},x_{j})<\epsilon$, where $d(x,y)$ is the distance between $x$ and $y$ given by the measure.

Note that in the definition of Cauchy sequence, the concept of distance is needed, thus a metric must be defined a priori.

We say that  $\left\{ x_ {n} \right\}$ converges to $x$ if $\lim_{ n \to \infty }d(x_{n},x)=0$. As we would naturally expect.

As a proposition, if $X$ is a normed space, then every convergent sequence in $X$ is a Cauchy sequence. The prove is skipped here. Hint: for two points $x_{i},x_{j}$ where$i,j>N$ for some $N$ in the sequence, consider their respective distance to their limit first.

**Not every Cauchy sequence in a metric space converges.** For example, $\mathbb{Q}$ is a metric space with metric given by the difference of two numbers, we can find a sequence $3,3.1,3.14,3.141,\dots$ that limits to $\pi$ which is not an element of $\mathbb{Q}$, hence its limit does not exist, hence it does not converge to any point in $\mathbb{Q}$. It is a Cauchy sequence in $\mathbb{Q}$ nevertheless. This naturally leads us to the next definition:

**Definition.** A metric space $X$ is said to be `complete` if every Cauchy sequence of $X$ converges to a point in $X$.

For example, $\mathbb{Q}$ is not complete but $\mathbb{R}$ is. 

Any normed space is automatically a metric space since the metric is given by 
$$
d(x,y) := \left\lVert x-y \right\rVert ,
$$
thus it makes sense to talk about Cauchy sequence and convergent sequence in a normed space. 


**Definition.** A normed vector space is called a `Banach space` if it is complete.

That is, a Banach space is a `complete normed vector space`. All the finite-dimensional normed vector spaces, such as the three dimensional spatial space, is a Banach space. **Completeness is really an issue only for infinite dimensional spaces**.

An example of a infinite dimensional space is a `function space`. A function space is a vector space whose elements are functions, usually satisfying certain properties, such as continuity or smoothness. For example, the set of all functions $\mathbb{R}\to \mathbb{R}$ forms a vector space, with addition and scalar multiplication defined pointwise. However, there is no obvious choice for a norm on this space. Should it be the integral? Or the integral of the absolute value of a function? However, if we strict the functions in consideration a bit we can define a normed function space.

As an example, consider all the continuous functions defined on $[-1,1]$, denoted by $C([-1,1])$. As for the norm, we can defined it to be the integral of the abs of the function:
$$
\left\lVert f(x) \right\rVert := \int dx \, \left\lvert f(x) \right\rvert .
$$
The problems is that, $C([-1,1])$ is not a complete space with respect to this norm. For example, consider the sequence of functions $f_{n}$
$$
f_{n} = 
\begin{cases}
-1 & x\in\left[ -1,-\frac{1}{n} \right]; \\
nx  &  x\in\left[ - \frac{1}{n}, \frac{1}{n} \right]; \\
+1  &  x\in\left[ \frac{1}{n},1 \right];
\end{cases}
$$
this function is continuous all right, but not smooth, and that may cause problems. You can even check that $f_{n}$ is a Cauchy sequence. However, the limit of $f_{n}$ is the step function, which stops being continuous. 

The trouble is that **sequences of continuous functions can converge to discontinuous functions, thus the space of all continuous functions is not complete.**

To fix this problem, we need the help from Lebesgue measure. Given a measure space $(X,\mu)$, where $\mu$ is the measure on $X$, we may assume that the space of 1-integrable functions $\mathcal{L}^{1}(X)$ is a Banach space. Well, not quite so, because the norm is not really given by $\int dx \, \left\lvert f(x) \right\rvert$, contrary to one might think. The issue is that a normed space must satisfy
$$
\left\lVert \mathbf{v} \right\rVert =0 \implies \mathbf{v}=0
$$
but in $\mathcal{L}^{1}(X)$, $\int dx \, \left\lvert f(x) \right\rvert=0$ does not necessarily imply that $f(x)=0$ everywhere, it only implies, with respect to the measure $\mu$, $f(x)$ is zero almost everywhere (shorten to a.e.). Thus, to make $\mathcal{L}^{1}(X)$ into a normed space, we must mod out the *almost everywhere* condition. That will give us a true Banach space,
$$
L^{1}(X):=\mathcal{L}^{1}(X) / \sim ,\quad \sim  \text{ denotes equivalent almost everywhere}
$$

In other words, if two function only differ on $\mu$-negligible sets, then they are considered as the same thing in space $\mathcal{L}^{1}(X)$.



## Distributions

### Functions that can not be evaluated

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

Having that in mind, let us move to distributions.

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

First we show that $\mathcal{D}$ is not empty, by giving some examples. Consider
$$
\phi_{a}(x) = 
\begin{cases}
\exp-\left( \frac{a^{2}}{a^{2}-x^{2}} \right) & \quad \left\lvert x \right\rvert \leq a,  \\
0  & \quad \text{otherwise},
\end{cases}
$$
where $a$ is a positive real number. $\phi_{a}$ has 1) a bounded support $[-a,a]$, 2) is differentiable at all orders. We can show that for another element in $\mathcal{D}$, the convolution between $f$ and $\phi$ is also in $\mathcal{D}$.

Recall that a subset $A$ of a topological space is said to be `dense`, if any point of the topological space is either in $A$, or is a limiting point of $A$. For example, the set of rational numbers is a dense subset of the real numbers, which is a topological space with the usual topology. 

**$\mathcal{D}$ is closed under convolution.**  If $f,\phi$ are elements of $\mathcal{D}$, their convolution
$$
f \star g (x)= \int dy \, f(y)g(x-y) 
$$
is also an element of $\mathcal{D}$, since one can take derivatives under the integral sign, and the support of $f\star g$ is compact.

- - -

To define continuity in $\mathcal{D}$, we need the concept of convergence in $\mathcal{D}$.

**Definition.** A sequence of test functions $(\phi_{n})$ in $\mathcal{D}$ is said to converge to function $\phi$ if 
1. all the supports of the functions of the sequence are contained in a bounded subset of $\mathbb{R}$;
2. for each positive integer $p$, the sequence of derivatives of order $p$, $\phi_{n}^{(p)}$ converges *uniformly* to the derivative of order $p$ of $\phi$.

It is readily seen the limit $\phi$ is in $\mathcal{D}$ since it is smooth and the support is bounded.

We give an counter example of converge of test functions. Consider
$$
\phi_{n} := 
\begin{cases}
0, & \left\lvert x \right\rvert >n, \\
\frac{1}{n} \exp -\left( \frac{n^{2}}{n^{2}-x^{2}} \right), & \left\lvert x \right\rvert \leq n,
\end{cases}
$$
the limit of $\Phi_{n}$ seems to be zero, however that is not true since the support of $\phi_{n}$ goes to the entirety of $\mathbb{R}$ instead of a bounded subset.

**Definition.** A *continuous linear form* on $\mathcal{D}(\mathbb{R})$ is called a `distribution` on $\mathbb{R}$.

The construction is that, first we define the linear vector space of test functions, then we define the continuous linear forms that maps the test functions to $\mathbb{R}$ to be distributions.

Distribution on $\mathbb{C}$ can be defined in a similar way. A distribution is an element of the `topological dual space` of $\mathcal{D}$. This space is denoted by $D'$ or $D^{\ast}$. We will use them interchangeably in the note.

Next we shall explain what linearity means for distributions. Let $T$ be a distribution, we would like the property
$$
T(\lambda_{1}\phi_{1}+\lambda_{2}\phi_{2})=\lambda_{1}T(\phi_{1})+\lambda_{2}T(\phi_{2})
$$
where $\phi_{1,2}$ belongs to $\mathcal{D}$ and $\lambda_{1,2}$ belong to $\mathbb{R}$ (or $\mathbb{C}$). That is the requirement of continuity. It follows the 
$$
\lim_{ n \to \infty } T(\phi_{n}) = T(\lim_{ n \to \infty } \phi_{n}) = T(\phi),\quad \phi_{n}\text{ converges to }\phi.
$$

$\mathcal{D}^{\ast}$ is a vector space, for any test function $\phi$ in $\mathcal{D}$ we have
$$
(\lambda_{1}T_{1}+\lambda_{2}T_{2})(\phi)=\lambda_{1}T_{1}(\phi)+\lambda_{2}T_{2}(\phi).
$$
Sometimes we use the notation of inner product to denote the action of a distribution on a test function, in this notation the last expression would be 
$$
\left\langle \lambda_{1}T_{1}+\lambda_{2}T_{2},\phi \right\rangle = \lambda_{1}\left\langle  T_{1},\phi\right\rangle + \lambda_{2}\left\langle  T_{2},\phi\right\rangle. 
$$
We will use these two notations interchangeably.

The most common way to define the map $D^{\ast}\otimes D\to \mathbb{R}$ is by evaluating the **integral**. For example, given a function $f:\mathbb{R}\to \mathbb{R}$ that is `locally integrable`,  that is integrable on any bounded subsets of $\mathbb{R}$, the linear form $T_{f}$ defined on $\mathcal{D}$ maps a test function $\phi$ to $\mathbb{R}$ in the following sense:
$$
\phi\to \left\langle T_{f},\phi \right\rangle =\int dx \,  \phi(x)f(x).
$$

Every locally integrable function $f$ corresponds to a distribution $T_{f}$, the reverse is not true. A distribution given by a locally integrable function is said to be `regular`. Since the map from functions to numbers are defined by integrals, of course two functions agree to each other almost everywhere define the same distribution. If a distribution is not regular, then it is called `singular`. 

As mentioned before, the most famous example of a singular distribution must be the so-called Dirac delta function, which strictly speaking is not a function at all. So we will call it the `Dirac distribution` $\delta$. It is defined by 
$$
\left\langle \delta,\phi(x) \right\rangle :=\phi(0),\quad \phi\in\mathcal{D}.
$$
$\delta$ is not regular since there is no locally integrable function that has the same integral property. More generally, the distribution $\delta_{a}$ is defined by 
$$
\left\langle \delta_{a},\phi \right\rangle :=\phi(a).
$$

- - -

The set of all *regular distributions* is a subspace of $D^{\ast}$. In a sense, distributions are generalizations of locally integrable functions. However, it is important to keep in mind that distributions are not functions, they live in the dual space of (test) functions.

The product of two distributions are not defined in general. In physics this sometimes leads to divergences, computing some integral where the product of two distributions (usually Dirac $\delta$ distributions) occur. However, in some particular cases, there is a self-consistent way to define the product of two distributions. For example, consider two *regular distributions* $T_{f}$ and $T_{g}$ where $f,g$ are two locally integrable functions. If their product, $f(x)g(x)$ is another locally integrable function, then we can define the product of $T_{f}$ and $T_{g}$ as 
$$
\left\langle T_{f}\times  T_{g},\phi(x) \right\rangle :=\int dx \, f(x)g(x)\phi(x) .
$$
More generally, given a regular distribution $T_{f}$, it is possible to define the product of any distribution $T$ by $T_{f}$, regardless of whether $T$ is singular or not. $T_{f}T$ is defined by 
$$
\left\langle T_{f}T,\phi(x) \right\rangle :=\left\langle T,f(x)\phi(x) \right\rangle .
$$
This definition makes sense since if $f,\phi$ are in $\mathcal{D}$, so is $f(x)\phi(x)$.

To simply notations, we sometimes use the same symbol to denote a function and the regular distribution defined by it. For example, $\phi T_{f}$ could be the product of distribution $T_{\phi}$ and $T_{f}$.

- - -

Why are they called distributions? I guess it is because they are the mathematical objects that correctly describe physical distributions, such as the distribution of a mass, as the Dirac delta distribution can be used to describe the mass of a point particle. These physical distributions usually have certain symmetry properties, it motivates the following definition, where we have generalized the idea of distributions to arbitrary dimensions. The generalization is trivial.

**Definition.**  Let $u$ be a invertible map $\mathbb{R}^{n}\to \mathbb{R}^{n}$. Let $T$ be a distribution defined on $\mathbb{R}^{n}$. The `transform` of $T$ by $u$ is the distribution $uT$ defined by 
$$
\left\langle uT,\phi \right\rangle :=\left\lvert J \right\rvert \left\langle T,u^{-1}\phi \right\rangle, \quad \left\lvert J \right\rvert \text{ is the Jacobian of }u, \quad J= \frac{ \partial u(x) }{ \partial x } ,
$$
and 
$$
(u^{-1}\phi(x))=\phi(u(x)).
$$
If $uT=T$, $T$ is said to be `invariant` under $u$.

The consistency of this definition follows from the fact that if $f$ is in $\mathcal{D}$, so is $u^{-1}f$. $u$ can be a translation, a rotation, a reflection, etc. For example, if $\tau_{a}$ is a translation, we have
$$
\tau_{a}x = x+a,\quad \tau_{a}^{-1}\phi(x)=\phi(\tau_{a}x)=\phi(x+a)
$$
thus 
$$
\tau_{a}\delta=\delta_{a}.
$$

- - -

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

Let $f$ be a function nonlocally integrable on $[a,b]$ but integrable on $[a+\epsilon,b]$, where $\epsilon$ is a positive infinitesimal. Assume $f$ can be written as 
$$
f(x) = \sum_{i=1}^{m} \frac{A_{i}}{(x-a)^{\lambda_i}} + g(x)
$$
where $g(x)$ is integrable on $[a,b]$, the exponents $\lambda_{i}$ are **non-integers**  such that $\text{Re}\lambda_{i}\geq 1$, for purposes that will be clear later. Then
$$
\int_{a+\epsilon}^{b} dx \, f(x) = I(\epsilon)+F(\epsilon), 
$$
where 
$$
I(\epsilon) = \sum_{i=1}^{m} \frac{A_{i}}{\lambda_{i}-1} \frac{1}{\epsilon^{\lambda_{i}-1}},
$$
that's why we require the real part of $\lambda_{i}$ to be no less then $1$. The finite part is 
$$
F(\epsilon) =  -\sum_{i=1}^{m} \frac{A_{i}}{\lambda_{i}-1} \frac{1}{(b-a)^{\lambda_{i}-1}} +\int_{a}^{b} dx \, g(x). 
$$
When $\epsilon\to_{0}$, $I(\epsilon)$ diverges while $F(\epsilon)$ has a finite limit. 

**Definition.** $F(\epsilon)$ is called the `Hadamard's finite part` of the divergent integral $\int_{a}^{b} dx \, f(x)$, denoted by 
$$
\text{Fp. }\int_{a}^{b} dx \, f(x). 
$$

This generalized integral is useful in physics, for it satisfies the following important properties,

a. The chain rule applies to the integral, meaning 
$$
\text{Fp. } \int_{a}^{b} dx \, f(x) = \text{Fp. } \int_{t(a)}^{t(b)} dt \,  \frac{dx}{dt}f(t).
$$
b. The finite part of a divergent integral is the analytical continuation of an ordinary integral.

These properties are satisfies if non of the $\lambda_{i}$s are equal to $1$.


## Convergence in $D^{\ast}$

A distribution $T_{\lambda}$ is said to converge to $T_{\lambda_{0}}$ in $D^{\ast}$ if for any test functions $\phi$ in $D$ we have 
$$
\lim_{ \lambda \to \lambda_{0} } \left\langle T_{\lambda},\phi \right\rangle =\left\langle T_{\lambda_{0}},\phi \right\rangle ,
$$
convergence of sequences and series are defined similarly. It follows that if $T_{\lambda}$ converges to $T_{\lambda_{0}}$ then

(i) If $\psi\in C^{\infty}$, 
$$
\lim_{ \lambda \to \lambda_{0} } \psi T_{\lambda} = \psi T_{\lambda_{0}}.
$$
(ii) If the distribution $T_{\lambda},S_{\lambda}$ converges to $T_{\lambda_{0}},S_{\lambda_{0}}$ respectively, then 
$$
\lim_{ \lambda \to \lambda_{0} } (T_{\lambda}+S_{\lambda}) = T_{\lambda_{0}}+S_{\lambda_{0}}
$$

As an example, consider the so-called Dirac sequence, which converges to the Dirac distribution. Let $f$ be any integrable function such that 
$$
\int_{-\infty}^{\infty} dx \, f(x) =1, 
$$
the sequence of functions $f_{n}$, defined by
$$
f_{n} := n f(nx),\quad n\in\mathbb{Z}^{+}
$$
defines a sequence of distributions $T_{f_{n}}$, called the `Dirac sequence associated to` $f$.  We state without proof that $T_{f_{n}}$ converges to $\delta$. It can be understood intuitively, since a ever larger $n$ squeeze the function horizontally but preserves the integral.

**Theorem.** Let $T_{\lambda}$ converges to $T_{\lambda_{0}}$ when $\lambda$ tends to $\lambda_{0}$, then the derivative $T'_{\lambda}$ converges to $T_{\lambda_{0}}'$.

The proof is very simple thus skipped here. 

## Convolution

Convolution plays an essential rule in the theory of distribution. Many types of differential equations or integral equations are convolution equations. In the following we sometimes attach the variable as subscripts to avoid confusion, for example, if we need to specify that the variable is $x$, we shall denote $\mathcal{D}_{x}$ the usual space of test function.

**Definition.** Let $D_{x},D_{y},D_{x,y}$ be the spaces of test functions on $R_{x},R_{y}$ and $R_{x}\times R_{y}$ respectively. Let $S_{x},T_{y}$ be two distributions defined on $R_{x},R_{y}$ respectively. The `tensor product` $S\otimes T$, defined on $R_{x}\times R_{y}$, is defined uniquely by 
$$
\left\langle S_{x}\otimes T_{y},\phi(x)\psi(y) \right\rangle :=\left\langle S,\phi(x) \right\rangle \left\langle T,\psi(y) \right\rangle,\quad \phi\in D_{x},\quad \psi\in D_{y}.
$$
The tensor product is commutative. It belongs to $D^{\ast}_{x,y}$.

**Definition.** The convolution of two distributions $S,T$ on $\mathbb{R}_{x}$ is denoted by $S\ast T$, it is the unique (up to almost-everywhere relations) distribution that satisfies, for any $\phi(x)$ in $\mathcal{D}_{x}$
$$
\boxed{
\left\langle S\ast T, \phi(x) \right\rangle := \left\langle S_{x}, \left\langle T_{y},\phi(x+y) \right\rangle  \right\rangle .
}
$$
Note the variable of $\phi$ is $(x+y)$. It can be shown that convolution is commutative, $S\ast T=T\ast S$.

Similar to product of two distributions, **the convolution of two distributions is in general not a distribution.** It is because the support of $\phi(x+y)$ is in general not compact anymore on $\mathbb{R}^{2}$. To make the convolution mathematically rigorous, we first need to define the `support of a distribution`.

The support of a distribution is conceptually very much alike to the support of a function. The support of a regular function is a `closed set` on which the function is not null, similarly, the support of a distribution is a closed set on which the distribution is not null, in a sense to be elaborated in the following.

**Definition.** Let $\phi$ be a test function and $T$ a distribution. Let the support of $\phi$ be contained in an open subset $\Omega$ of $\mathbb{R}$. If for all $\phi$ we have $\left\langle T,\phi \right\rangle=0$, then the distribution is said to be `null` in $\Omega$. Find the largest open set on which $T$ is null, its **complement** is called the `support` of $T$. It is denoted by $\text{supp }T$ sometimes.

Although it is meaningless to say that "the distribution is null at $x_{0}$" since a point is $\mu$-negligible, it is meaningful to say "the distribution is null in a neighborhood of $x_{0}$" if the distribution in question is null at *any* open set containing $x_{0}$.

The null of Dirac $\delta$ distribution is the complement of the origin, thus the support of $\delta$ distribution is the origin. So are the derivatives of $\delta$. 

**Remark.** If the support of a distributions $T$ consists of only one point, say $x_{0}$, it does not mean that $\left\langle T ,\phi(x)\right\rangle$ only depends on $\phi(x_{0})$. For example, $\delta'$, the derivative of $\delta$ has support consists of $x_{0}=0$, however $\left\langle \delta',\phi \right\rangle = -\left\langle \delta,\phi'(x) \right\rangle = \phi'(0)$ is not determined by $\phi(0)$ alone. More generally, $\left\langle T,\phi \right\rangle$ does not depends on the values of $\phi$ taken on the support of $T$, but rather **on the neighborhood of the support of** $T$.

We can see that if the support of $T$ is compact, the linear form $\left\langle T,\phi \right\rangle$ is defined even when the support of $\phi$ is not bounded. Thus $\left\langle T,\phi \right\rangle$ is defined when $\text{supp }T \cap \text{supp } \phi$ is bounded.

Now we are ready to answer the question: when is the convolution of two distributions defined?

**Theorem.** Let $T$ be a distribution with bounded support, then for any other distribution $S\ast T$ is defined. Or, if the supports of both $S$ and $T$ are bounded from below (or both from above), then $S\ast T$ is defined.

In the first case, since the support of $T$ is bounded, the map
$$
x \mapsto \left\langle T_{y},\phi(x+y) \right\rangle 
$$
also has a bounded support in $x$, thus belongs to $\mathcal{D}$, which can be acted on by another distribution $S$.

In the second case, the intersection of the support of $x \mapsto \left\langle T_{y},\phi(x+y) \right\rangle$ and $T$ is bounded. 

Next we give some examples. It is easy to verify that 
$$
\delta \ast  T = T
$$
and 
$$
\delta' \ast  T = T'.
$$

The first shows that $\delta$ is the identity of the algebra of convolution of distributions. The second shows that, when looked at from right to left, derivative of a distribution can be regarded as a convolution. More generally, we have 
$$
T^{(p)} = \delta^{(p)} \ast  T.
$$

For distributions with unbounded support, the convolution, when it exists, may not be associative. For example, the support of $\theta$ is not bounded from above, and we have 
$$
(\theta \ast  \delta')\ast 1 = 1 \neq \theta\ast (\delta'\ast 1)=0.
$$

**For distributions whose support are all bounded from below or above, their convolution is always associative.**

We state without proof that, the exists, the derivative of convolution satisfies
$$
\boxed{
(S\ast T)' =S'\ast T = S\ast T'.
}
$$

That is, to differential a convolution we just need to differentiate one of the distributions. To prove it, it is helpful to use the Dirac $\delta$ distributions perspective of derivatives. Interested readers can use it as an exercise.

As an example, consider the electric potential due to a charge density $\rho$,
$$
V = \rho \ast \frac{1}{4\pi\epsilon_{0} r}
$$
then differentiate it twice we have 
$$
\nabla^{2}V =  \rho \ast \frac{1}{4\pi\epsilon_{0} }\nabla^{2} \frac{1}{r} = -\frac{\rho}{\epsilon_{0}}.
$$
Another useful example appears in solving the differential equation. Let 
$$
Du=f
$$
be a differential equation with constant coefficients. The distribution $g$ satisfying 
$$
Dg = \delta
$$
is called the `fundamental solution.` It is not unique since if there exists $h$ such that $D h = 0$, then $g+h$ is another fundamental solution. 

Once the fundamental solution is known, the solution can be immediately written down (at least formally) using convolution, i.e. $u=f\ast g$ is a solution of $Du=g.$

- - -

The convolution can be used to approximate certain functions by more differentiable ones. This technique can be used to show that certain sets of differential functions in $L^{p}$ were dense, it is known as the `regularization`, not to be confused with the regularization in quantum field theory. More generally, given a distribution $T$, it is possible to find an infinite sequence of $C^{\infty}$ functions whose limit in $D^{\ast}$ is $T$. This result is a consequence of the following theorem.

**Theorem.** Let $T$ be a distribution and $\phi$ a test function. The convolution $T\ast\phi$ is an $C^{\infty}$ function defined by 
$$
\boxed{
(T\ast \phi)(x) = \left\langle T(y),\phi(x-y) \right\rangle .
}
$$
The differentiation of $T\ast\phi$ can be shown to be
$$
\frac{d^{m}}{dx^{m}} (T\ast \phi) = T \ast   \left( \frac{d^{m}}{dx^{m}} \phi \right).
$$

We state without proof the theorem,

**Theorem.** The space $\mathcal{D}$ regarded as a subset of $\mathcal{D}^{\ast}$ is `dense` in $\mathcal{D}^{\ast}$.


## Fourier Series

A distribution $T$ is said to be `periodic` if there exists a real number $a$, called the period of $T$, such that the translation of $T$ is the same as $T$, $\tau_{a} T = T$.

This definition means that, for any test function $\phi$, we have 
$$
\left\langle T,\phi(x+a) \right\rangle  = \left\langle \tau_{-a}T,\phi(x) \right\rangle =\left\langle T,\phi(x) \right\rangle
$$
Let $D(\mathbb{S}^{1}_{a})$ be the space of functions defined on a circle with length $a$. To a function $f\in D(\mathbb{S}^{1})$ we may associated a regular periodic distribution $T_{f}$, with periodic $a$. Note that $f$ has a bounded support, for $\mathbb{S}^{1}$ is bounded.

In this section we shall only consider the periodic distributions in $D^{\ast}(\mathbb{S}^{1})$.

**Definition.** Let $T$ be a distribution in $D^{\ast}(\mathbb{S}^{1})$ , the number
$$
c_{k}(T):=\frac{1}{a} \left\langle T_{s}, \exp- \frac{2\pi iks}{a}  \right\rangle ,\quad k\in \mathbb{Z}
$$
where $a$ is the period of $T$, is called the `Fourier coefficient` of $T$, and the series
$$
\sum_{k\in \mathbb{Z}}c_{k}(T) \exp \frac{2\pi iks}{a}
$$
is called the `Fourier series` of $T$.

For example, the Fourier coefficient of $\delta$ is simply $1 / a$. 

After everything we have said about convolution of distributions, a natural question to ask is, what is the Fourier coefficients of the convolution of two distribution. A straight computation shows that i**t is equal to $a$ times the product of the corresponding Fourier coefficients of the two distributions.**

## Fourier Transform of Tempered Distribution

Recall that the` Fourier transform` of a function is 
$$
\widetilde{f}(k) = \int_{-\infty}^{\infty} dx \,  f(x)e^{ -ikx }
$$

and the inverse is 
$$
f(x) = \int_{-\infty}^{\infty} \frac{dk}{2\pi} \, \widetilde{f}(k) e^{ ikx }.
$$
The convention we used is widely adopted in physics, but sometimes it makes certain formulae less symmetric. 

Sometimes we use $\mathcal{F} [f(x)]$ or $\mathcal{F}[f]$ for short to denote the Fourier transform of $f(x)$, $\mathcal{F}$ can be regarded as the operator of Fourier transform. $\mathcal{F}[f(x)]$ itself is a function of $k$, thus we sometimes write it as $F[f](k)$. Similarly the inverse Fourier is sometimes written as $f(x) = \mathcal{F}^{-1}[\widetilde{f}(k)]$. 

Note that with our convention, $\mathcal{F}^{2}\neq 1$, in contrast to some conventions used by, e.g. Boccara's textbook.

- - -

The Fourier transform has a number of elementary properties. It is a `linear` transform, namely 
$$
\mathcal{F}[c_{1}f_{1}+c_{2}f_{2}]=c_{1}\mathcal{F}[f_{1}]+c_{2}\mathcal{F}[f_{2}].
$$

The translation in $x$ corresponds to a phase factor to the Fourier transform, 
$$
\mathcal{F}[f(x+a)](k) = e^{ -iak }\mathcal{F}[f](k).
$$
The converse is also true, a phase factor in $f$ corresponds to a translation in $k$,
$$
\mathcal{F}[e^{ ilx }f](k)=\mathcal{F}[f](k-l).
$$

The scaling property is 
$$
\mathcal{F}[f(cx)] = \frac{1}{\left\lvert c \right\rvert } \mathcal{F}[f(x)].
$$

The Fourier transform of convolution is particularly useful,
$$
\mathcal{F}[f \ast g] = \mathcal{F}[f]\mathcal{F}[g].
$$


The most useful property of Fourier transform is probably that it *turns derivative to multiplication*,
$$
\mathcal{F}[f'(x)] = ik\mathcal{F}[f(x)].
$$
Note that for this relation to work, $f(x)$ must decay at $\left\lvert x \right\rvert\to \infty$, otherwise there will be surface terms.

- - -

A further important property of Fourier transform is that it preserves the $L^{2}$ inner product between two functions, up to a multiplicative factor. Let $f,g$ be two complex-valued functions, we have
$$
\begin{align}
\left\langle f,g \right\rangle  & = \int dx \, f^{\ast }(x) g(x) \\ \\
&= \int dx \, f^{\ast }(x) \int \frac{dk}{2\pi} \, e^{ ikx }\widetilde{g}(k) \\
&= \frac{1}{2\pi}\int dk \, \widetilde{g}(k)\left[ \int dx \, e^{ -ikx } f(x)  \right]^{\ast } \\
&=\frac{1}{2\pi}\int dk \, \widetilde{f}^{\ast }(k)\widetilde{g}(k) \\
&=\frac{1}{2\pi}\left\langle \widetilde{f},\widetilde{g} \right\rangle 
\end{align}.
$$
Or, if we regard variable $k$ as momentum, and define the inner product of two function in momentum representation as
$$
\left\langle f,g \right\rangle_{p} := \int \frac{dp}{2\pi} \, f(p)g(p) 
$$
where $\left\langle - , - \right\rangle_{p}$ denotes the inner product in momentum space, then we could write
$$
\left\langle f(x),g(x) \right\rangle _{x} = \left\langle \widetilde{f}(p),\widetilde{g}(p) \right\rangle _{p}.
$$
In our note we will not use this convention, for it introduces unnecessary complication.

*Everything we have said above can be directly generalized to higher dimensions.* 

- - -

Now, we have leant that distributions are not functions, test functions live in the space $\mathcal{D}$ while distributions live in the dual space $\mathcal{D}^{\ast}$. How should be define the Fourier transform of distributions, if we can at all? A natural idea is to define how a Fourier transformed distribution would act on a test function.

As a start, consider two functions, direct computation shows that
$$
\left\langle \mathcal{F}\phi,\mathcal{F}\psi \right\rangle =2\pi \left\langle \phi,\psi \right\rangle \implies \left\langle F\phi,\chi \right\rangle = 2\pi \left\langle \phi,\mathcal{F}^{-1}\chi \right\rangle 
$$
where $\chi=\mathcal{F}\psi$. 

Follow this path we define the Fourier transform of a distribution as follows.

**Definition.**  The `Fourier transform of a distribution` $T$, denoted by $\widetilde{T}$, is defined by 
$$
\boxed{
\left\langle \widetilde{T}_{p},\phi(p) \right\rangle := \left\langle T_{x},2\pi \mathcal{F}^{-1}\phi \right\rangle .
}
$$
Note that the variable of $T$ is $x$, the same as the function $\mathcal{F}^{-1}\phi$, while the variable of $\widetilde{T}$ and $\phi$ is $p$.

The problem is that, the definition is meaningless for arbitrary distribution $T$, since sometimes $\mathcal{F}^{-1} \phi$ might not belong to $\mathcal{D}$. In other words, the Fourier transform of an arbitrary distribution in $\mathcal{D}^{\ast}$ may not in $\mathcal{D}^{\ast}$. Thus, we need to restrict the distributions in the context of Fourier distributions. 

L. Schwartz defined a special class of test functions, denoted by $\mathcal{S}$. If a function is in $\mathcal{S}$, we want its (inverse-) Fourier transform also to be in $\mathcal{S}$. It is less obvious but, since Fourier exchanges multiplication and differentiation, thus in order for the derivative and multiplication of distributions to be well defined, $\mathcal{S}$ needs to be invariant under i) differentiation and ii) multiplication by polynomials. Thus we define the space $\mathcal{S}$ to be the set of all $C^{\infty}$ functions such that
$$
\text{sup }\left\lvert x^{m}\phi^{(n)}(x) \right\rvert <\infty,\quad m,n\in\mathbb{Z}^{+}
$$
where $\phi^{(n)}$ is the n-th derivative of $\phi(x)$. The functions in $\mathcal{S}$ do not necessarily have bounded supports, but are required to go to zero as $\left\lvert x \right\rvert\to \infty$, faster than $x^{-n}$ for any integer $n$. The same goes for any order of derivatives of $\phi$. In terminologies, $\mathcal{S}$ is the space of `rapidly decreasing` test functions.

A simple example of a function in $\mathcal{S}$ is $p(x)e^{ -x^{2} }$, where $p(x)$ is a polynomial function in $x$. 

If $\phi_{n}$ is a sequence of functions in $\mathcal{D}$, if it converges to a function $\phi$ in $\mathcal{S}$, pointwise convergence is not enough, the derivative and multiplications also need to converge to $\phi$, namely 
$$
\lim_{ n \to \infty } \text{sup }\left\lvert x^{m}(\phi_{n}^{(p)}(x)-\phi^{(p)}(x)) \right\rvert=0
$$
for any positive integer $m$ and $p$. 

Note that $\mathcal{D}$ is contained in $\mathcal{S}$, for any functions with compact support certainly satisfies the condition of rapidly decreasing, or the Schwartz condition.

The continuous linear forms on $\mathcal{S}$ are important enough to deserve its own name, they are called `tempered distributions`, denoted by $\mathcal{S}^{\ast}$. It is contained in $\mathcal{D}^{\ast}$. There are fewer tempered distributions than distributions. 

Forget about test functions, it turns out that tempered distributions can be applied to a much wider class of functions. Thanks to the rapid decreasing of function in $\mathcal{S}$, distributions in $\mathcal{S}^{\ast}$ can be applied to any (real) functions such that there exists a positive integer $m$ and a positive real number $A$, such that 
$$
\left\lvert f(x) \right\rvert \leq A \left\lvert x \right\rvert ^{m}, \quad 
$$
such functions are said to be of `slow growth at infinity`. 

**The Fourier transform of a tempered distribution is another tempered distribution.** This fact allows us to define the Fourier transform of any tempered distribution.

As an example, consider the Fourier transform of Dirac $\delta$ distribution. It's easy to verify that $\delta$ satisfies the Schwartz condition thus is a tempered distribution. Then we know its Fourier transform exists. In a not mathematically rigorous way, regarding $\delta$ as a (uniform) limit of regular functions, then direct computation show that
$$
\mathcal{F}[\delta] = \int_{-\infty}^{\infty} dx \, \delta(x) e^{ -ikx }=1. 
$$
This can serve as a reference. 

Follow the strict definition of the Fourier transform of distribution, we have 
$$
\left\langle \mathcal{F}\delta,\phi \right\rangle =2\pi \left\langle \delta,\mathcal{F}^{-1}\phi \right\rangle ,
$$
using the definition of $\delta$ and inverse Fourier transform we have 
$$
2\pi \left\langle \delta,\mathcal{F}^{-1}\phi \right\rangle = 2\pi \left\langle \delta_{k}, \frac{1}{2\pi}\int_{-\infty}^{\infty} dk \, \phi(k)e^{ ikx }  \right\rangle 
$$





