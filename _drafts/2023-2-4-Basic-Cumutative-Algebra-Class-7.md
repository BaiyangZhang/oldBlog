---
layout:     post   				                    # 使用的布局（不需要改）
title:      Basic Commutative Algebra Class 7		# 标题 
subtitle:   Class 7
date:       2023-2-4 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/mathArt3.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - Math
    - Commutative Algebra
    - Notes
---

### Localization

Localization is a technique used in commutative algebra in both algebra and geometry. In geometry it is used when we want to look at points in varieties locally, hence the name. 

Let $R$ be a ring (commutative, unital). The general idea is that, given a certain subset $S\subset R$, we want to introduce the invers of $S$, namely the inverse of all the elements $s\in S$, into $R$. In other words, we want to `division` by $S$. 

As a motivating example, look at the ring of integers $\mathbb{Z}$. Let $S$ be the non-zero integers, $S = \mathbb{Z}-0$. Inverting all elements of $S$ one obtains the ring of rational numbers $\mathbb{Q}$, or the field of rational numbers since all the elements are invertible. Formally, a rational number can be considered as a pair of integers $(a,s)$ where $a\in\mathbb{Z}$ and $s\in S$, plus the equivalence relation
$$
(a,s) \sim (a',s') \iff as'=a's,
$$
then the equivalent class $(a,s)$ is denoted $a / s$, and addition and multiplication is `defined` by 
$$
(a,s)+(a',s') = (as'+a's,ss'),\quad (a,s)\cdot (a',s')=(aa',ss').
$$

Now we want to generalize this procedure to arbitrary rings. The first observation is that one can not introduce the inverse of just about any arbitrary subsets, but just `multiplicatively closed` sets, namely sets that is closed under multiplication. To be accurate, A subset $S\subset R$ is said to be multiplicatively closed if 
$$
1\in S \text{ and } s,s'\in S\implies ss'\in S.
$$

In spirits of construction of rational numbers from integers, we define the equivalence class $(a,s),a\in R,s\in S$ under the equivalence relation 
$$
(a,s)\sim (a',s') \iff \exists u\in S \text{ such that } u(as'-a's)=0.
$$
The set of equivalence classes is denoted by $S^{-1}R$, with addition and multiplication defined as before. 

Readers can check that $R^{-1}S$ indeed form a ring, called the `localization` of $R$ at $S$. 

Note that the condition 
$$
\exists u\in S \text{ such that } u(as'-a's)=0
$$
means that if $R$ is a integral domain, then $as'-a's$ itself must be zero since there are no zero devisors. $u$ should not be $0$ or we will get a trivial localization. 

There is a natural isomorphic map from $R$ to $S^{-1}R$ defined by $\iota : a\mapsto a / 1$. Surprisingly the map is not always injective, it is only so when $S$ does not contain zero divisors. To see it, take a look at the kernel of $\iota$,
$$
\text{ker }(\iota) = \left\{ a\in R \,\middle\vert\, \frac{a}{1}=\frac{0}{1} \right\}, 
$$
the equivalence relations says that the equal sign holds if there exists non-zero $u\in S$ such that 
$$
u(a\cdot 1-1\cdot 0)=ua=0,
$$
namely if $u$ is a zero divisor. By the way, $S$ contains zero divisors does **not** necessarily means that $S$ contains zero itself, think about it. 

