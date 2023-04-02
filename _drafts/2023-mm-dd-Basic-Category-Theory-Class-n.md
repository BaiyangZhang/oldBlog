---
layout:     post   				    # 使用的布局（不需要改）
title:     Basic Category Theory Class n			# 标题 
subtitle:   
date:       2023-mm-dd 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/mathArt7.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - PureMath
    - CategoryTheory
    - Notes
---

### The Universal property

Category theory is about structures, not about details. It doesn't care about what you look like, but rather who and how you interact with. Category theory takes a bird's eye view of mathematics. 

One of the most important concept in category theory is that of `universal property`. They are ubiquitous in all the branches in mathematics, often in disguise. To get a better understanding of universal property, let's start from some examples.

As a first example, let's consider sets. Let $1$ denote the set with only one elements. It doesn't matter what the element really is, may it be a real number, a complex number, or even a person. It again shows the "taking a bird's view" nature of category theory. **Given a set $1$, for all sets $X$, there exists a unique map from $X$ to $1$**. In this context, the words "map", "arrow" and "function" are all the same thing.

The key word here is `unique`. Given any map $X$, there is indeed only one possible way to map all and every elements of $X$ to $1$, namely the constant map, $f(x)=1$. 

Phrases of the form "there exists a unique such-and-such satisfying some condition" are common in category theory. The phrase means that there is only one such-and-such satisfying the condition. To prove it, we need to prove that i) there exists at least one such-and-such and ii) there exists at most 1 such-and-such. If there are two things satisfying the condition, they must be the same.

This kind of properties are called `universal properties`, since it describes how the object being described (in our example, the set $1$) relates to **all** the other objects in the universe it lives in (the universe of sets). In our example, the property starts with "for *all* sets $X$", and therefore says something about the relationship between $1$ and the entire universe of sets.

As the second example, consider the universe of rings. In our note rings are always assume to contain a multiplicative identity $1$. Recall that homomorphisms between rings are maps that preserves addition and multiplication, and of course identity $1$. 

The ring of integers $\mathbb{Z}$ is special among rings in the sense that, for all rings $R$, there exists a unique homomorphism $f:\mathbb{Z}\to R$, which maps number $1$ to the multiplicative identity of $R$. Note this is again of the form "there exists a unique such-and-such that blahblahblah". Any number can be written as the summation of certain number of $1$, for example $5$ is $1+1+1+1+1$, then the homomorphism $f$ maps number $5$ to an element in $R$ which is the summation of five multiplicative identity. In this way, the homomorphism is `unique`. 

To prove the uniqueness, we don't need to rely on any specific properties of rings! Let $\phi:\mathbb{Z}\to R$ be another homomorphism, we want to prove that $\phi$ is the same as $f$. Now, two maps between sets are equal when they map every element to the same element. So we need to look at how $f$ and $\phi$ acts on elements of $\mathbb{Z}$. Since homomorphism preserves identity, we have $\phi(1)=1=f(1)$. Since homomorphism preserves addition, we have 
$$
\phi(n) = \phi(1+\dots+1) = \phi(1)+\dots+\phi(1)=1+\dots+1=f(1)+\dots+f(1)=f(1+\dots+1)=f(n).
$$
Since homomorphism preserves zero, we have $f(0)=0=\phi(0)$. Thus $f(z)=\phi(z)$ for all $z\in\mathbb{Z}$. 

**Crucially, there can be essentially only one object object that satisfying a given universal property**. The word "essentially" means the two objects satisfying the same universal property need not literally be equal, but only equal up to isomorphism. Recall that isomorphism between $A$ and $B$ means that there are two arrows $A\to B$ and $A\leftarrow B$, whose compositions are identity on both ends. In our example of rings, the uniqueness of such objects says:

Let $A$ be a ring with the following property: for all rings $R$, there exists a unique homomorphism $A\to R$. Then $A\cong B$.

Before proving it, let me mention that a ring with this property is called an `initial object`, since there is a arrow coming out from this object to any other objects. We could say that $A$ is `initial` in the category of rings (I haven't said what a category is yet, for now just think of category as a collection of rings).

Now the lemma we want to prove has become, if $A$ is initial, and we already know that $\mathbb{Z}$ is initial, prove that $A\cong \mathbb{Z}$. 

Since $A$ is initial, there is a unique map from $A$ to all the other rings, including $\mathbb{Z}$, call it $\phi:A\to \mathbb{Z}$. Since $\mathbb{Z}$ is also initial, there exists a unique map $\phi':\mathbb{Z}\to A$ as well. Now $\phi'\circ\phi:A\to A$ is a homomorphism (the composition of two homomorphisms is itself a homomorphism), but so is the identity map $1_{A}:A\to A$. Since $A$ is initial, there is a **unique** map from $A\to A$ as well! It means that $\phi'\circ\phi$ can't be different from $1_{A}$, otherwise the map $A\to A$ won't be unique. Thus $\phi'\circ\phi\cong {1}_{A}$. In the same way we can prove that $\phi\circ\phi'\cong 1_{\mathbb{Z}}$. Thus $A$ is isomorphic to $\mathbb{Z}$.

The proof has very little to do with the properties of rings (addition, multiplication are defined, etc.), it belongs to a higher level of generality.  


