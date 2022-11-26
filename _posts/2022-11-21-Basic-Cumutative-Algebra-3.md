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

The set ${\frak R}$ of all nilpotent elements in ring $A$ is an ideal, and $A / {\frak R}$ has no nilpotent elements. To see that ${\frak R}$ form an ideal, convince yourself that the addition of two nilpotents is still a nilpotent. 

**Definition.** The ideal ${\frak R}$ of nilpotent elements of $A$ is called the `nilradical`. The nilradical is also the intersection of all the prime ideals of $A$. 


*Proof.* Let ${\frak R}'$ be the intersection of all the prime ideals of $A$. If $f\in A$ is nilpotent, then for some $n$ we have $f^n=0\in {\frak p}$, where ${\frak p}$ is a prime ideal. hence ${\frak p}$ is prime, $f$ must be in ${\frak p}$ as well, i.e., a nilpotent must be an element all the prime ideals, $f\in {\frak R}'$.  Conversely, we shall show that if $f$ is not nilpotent,  $f$ is not in ${\frak R}'$. Suppose $f$ is not nilpotent, let $\Sigma$ be all the ideals that does not contain multiples of $f$, each element of $\Sigma$ is an ideal ${\frak a}$ such that 
$$
n>0 \implies f^n \notin {\frak a}.
$$
Then $\Sigma$ is no empty since $0\in \Sigma$, and Zorn's lemma says that there is a maximal element, order by inclusion. Let ${\frak p}$ be a maximal element of $\Sigma$, we shall show that ${\frak p}$ is indeed prime, as the notation suggests. Let $x,y \notin {\frak p}$, then the ideals ${\frak p}+(x),{\frak p}+(y)$ strictly contain ${\frak p}$ and therefore do not belong to $\Sigma$. Hence, by construction, multiples of $f$ is an element of these larger ideals,
$$
f^m\in {\frak p}+(x),\quad f^n\in {\frak p}+(y)
$$
for some $m,n$. It follows that $f^{m+n}\in {\frak p}+(xy)$, which means ${\frak p}+(xy)$ is not in $\Sigma$, thus $xy\notin {\frak p}$. To sum up,
$$
x,y\notin {\frak p} \implies xy\notin {\frak p},
$$
it follows that ${\frak p}$ is prime. Q.E.D.

**Definition.** The `Jacobson radical` ${\frak R}$ of $A$ is defined to be the intersection of all the maximal ideals. 

**Proposition.** Leg ${\frak R}$ be Jacobson radical of ring $R$. 
$$
x\in {\frak R} \Leftrightarrow 1-xy \text{ is a unit } \forall y \in R 
$$
The proof can be found in Atiyah's textbook.


- - -

Next we discuss operations allowed on ideals. Ideals are sets, naively we would think that all the operations defined for ideals are naturally defined for ideals as well, however, the question is whether the result is still an ideal?

**Sum**

Let ${\frak a}{\frak b}$ be two ideals of ring $R$. The sum ${\frak a}+{\frak b}$ is defined element-wise, namely 
$$
{\frak a}+{\frak b} := \{ x+y \mid x\in {\frak a}, \,y\in {\frak b} \}. 
$$
Note ${\frak a}+{\frak b}$ is different from ${\frak a} \cup {\frak b}$. The sum of ${\frak a},{\frak b}$ is the smallest ideal containing ${\frak a}$ and ${\frak b}$. This definition can be generalized to the sum of arbitrary numbers of ideals. 

