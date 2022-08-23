---
layout:     post   				    # 使用的布局（不需要改）
title:      The Nullstellensatz and the Geometry of Spec A	# 标题 
subtitle:    #副标题
date:       2022-08-23 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/mathArt2.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - math
    - abstract algebra
    - ring
---

## Field Extensions

A field has characteristic either zero or a prime number $p$. Recall that the characteristic of a field is defined by the minimum number of how many unit elements we can add together to get 0, for example, if the characteristic is N, then we have 
$$
 \underbrace{1+1 \dots +1}_{N} = 0.
$$
For example, $\mathbb{Z}_{5}$ has characteristic 5 since $1+1+1+1+1 = 5 = 0$, $\mathbb{Q}$ has characteristic zero.

Let $k\subset K$ be both fields, we shall say that $K$ is an *extension* of $k$ and $k$ a subfield of $K$. 

If $K,K'$ are two fields, then any homomorphism $\phi: K \to K'$ is either isomorphism or trivial. It is because $\text{ker} \phi$ is an ideal in $K$, and only ideals in $K$ are either 0 or $K$ itself. 

- A field of characteristic zero has a subfield isomorphic to $\mathbb{Q}$ and a field of characteristic $p>0$ has a subfield isomorphic to $\mathbb{Z}_{p}$.

To understand it, just consider the case where there is a map from the ring of integers (or algebraic integers, they are the same things) to some field, and consider the kernel of the map.

Let $K / k$ be a field extension. We shall identify the elements of $K$ and $k$ and denote the common unit element by 1. $K$ has over $k$ the structure of a vector space, for example if $y_{1} \notin k$, then $y_{1} \times k$ are elements in $K$ but not in $k$, and $y_{1}$ can be considered as a base. If the basis $y$'s are finite(infinite), we say that K has finite(infinite) basis over $k$, the extension $K / k$ is called a finite or infinite extension.  The number of basis is called the *degree* of $K$ over $k$ and denoted by $(K : k)$. 

Let $K / k$ be an extension and $\alpha \in K$. Consider the ring $k[x]$ of polynomials in $x$ over $k$. For any $f(x) \in k[x]$, $f$ is an element of $k[x]$ and $f(x)$ of $K$. Given an element $\alpha$ of $K$, we could ask the question that what polynomials have zero value at $\alpha$. Denote the set of such polynomials $I(\alpha)$, apparently they form an ideal since the multiplication or addition of two such polynomials still has zero value at $\alpha$. If $I(\alpha)$ is empty, we say $\alpha$ is **transcendental**, otherwise we can $\alpha$ is **algebraic**, over $k$. We sum it up as following.
- Let $K / k$ be an extension field. $\alpha\in K$ is said to be algebraic over $k$ if $\alpha$ is root of some non-zero polynomial in $k[x]$. Otherwise it is said to be transcendental.
The following are some related concepts.
- The ideal of $\alpha$ over $k$ is the set of polynomials with zero value at $\alpha$,
- the irreducible polynomial $\varphi(\alpha)$ is the generator of the ideal of $\alpha$,
- the monic polynomial obtained from $\varphi(\alpha)$ by multiplying a suitable field element is called the minimum polynomial of $\alpha$.

We now define an extension $K / k$ to be algebraic over $k$ if every of $K$ is algebraic over k. In the contrary case $K$ is said to be transcendental extension of k. For example, $\mathbb{C} / \mathbb{Q}$ is algebraic. 


## Weak Nullstellensatz

Let $k$ be a field,  and consider the polynomial ring $k[X_1,\dots,X_n]$. For any maximal ideal $m$, the residue field $K =k[X_{1},\dots,X_{n}] / m$ is a finite algebraic extension of k. Suppose in addition that $k$ is algebraically closed, then $k = K$. 

The maximal ideals of $A = k[X_{1},\dots,X_{n}]$ are of the form 
$$
m = (X_{1}-a_{1},\dots, X_{n} - a_{n}),\quad a_{i} \in k.
$$
Take $A=k[X]$ for example, $X-a_{1}$ is irreducible, $X^2+a_{2}X+a_{3}$ is not irreducible since $k$ is closed and $X^2+a_{2}X+a_{3}=0$ always has roots so we can always reduce it. Thus $(X-a_{1})$ is the maximal ideal.

## Definition of a variety

Let $k$ be a closed field. A *variety* is a subset of $k^n$, a geometric shape of the form 
$$
V = V(J) = \{ (a_{1},\dots,a_{n}) | f(a_{1},\dots,a_{n})=0 \text{ for all } f\in J  \},
$$
where $J$ is an ideal of $k[X_{1},\dots,X_{n}]$. Note that $J=(f_{1},\dots,f_{n})$ is finitely generated. The variety of $J$ is nothing but the zero locus of $f_{1},\dots,f_{n}$. 

Every maximal ideal corresponds to a point in $k^n$. In other words, there is a 1-2-1 correspondence 
$$
  V(J) \longleftrightarrow \text{m-Spec}, \text{ given by } (a_{1},\dots,a_{n}) \longleftrightarrow (x_{1}-a_{1},\dots,x_{n}-a_{n}),
$$
where m-Spec is the set of maximal ideals.

## The correspondences V and I

A variety $X \subset k^n$ is by definition the same as $V(J)$ for some ideal $J$. We can regard V as a function that maps an ideal to its variety. There is another function doing the inverse: maps a variety to an ideal:  
$$
  I: \{ \text{subsets X of } k^n \} \to \{ \text{ideals of } k[X_{1},\dots,X_{n}]\},
$$  
defined by taking a variety into the *maximal* ideal.

But, what is the relation between $V(J)$ and the corresponding maximal ideal, namely $I(V(J))$? Are the always the same? That question is answered by 

**Theorem** (**Nullstellensatz**) Let k be an algebraically closed field.
1. If $J \subset k[X_{1},\dots,X_{n}]$ but $J \neq k[X_{1},\dots,X_{n}]$, then $V(J) \neq 0$.
2. $I(V(J)) = \text{rad} J$.

## Irreducible variety

A variety is irreducible if it is non-empty and not the union of two proper subvarieties, 

**Proposition** A variety $X=V(J)$ is only irreducible if $I(X)$ is prime, namely irreducible.  

<center>
<img src="https://i.upmath.me/svg/%0A%5Cbegin%7Btikzcd%7D%0A%09%7B%5Ctext%7Bradical%20ideal%20%7D%20j%7D%20%26%26%20%7B%5Ctext%7Bvarieties%20%7DX%5Csubset%20k%5En%7D%20%5C%5C%0A%09%5C%5C%0A%09%7B%5Ctext%7Bprime%20ideal%20%7D%20P%7D%20%26%26%20%7B%5Ctext%7Birreducible%20varieties%20%7DX%5Csubset%20k%5En%7D%0A%09%5Carrow%5B%22%5Ccup%22%2C%20from%3D3-1%2C%20to%3D1-1%5D%0A%09%5Carrow%5B%22%5Ccup%22%2C%20from%3D3-3%2C%20to%3D1-3%5D%0A%09%5Carrow%5Btail%20reversed%2C%20from%3D1-1%2C%20to%3D1-3%5D%0A%09%5Carrow%5Btail%20reversed%2C%20from%3D3-1%2C%20to%3D3-3%5D%0A%5Cend%7Btikzcd%7D%0A" alt="
\begin{tikzcd}
	{\text{radical ideal } j} &amp;&amp; {\text{varieties }X\subset k^n} \\
	\\
	{\text{prime ideal } P} &amp;&amp; {\text{irreducible varieties }X\subset k^n}
	\arrow[&quot;\cup&quot;, from=3-1, to=1-1]
	\arrow[&quot;\cup&quot;, from=3-3, to=1-3]
	\arrow[tail reversed, from=1-1, to=1-3]
	\arrow[tail reversed, from=3-1, to=3-3]
\end{tikzcd}
" />
</center>

Therefore, Spec $k[X_{1},\dots,X_{n}]$ corresponds to the irreducible varieties.

## The Zariski topology on a variety

The varieties form  the *closed* sets of a topology on $k^n$, since 
- The union of two varieties is again a variety,  
$$
V(I) \cup V(J) = V(I\cap J) = V(IJ),
$$
- The intersection of any varieties is again a variety,   
$$
\cap X_{i} = V\left( \sum J_{i} \right)
$$  
The Zariski topology on a variety Y is defined by taking the subvarieties $X \subset Y$ as the closed sets.

The Zariski topology is a very weak topology, that is, it has very few closed sets.
