---
---
layout:     post   				    # 使用的布局（不需要改）
title:      Basic Commutative Algebra Class 1			# 标题 
subtitle:   Inspired by the lectures by Richard E. Borcherds
date:       2022-11-17 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/mathArt5.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - Math
    - Commutative Algebra
    - Notes
---

>It is the mark of the educated mind to use for each subject the degree of exactitude which it admits.
>— Aristotle


Commutative algebra is the basic of many other fields in mathematics. You need to know quite a lot of commutative algebra if you want to understand algebraic geometry, which is the study of the geometry of polynomial rings, or number theory which I know nothing about, or Invariant theory which is a little out-fashioned nowadays.

<<<<<<< Updated upstream:_drafts/2022-11-17-Basic-Cumutative-Algebra-Class-1.md
I supposed you know the definition of commutative rings already, if not, you can easily find the definition on the internet. Two textbooks are strongly recommended for complete beginners,
- [*A First Course in Abstract Algebra*](https://www.amazon.com/First-Course-Abstract-Algebra-7th/dp/0201763907) by  John Fraleigh,
- [*An Introductory Course in Commutative Algebra*](https://www.amazon.com/Introductory-Commutative-Algebra-Science-Publications/dp/0198501447/ref=sr_1_1?crid=GZ3K9KD5JH2I&keywords=an+introductory+course+in+commutative+algebra&qid=1661817436&s=books&sprefix=an+introductory+course+in+commutative+algeb%2Cstripbooks%2C446&sr=1-1) by A. W. Chatters and C. R. Hajanavis
and the all-time most classic 
-  *Introduction to Commutative Algebra* by M.F.Atiyah and I.G.Macdonald.
=======

I assume the reader is familiar with the definition of commutative rings, which can be easily find the definition on the internet. Two textbooks are strongly recommended for complete beginners,
- [*A First Course in Abstract Algebra*](https://www.amazon.com/First-Course-Abstract-Algebra-7th/dp/0201763907) by  John Fraleigh,
- [An Introductory Course in Commutative Algebra](https://www.amazon.com/Introductory-Commutative-Algebra-Science-Publications/dp/0198501447/ref=sr_1_1?crid=GZ3K9KD5JH2I&keywords=an+introductory+course+in+commutative+algebra&qid=1661817436&s=books&sprefix=an+introductory+course+in+commutative+algeb%2Cstripbooks%2C446&sr=1-1) by A. W. Chatters and C. R. Hajanavis.

Starting with some examples of commutative rings. 
>>>>>>> Stashed changes:_drafts/2022-8-30-Basic-Cumutative-Algebra-Class-1.md

Let's start with some examples of commutative rings,
- The ring of integers $\mathbb{Z}$, for plus, minus and multiplication is defined but not division.
- The Gaussian integer $\mathbb{Z}[i]$, it is the set of complex integers of form $m + i n$ where $m,n$ are integers and $i^{2}=-1$.



**Definition.** 
- A *Domain* is a nonzero ring with in which $ab = 0$ implies $a=0$ or $b=0$ or both. If $ab=0$ and $a,b\neq 0$, then $a,b$ are called *zero devisors*, so a domain can be said to be a non-zero ring without zero devisors. It makes a lot of operations familiar to us from the manipulation of integer numbers still valid. For example $\mathbb{Z}$ is a Domain. 
- An integral domain is just a commutative domain.
- A *prime element* is an element which is not zero or a unit (defined next), satisfying $p | ab$ implies that $p | a$ or $p|b$, where $p|a$ means $p$ divides $a$.
- A unit of a ring is an invertible element for the multiplication of the ring. That is, an element $u$ of a ring is a unit if there exists $v$ in the same ring such that $uv = vu =1$.

A question people usually ask about these rings is: Is it a Unique Factorization Domain, U.F.D. for short? Meaning that can every element in it be uniquely factorized as a product of primes up to order units. 
