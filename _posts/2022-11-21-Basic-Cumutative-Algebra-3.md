---
layout:     post   		                    # 使用的布局（不需要改）
title:      Basic Commutative Algebra		# 标题 
subtitle:   Class 3
date:       2022-11-21 				        # 时间
author:     Baiyang Zhang 					# 作者
header-img: img/mathArt8.jpg 	            # 这篇文章标题背景图片
catalog: true 			        			# 是否归档
tags:							        	# 标签
    - Math
    - Commutative Algebra
    - Notes
---



On the other hand, clearly $({\frak ab})\subseteq({\frak a})\cap({\frak b})$, thus if $({\frak a}+{\frak b})=(1)$ then we have both  $({\frak a}\cap {\frak b}) \subseteq ({\frak ab})$ and $({\frak ab})\subseteq({\frak a})\cap({\frak b})$, hence $({\frak ab}) = ({\frak a})\cap({\frak b})$.

**Definition.** Two ideals ${\frak a},{\frak b}$ are said to be `coprime` if ${\frak a}+{\frak b}=(1)$.

If ${\frak a},{\frak b}$ are coprime then $({\frak ab}) = ({\frak a})\cap({\frak b})$.

**Definition.** The `direct product` of rings $A_{1},\dots,A_{n}$ is denoted by 
$$
A = \prod_{i=1}^n A_{i}
$$
which is comprised of element $x = (x_{1},\dots,x_{n})$ where $x_{i} \in A_{i}$. Addition and multiplication is defined componentwise. A is a commutative ring with identity $(1,\dots,1)$. We have projections $p_{i}:A\to A_{i}$ which projects $x$ to its $i$-th component.

Let $A$ be a ring (any ring, not necessarily a product ring) and ${\frak a}_{i}$ ideals of $A$, we can first make a list of rings ${A} / {{\frak a}_{i}}$ then multiply them together to form a product ring $\prod_{i} A / {\frak a}_{i}$. There is a ring homomorphism from $A$ to this product ring, denoted by $\phi$,
$$
\begin{align}
\phi : &A \to \prod_{i=1}^n A / {\frak a}_{i},\\
       & x \mapsto (x+{\frak a}_{1},\dots,x+{\frak a}_{n}),
\end{align}
$$
which maps each element of $A$ to a n-tuple. 

Let's take a look at the kernel of $\phi$, which is comprised of the elements that are send to zero in the product ring. Take a look at the first component, for $x+{\frak a}_{1}$ to be zero in $A / {\frak a}_{1}$, $x$ must be an element of ${\frak a}_{1}$. Then,
$$
\text{ker}(\phi) = \{ x\in A \mid x\in {\frak a}_{i},\,i=1,\dots,n \} \implies \text{ker}(\phi)={\frak a}_{1}\cap\dots \cap {\frak a}_{n}. 
$$
If $\phi$ is injective, meaning the kernel has only one element, then $\cap_{i}{\frak a}_{i}=0$.

**Definition.** Let ${\frak a},{\frak b}$ be ideals of a ring $A$. Their `ideal quotient` is 
$$
({\frak a}: {\frak b})=\{ x\in A \mid x{\frak b}\subset {\frak a} \}
$$
which is an ideal, as can be easily verified, and justifies the usage of parenthesis. 

$({\frak a}: {\frak b})$ is useful when ${\frak a}<{\frak b}$, where the ordering is given by inclusion. Particularly, $(0: {\frak b})$ is called the `annihilator` of ${\frak b}$ and is sometimes denoted by $\text{Ann}({\frak b})$: it is the set of all $x\in A$ such that $x{\frak b}=0$. In this notation the zero-divisors of $A$ are denoted by 
$$
D = \bigcup_{x\neq 0} \text{Ann}(x).
$$

To simplify the notations, if $(x)$ is a principal ideal, instead of $({\frak a}:(x))$ we simply write $({\frak a}:x)$.

Take the ring of integers for example, we have 
$$
(8:2)=\{ x\in \mathbb{Z} \mid 2x\in 8\mathbb{Z} \} =\left\{ 4\mathbb{Z} \right\} =(4).
$$
Various relation concerning ideal quotient can be found in textbooks, we will not list them here.

**Definition.** Let ${\frak a}$ be any ideal of $A$, the `radical` of ${\frak a}$ is 
$$
\text{rad}({\frak a}):=\{ x\in A \mid x^n\in{\frak a} \text{ for some }n\in\mathbb{Z}^+ \}.
$$

Let $\phi:A \to A / {\frak a}$ be the standard ring homomorphism, what would $\phi(\text{rad(\frak a)})$ be like? Since some power of $x$ is in ${\frak a}$, in the quotient ring $A / {\frak a}$, some power of $x$ is zero, thus 
$$
\phi(\text{rad} ({\frak a})) = \text{nilradical of } A / {\frak a} = {\frak R}(A) \implies \text{rad}({\frak a}) = \phi^{-1}({\frak R}_{A / {\frak a}}),
$$
which also shows that $\text{rad}({\frak a})$ is an ideal. 

The radical of an ideal has the following properties:
- ${\frak a}\subseteq\text{rac}({\frak a})$
- $\text{rad}(\text{rad}{(\frak a)})=\text{rad}({\frak a})$
- $\text{rad}({\frak ab})=\text{rad}({\frak a})\cap \text{rad}({\frak b})$
- if ${\frak p}$ is prime, $\text{rad}({\frak p}^n)=\text{rad}({\frak p})$ for all $n>0$.

**Proposition.** The radical of an ideal ${\frak a}$ is the intersection of all the prime ideals containing ${\frak a}$. 

More generally, we can define the radical of any subset $E$ of ring $A$ in the same way. It is not necessarily an ideal. 
