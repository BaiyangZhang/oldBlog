---
layout:     post   				    # 使用的布局（不需要改）
title:      Basic Measure Theory 				# 标题 
subtitle:    #副标题
date:       2022-08-02 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/functionalAnalysis.png 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - math
    - functionalAnalysis
    - distribution
    - measureTheory
---

### Pointwise Convergence vs. Uniform Convergence

At the end of the 19th century, mathematicians extensively discussed weather you could take the limit out of the integral (Riemannian integral, to be exact), namely weather we have 
$$
\int_{-\infty}^{\infty} \lim_{ n \to \infty } f_{n}(x) \, dx 
=\lim_{ n \to \infty } \int_{-\infty}^{\infty} f_{n}(x) \, dx.
$$

Here $f_{n}$ is a **non-uniformly** convergent sequence of functions which are Riemann-integrable. Recall the meaning of uniformly convergence,

**Definition.** A sequence of functions $\left\{ f_{n}(x) \right\}$ is said to converge uniformly to $f$ on a set $S$ if for every $\epsilon > 0$ there exists an N such that for all $n>N$ we have 
$$
\text{sup}\left| f_{n}(x) - f(x) \right| < \epsilon \, \text{ for all } x\in S, 
$$

where sup is the supremum. Uniform convergence means that for a given $\epsilon$, one $N$ works for every $x$. You can regard $\left| f_{n}(x) - f(x) \right|$ as a set where each element is given by different $x$, then sup$\left| f_{n}(x) - f(x) \right|$ is the supremum of this set. 

*Uniform convergence* is in contrast to *pointwise convergence*. Pointwise convergence means that  $\lim_{ n \to \infty } f_{n}(x) = f(x)$ for every $x$ in the domain of $f$. Note that, this limit process is defined at each point, namely for every $x$, there exists $N(x)$ which depends on $x$, such that $\left| f_{n} - f \right|,\,n>N$ is smaller than a given $\epsilon$. This is different from the uniform convergence, where the $N$ is independent of $x$, once $N$ is given it must apply for all $x$ in the domain. 

Uniform convergence is a stronger condition than pointwise convergence, especially that uniform convergence preserves the **continuity**,

**Theorem** If the functions $f_{n}$ are continuous and they uniformly converges to $f(x)$, namely 
$$
\lim_{ n \to \infty } \text{sup} \left| f_{n}(x) - f(x) \right| = 0,
$$

Then $f(x)$ is also continuous on the domain.

Interested readers may find the proof somewhere else, but note that the proof uses the key important property that $N$ in the $\epsilon-N$ language is independent of $x$. 

On the other hand, pointwise convergence does not preserve continuity. We will give an example that is pointwise convergent (which is the weaker condition) but not uniformly convergent (which is the stronger condition). 

Consider function
$$f_{n}(x) : x \mapsto x^n$$

defined on $[0,1)$ . Since as long as $x<1$, there exists $N$ such that $x^n < \epsilon$, $f_{n}$ pointwise converges to step function $x \mapsto 0$ on $[0,1)$ and $f(1) = 1$. However, we know that that can't be the case for uniform convergence since $f_{n}(x)$ is continuous on $[0,1]$ but the step function is not, and uniform convergence must preserve the continuity. Indeed, given $N\in \mathbb{N}$, no matter how large it is, there exists $\delta$ small enough such that $(1-\delta)^N = f_{N}(1-\delta)$ is some value between 0 and 1. So, the set made by $f_{N}(x) - 0$ on $[0,1)$, namely $\{ f_{N}(x) - 0 \mid x \in [0,1)  \}$ is $[0,1)$ and the supremum of it is not zero everywhere, hence there is no uniform convergence. 

Anyway, after some close analysis of integrals, Lebesgue and others came up with their theory of integration. Lebesgue's integration is more general and better adapt to deal with limit processes.

The concept of **measure** plays a crucial role in Lebesgue's definition of the integral. A measure is a generalization of the concept of length, and there are more than one way to define measure, they all need to satisfy certain conditions, the so-called $\sigma$-algebra.

### When is a Function Measurable?

In physics, it is very unlikely that one would have to deal with nonmeasurable functions, but still, we should rigorously define what is means to be measurable. 

Suppose that we want to measure the length of the set of all the real numbers, namely the real number axis. Any interval if endowed with certain length, there is no problem measuring that. The union of some measurable intervals also has a well-defined length, there is no problem measuring that as well. The intersection of some measurable intervals are trickier, what if the intersection is just a point? Can you measure the length of a point? Is it zero? Hmm... let's postpone the discussion on that and ignore it for now. What about the complement of a measurable interval? Obviously, **if the full set is measurable**, then the complement of an interval should also be measurable. In light to be these discussions, we define the so-called $\sigma$-algebra,

A class $\mathcal{A}$ of subsets of $X$ is said to be a $\sigma$-algebra (sigma algebra) in $X$ if 
1. $X$ belongs to $\mathcal{A}$, meaning there is no element in $X$ left,
2. any **countable** unions of elements of $\mathcal{A}$ belongs to $\mathcal{A}$,
3. the complement of any elements in $\mathcal{A}$ is also in $\mathcal{A}$.

Note that the so-called sigma algebra is a class of sets with extra structures, so it makes sense to say something is in the sigma algebra.

From these properties it follows that 
-  $\sigma$-algebra is also closed under countable intersection.
- $\emptyset$ is in $\mathcal{A}$ since it is the complement of $X$. 
- If $A,B$ belong to $\mathcal{A}$, then $A - B = A\cap(B^C)$ is in $\mathcal{A}$, 
- If $A,B$ belong to $\mathcal{A}$, then $A \Delta B$ is also in $\mathcal{A}$, where $A\Delta B$ is the symmetric difference of $A$ and $B$, namely all the elements that are either in $A$ or $B$ but not in both $A$ and $B$. In set language, $A\Delta B = (A-B)\cup(B-A)$.

You will find that the definition of sigma algebra is similar to the definition of topology. However there is an essential difference: the complement of a sigma algebra is in the sigma algebra, while in topology the complement of an open set is defined to be a closed set, **not** a open set. Confusing enough, in topology some sets can be both open and closed, they even invented a word for it called clopen. 

Back to $\sigma$-algebra. Le $\mathcal{E}$ be a class of subsets of $X$. 

**Definition** The smallest $\sigma$-algebra containing $\mathcal{E}$ is the $\sigma$-algebra generated by $\mathcal{E}$, denoted $S(\mathcal{E})$.

It means that everything in $\mathcal{E}$ is also in the $\sigma$-algebra. $S(\mathcal{E})$ consists of all the subsets of $X$ that can be made from elements of $\mathcal{E}$ by a countable union, complement and intersection. For example, if $\mathcal{E}$ is empty, then $S(\mathcal{E}) = \{ \emptyset, X \}$.  



**Theorem** Let $f: X \to Y$, $\mathcal{B}$ a $\sigma$-algebra in $Y$, then $\mathcal{A} := f^{-1} \mathcal{B}$ is a $\sigma$-algebra in $X$. 

The reader can check that $\mathcal{A}$ does satisfy all the requirements for a $\sigma$-algebra. For example, since $Y$ is contained in $\mathcal{B}$, and $f$ maps the entirety of $X$ to $Y$, then $f^{-1} \mathcal{B}$ contains $X$. 

**Definition** If $\mathcal{A}$ is a $\sigma$-algebra of $X$, then the pair $(X,\mathcal{A})$ is called a measurable space, and the elements of $\mathcal{A}$ are called measurable sets. 

Accordingly, given a map $f$ from $(\mathcal{A},X)$ to $\mathcal{B},Y$, it is said to be a $\mathcal{A}-\mathcal{B}$ measurable map, or just a measurable map if there is no confusion, if the preimage of a measurable set in $\mathcal{B}$ is a measurable set in $\mathcal{A}$. This is very similar to the definition of a continuous map in topology, where a continuous map means that the preimage of a open set is also open. 

**Theorem** Let $f:(X,\mathcal{A}) \to (Y,\mathcal{B})$, and let $\mathcal{E}$ be a class of subsets of $Y$ generating the $\sigma$-algebra on $\mathcal{B}$; then $f$ is measurable if $f^{-1}(\mathcal{E})$ is a subset of $\mathcal{A}$.

We already know that the $\sigma$-algebra generated by $\mathcal{E}$ is made from countable times of union, intersection and complement operations, the the inverse map $f^{-1}$ preserves these operations, for instance, for $B_{1,2} \subset Y$, we have
$$
f^{-1} (B_{1} \cup B_{2}) = f^{-1} (B_{1}) \cup F^{-1}(B_{2}) .
$$

Hence we have 

**Lemma** Let $f:X\to Y$, and let $\mathcal{E}$ be a class of subsets of $Y$, then 
$$
f^{-1}(S(\mathcal{E})) = S(f^{-1} (\mathcal{E})).
$$

We can define the product of the measurable spaces. Let $(X,\mathcal{A}), (Y,\mathcal{B})$ be two measurable spaces, then the space $(X \times Y)$ with $\sigma$-algebra generated by $\mathcal{A} \times \mathcal{B}$ is called the product of the measurable spaces. In the product space, the measurable sets are given by the products of two measurable sets, that is intuitive. 


After all the definitions and theorems, let's actually try to construct a $\sigma$-algebra. One of the most famous example is the *Borel set*. Given a topological space $X$ with a set $\mathcal{O}$ of open sets, the $\sigma$-algebra $\mathcal{B}$ of $X$ is defined to be generated by $\mathcal{O}$.  The measurable set in $\mathcal{B}$ are called Borel sets of $X$. Since the complement of open sets are close sets, and the complement of a measurable set is also measurable, it follows that the close sets are also measurable.  So are all the countable intersection and unions of the open and closed sets. If $X = \mathbb{R}$, the $\sigma$-algebra $\mathcal{B}$ is generated by the set $(a,\infty)$.

Any topological space can be regarded as measurable sets where the Borel sets play the role of $\sigma$-algebra. Let $X,Y$ be two topological spaces, a measurable map $f:X\to Y$ is said to be Borel measurable. For instance, any continuous map is Borel measurable. 

A function is in general a map from any space $X$ to $\mathbb{R},\mathbb{C}$. Convince yourself that a function is measurable if for any $a \in \mathbb{R}$, the set $\{ x \mid f(x) >a \}$ is measurable. Here we treat $\mathbb{R}$ as a measurable set with Borel sets as its $\sigma$-algebra, then measurable functions are just special kinds of measurable maps. Then the set $\{ x \mid f(x) \geq a \}$ is also measurable, hence the set $\{ x\mid f(x) = a \}$ is a Borel set.

**Definition** The characteristic function $1_{A}$ of a set $A$ is defined as
$$
1_{A}(x) = 
\begin{cases}
1  & x\in A, \\
0  & x \notin A.
\end{cases}
$$

And $1_{A}$ is only measurable if $A$ is measurable. 

A complex function is measurable if both the real and imaginary parts are measurable respectively. 

**Theorem** Let $f,g$ be measurable function from $X$ to $\mathbb{R}$ (or $\mathbb{C}$).

1. for any $\alpha \in \mathbb{R}^+$, $\left| f \right|^\alpha$ is also measurable,
2. if ${1}/{f}$ is defined everywhere, it is also measurable,
3. $f+g, fg$ are both measurable. 

Before we continue with more measure theory, we stop to introduce some more terminologies. Given a partially ordered set $P$. Partially ordered sets, or posets, means that  not every pair of elements needs to be comparable, as compare to total orders, in which every pair of elements are comparable. For a subset $S$ of $P$, we define

- Supremum. The supremum of $S$, $\text{sup } S$ is the least element of $P$ that is greater than or equal to each element in $S$. It is sometimes referred to as the least upper bound (LUB).
- Infimum. The infimum of $S$, $\text{inf } S$ is the largest element of P that is smaller than or equal to each element in $S$. It is sometimes referred to as the greatest lower bound (GLB). 

Note that neither $\text{sup } S$ or $\text{inf }S$ needs not to be in $S$, as contrast to minimum and maximum.  Supremum and infimum are more useful in analysis because they apply to special sets which may not have maximum or minimum. For example, the set of positive real numbers $\mathbb{R}^+$ (not including 0) does not have a minimum, since any element in $\mathbb{R}^+$ can be divided by two resulting in a smaller number still in $\mathbb{R}^+$. However $\mathbb{R}^+$ does has exactly one infimum, 0.

There are a pair of related concepts, lim sup and lim inf. Let $s_{n}$ be a sequence in $\mathbb{R}$, we define 

$$
\text{lim sup } s_{n} = \lim_{ N \to \infty } \text{sup } \{ s_{n} \mid n>N \}
$$

and 
$$
\text{lim inf } s_{n} = \lim_{ N \to \infty } \text{inf } \{ s_{n} \mid n>N \}.
$$

In other words, lim sup and lim inf of a sequence is the supremum or infimum of all the terms larger than $N$, where $N$ is taken to be $\infty$ eventually. 

**Definition** Let $\phi$ be a function which is 
1. measurable, and
2. only takes finite number of values,   
then $\phi$ is said to be a simple function. 

For instance, if $A$ is a measurable set, then the characteristic function $1_{A}$ is a simple function. 

The sum and product of two simple functions are simple functions. 

**Theorem** Any measurable function is the limit of a sequence of simple functions. 

This is similar in the case of Riemann integral of a function. 

### Positive Measure

Measure is the generalization of concepts such as length, weight, probability. Thus it is natural to supposed the the measure assign to a set to be positive definite. 

**Definition**  Let $(X,\mathcal{A})$ be a measurable space, a *positive measure* on $(X,\mathcal{A})$ is a mapping $\mu:\mathcal{A}\to \overline{R}^+$ such that
1. the measure of the empty set is zero, $\mu(\emptyset) = 0$.
2. If $\{A_{n}\}$ is a countable collection of pairwise disjoint elements of $\mathcal{A}$, then 
$$
\mu\left(\bigcup_{n}A_{n}\right) = \sum_{n} \mu(A_{n}).
$$

The triple $(X,\mathcal{A},\mu)$ is called a measure space. Recall that $(X, \mathcal{A})$ , namely a space with a sigma algebra, is called a measurable space. A tiny and perhaps insignificant difference in naming. 

Note that property number 2 is sometimes called $\sigma$-additivity, it is crucial to measure space. 

There are different quantities which can be used as measure, may it be the length, weight, probability, etc. Thus there exists different ways to construct measure spaces. Below we provide some example of measure spaces. 

- **Counting measure**. Given a space $X$, for any subset $A\subset X$, define $\mu(A)$ to be she number of points in $A$ if A is finite, $\mu(A) = \infty$ if $A$ is infinite. This is called the counting measure on $(X,\mathcal{A})$.
- **Dirac measure**. Let $X,\mathcal{A}$ be a measure space, and $a\in X$ a fixed point in X. For any set $A$, define $\mu(A) = 0$ if point $a$ is not in set $A$, $\mu(A) = 1$ if $a$ is in $A$. 
- **Lebesgue measure**. Lebesgue measure is essential to define Lebesgue integral. Given a function from $\mathbb{R}$ to $\mathbb{R}$, we need to generalized the concept of length for a given subset of $\mathbb{R}$, no matter how weird it is, such as the set of all the rational points. On the other hand, the generalized concept of length should be invariant under translation, and satisfy other naturalness requirements. Let $A$ be a subset of $\mathbb{R}$, we first find some open sets to cover $A$ fully, namely find $I_{j},j\in J$ so that $A \subset \cup_{j\in J} I_{j}$, where $J$ is some index set. Note that $I_{j}, j\in J$ is *not* a partition of $A$, far from it, the unions of all the $I_{j}$ just need to cover $A$. As you can imagine, the unions of all the $I$'s will most likely over-cover $A$, then if we sum the measure of all $I$'s, we will get a measure which is larger than the measure of actual $A$. The real size, or measure, of $A$ is roughly speaking given by the lower bound of the measure of all the possible $I_{j}$'s. Out of this spirit we define the outer measure of $A$,
$$
m^\ast (A) = \text{inf } \sum_{j\in J} l(I_{j})
$$

where $l(I)$ denotes the length of $I$, and the infimum is taken over all finite or countable collections of open intervals $\{ I_{j} \mid j\in J \}$ such that $A\subseteq \cup_{j\in J} I_{j}$. Although the outer measure is not really a measure, it still satisfies some of the properties that real measures satisfy, for instance,
1. $m^\ast(\emptyset) = 0$,
2. $m^\ast(A) \geq 0$,  
3. $m^\ast(\{ x \}) = 0$, the length of a single point is zero.

Note that the outer measure is defined for all subsets of $\mathbb{R}$, no matter how weird they are, since any subset of $\mathbb{R}$ can be cover by some open sets. 

We then define the inner measure of $A$, which in a sense is the dual notion of outer measure. The outer notion approaches the real size of $A$ from above, and the inner measure approaches the real size of $A$ from below. The inner measure of $A$ is 
$$
	m_{\ast } (A) = \text{sup } m^\ast (K), \quad K \text{ is closed and } K\subseteq A, 
$$

The supremum is taken over all such subsets $K$. For any $A$ we have $m_{\ast} A \leq m^\ast(A)$.

A subset $A\subset \mathbb{R}$ is said to be Lebesgue measurable if 
$$
m_{\ast } A = m^\ast  A < \infty.
$$

This finite number is called the Lebesgue measure of $A$. It is denoted $m(A)$, $m$ for measure.  the Lebesgue measure is the real size of $A$. 

 
