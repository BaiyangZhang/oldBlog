---
layout:     post   				    # 使用的布局（不需要改）
title:     Introduction to Higher Form Symmetry 			# 标题 
subtitle:   Part 1
date:       2023-06-12 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/lib16.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - PureMath
    - CategoryTheory
    - Notes
---

For conventions used in this note, see my blog [here](http://www.mathlimbo.net/2022/07/17/Conventions-and-Formula/). I understand that my choice of the metric, the mostly negative one, will intrigue some strong emotional reaction among certain groups of physicist, but I will keep using it anyway, partly because it is the most widely used in the context of quantum field theory. 

## One-dimensional gauge invariant objects in pure YM

This chapter is meant for people who are not very familiar with Wilson loops and 't Hooft loop, if you are not the target reader, feel free to skip this chapter all together. 

I assume the reader has some basic notion of what quantum Yang-Mills theory is, if not, there exist an ocean of textbooks and introductory readings on quantum field theory, all necessarily include Yang-Mills theory. Personally I recommend the books written by Matthew D. Schwartz, A. Zee and Mark Srednicki. It's not that the all-time classic, Peskin&Schroeder's book is not good, just that it is not for beginners and is heavily focused on high energy physics calculations, you practically learn no geometry of QFT. I also recommend David Tong's lecture notes, which provides a pretty good balance between calculation detail and profound understanding.

- - -

The gauge group is assumed to be $SU(N)$ if not mentioned otherwise, sometimes when we talk about electric and magnetic field we will use $U(1)$ which is a abelian version of $SU(N)$. The Yang-Mills field is normalized such that the action reads
$$
S = - \frac{1}{g^{2}} \int d^{4}x \, \frac{1}{2}\mathrm{Tr}\,F_ {\mu \nu}F^{\mu \nu}
$$
Thus the coupling $g^{2}$ plays the rule of $\hbar$, at the limit $g^{2}\to 0$ it is the same as $\hbar\to 0$ and the classical contribution will dominate. 

### Wilson line

In this chapter we will assume the gauge field $A_ {\mu}$ is a *fixed background field*, in which we place a test particle. The test particle is under our control and its own contribution to the potential is neglected, in other word it tests the field but *sources nothing*. Suppose the particle moves along a curve $C$, which starts at $x_ {i}$ (i for initial) and ends at $x_ {f}$ (f for final), we define the corresponding `Wilson line` as 
$$
U[C] := \mathcal{P} \exp\left( i \int_{x_ {i}}^{x_ {f}} dx^{\mu} \, A_ {\mu}  \right) = \mathcal{P}\exp\left( i\int_{x_ {i}}^{x_ {f}} A \right)
$$
where $\mathcal{P}$ stands for the path-ordering and in the last term we adopted the 1-form expression for the gauge field (or *connection*, if you prefer to treat is as a fiber bundle). The Most important property of Wilson line is how it transforms under a gauge transformation. Turns out it only depends on the end point,
$$
U[x_ {i},x_ {f};C]\to \Omega(x_ {i})\; U[x_ {i},x_ {f};C] \; \Omega ^{\dagger}(x_ {f}).
$$

If we compactify $C$ to a closed curve, namely a loop, then we get a `Wilson loop`,
$$
W[C] = tr \mathcal{P} \exp\left( i \int A   \right),
$$
Note we have also put a trace in the definition for future convenience. Mathematically it is known as a gauge `holonomy`. The important thing is that, **Wilson loop is gauge invariant**! 

**Remarks.** 

1. Wilson loop is a one-dimensional thing,
2. Wilson line is not gauge invariant but Wilson loop is,
3. It will play the most important rule in the study of deconfinement phase transition.

The Wilson loop can also be regarded as operators acting on the Hilbert space of the quantum system. However, remember that in quantum theories, states are defined as living on a spacelike slice of the spacetime, thus it is important to first rotate our Wilson loop so that it lives in a time slice, namely in a space at fixed time. It turns out that when $W[C]$ acts on a state, it adds to the state a loop of electric flux along $C$. Roughly speaking, in the language of *canonical quantization*, let $\pi$ be the canonical momentum, similar to $p = -i \frac{\partial}{\partial x}$, we have the following functional expression
$$
\pi_ {i} = -i \frac{\delta \mathcal{L}}{\delta  {A}^{} {i}} = E_ {i}+\frac{\theta}{8\pi^{2}}B_ {i}
$$
thus when the $\theta$-angle is zero, we simply get 
$$
E_ {i} = -i \frac{\delta}{\delta A^{i}}
$$
Thus when acting on a state $W[C]\left\lvert{\psi}\right\rangle$, we have 
$$
E^{i}W[C]\left\lvert{\psi}\right\rangle  = \mathrm{Tr}\, \mathcal{P} \left\{ \left( \frac{\delta}{\delta A_ {i}}\int_ {C} A  \right) W[C] \right\} \left\lvert{\psi}\right\rangle 
$$
whose support is $C$, meaning the electric field is zero at any place but $C$. For more detail, see David Tong's note.

- - -

### 't Hooft line

We have talked about test particles with charge, they are electric probes. Then what about magnetic probe? We run into problems immediately, since we don't know what is the operator that inserts a magnetic monopole in the spacetime. For electric probe, a charged particle is inserted by the source term $j^{\mu}$, there is no magnetic counterpart of it. It turns out there is still a way to do it, and the operator that is responsible for the insertion of a magnetic field is called a `'t Hooft line`. 

Take the simplest gauge group, $U(1)$ for example. We know the magnetic monopole solution, although they are singular at the origin, but it doesn't matter for our discussion. Suppose that a monopole of magnetic charge $m$ traces out a world line $C$ in our Minkowski spacetime. For any $\mathbb{S}^{2}$ that surrounds $C$ in space (*not 4D spacetime but 3D space*), we have
$$
\int _ {\mathbb{S}^{2}} \, B\cdot dS =m.\tag{1}
$$
We now define the 't Hooft line by requiring that we take the path integral only over fields that satisfy the above equation on $C$. 

The logic is really simple, since we can't simply find the operator that sources the monopole, then let's start from the path integral, whenever we want to calculate the expectation value of something in the background of a monopole (with worldline $C$), we require that only the field configurations satisfy this condition to be included into the path integral! Then, at least in principal, we can calculate the correlation between a 't Hooft line $T[C]$ with other stuff.

Next we go to Yang-Mills theory with gauge group $G$, whose Lie algebra is denoted ${\frak g}$. Recall that ${\frak g}$ include a set of $r$ mutually commute vectors (or `generators`, anyway if the group is regarded as a manifold then the generators are nothing but vectors at the identity, for more detail refer to Theodore Frankel's textbook), where $r$ is the `rank` of the Lie group. 

Let ${\frak h}\subset {\frak g}$  be the Cartan subalgebra of ${\frak g}$. Recall that ${\frak h}$ is just the maximal set of $r$ (=rank) mutually commuting generators, or if you prefer the geometric interpretation, substitute *generator* with *vector* and *commuting* with *vanishing Lie bracket*. ${\frak h}$ can be regarded as a vector of $r$ components. 

let $C$ be a timelike (since nothing moves faster than light) curve sitting at the origin. We will require the magnetic field $B^{i}, i=1,2,3$ to take the form 
$$
B^{i} \to \frac{\hat{r}^{i}}{4\pi r^{2}} {\frak q}(x), \quad  r\to \infty,
$$
where ${\frak q}(x)$ is some ${\frak g}$-valued things that specifies the magnetic charge of the monopole, we will say more about it later. Just to remind you, the magnetic field $B^{i}$ is just an component of the field strength $F_ {\mu \nu} = F_ {\mu \nu}^{a} T^{a}$, hence is ${\frak g}$-valued. 