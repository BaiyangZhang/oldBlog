---
layout:     post   				    # 使用的布局（不需要改）
title:     Quartic time derivative in a Lagrangian 			# 标题 
subtitle:   Does it work?
date:       2023-07-07 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/background17.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - 
---

### Introduction

One day my postdoc supervisor game me this function
$$
T = \frac{\alpha}{2} b^{2}_ {i} + \frac{\beta}{4} (b^{2}_ {i})^{2}
$$
I guess $b_ {i}$ is something like $\dot{a}_ {i}$. $T$ is probably the kinetic energy.

The canonical momentum is 
$$
\pi_ {i} = \frac{\partial T}{\partial b_ {i}} = \alpha b_ {i} + \beta b^{2} b_ {i},\quad  b^{2}:=b_ {i}b_ {i}.
\tag{5}
$$

The question is, what is $T(\pi_ {i})$? And the next question, I guess, is how to quantize it?

There might be two methods adoptable here, Legendre transform and direct algebraic substitution. The latter is to solve for $b_ {i}$ from Eq.(5) and substitute it back to the expression for $T$. 

The problem is that, the algebraic substitution will in general loose some information.

Functions are information. Different functions contain different functions, some contains more and some less. For example, the constant function contains little information. In general we have the following conclusions.

- The information of a function is equivalently contained in its graph. Thus, any operation that preserved the graph up to rotation, stretching, mirroring, etc. also preserved the information. For example, given a function $y=f(x)$, its inverse function, if exists, contains the same information since the graphs are just mirrored along $y=x$. 
- The Fourier transform also preserves the information. In fact, functions are elements, or vectors in some Hilbert space and the Fourier transform corresponds to a change of representation.

So the question I wanna ask myself is, does Legendre transform preserve the information, just as Fourier transform?

- - -

What is a Legendre transform, really? Given a function $y = f(x)$, or $y = y(x)$, sometimes we are more interested in the slope $dy / dx$, so much as to wanting them as the variable instead of $x$. So we define a new variable,
$$
p:= \frac{dy}{dx} = p(x).
$$
Now how can we get a function in terms of $p$ without loosing any new information? The obvious way is to solve $x$ in terms of $p$, then substitute $x$ by $p$ in the original function to obtain $f(x(p))$. All seems good, except that this procedure actually causes a loss of information, as shown in the below example.

Consider a function $y =\frac{1}{2} (x-x_ {0})^{2}$, follow the procedure we introduced before, define
$$
p := \frac{dy}{dx} = (x-x_ {0}) \implies x = p+x_ {0}
$$
take it back to the original function we get
$$
y = \frac{1}{2} (p+x_ {0}-x_ {0})^{2} = \frac{1}{2}p^{2},
$$
$x_ {0}$ is gone! This is bad news since now we have loss the information of $x_ {0}$. Another way to say it is that, now two function with different $x_ {0}$ will be transformed to the same function $y=\frac{1}{2} p^{2}$. Bad news indeed. If it is a good transform, we should be able to transform it back to the original function, just as Fourier transform or Laplace transform or Borel transform, etc. Or, you could say now the information has been split to two places, the final function $\frac{p^{2}}{2}$ and the specific transform process, that is we used $p=x-x_ {0}$. Well, we don't want the transform process itself to contain any information! When we are doing Fourier transform or anything, we don't need to remember anything about the original function, do we?

Well there is a solution but only works for convex and concave functions. Recall that roughly speaking a convex function is a functions curves downwards and a concave function is a function that curves upwards. They are assumed to be almost-everywhere differentiable, if you don't remember what "almost-everywhere" means please refer to my other notes.

Now, the solution of course is the Legendre transformation. Denote $\widetilde{y}$ the Legendre transformed function, we have 
$$
\widetilde{y}(p) = 
\begin{cases}
\text{sup }\left\{ px - y(x) \right\} & y \text{ is convex}, \\
\text{inf }\left\{ px - y(x) \right\} & y \text{ is concave}.
\end{cases}
$$
If the function is not convex/concave only in localized regions, then the transform still makes sense. Sometimes it is defined with an extra minus sign. 

Let's apply Legendre transform to $y=\frac{1}{2} (x-x_ {0})^{2}$, we have $p=dy / dx = x-x_ {0}$ and 
$$
\widetilde{y} = px-y = (x-x_ {0})x -\frac{1}{2} (x-x_ {0})^{2} = (x-x_ {0})\left( x-\frac{x}{2} + \frac{x_ {0}}{2} \right) = \frac{1}{2}(x-x_ {0})(x+x_ {0}),
$$
$x_ {0}$ is still there!

- - -

Now we can do the Legendre transform twice to prove that for certain functions 
$$
\widetilde{\widetilde{y}} = y.
$$
To show it, first perform once Legendre transform
$$
\widetilde{y}(p)=p x(q)-y(q),\quad  p = dy / dx.
$$
That is, assume you can solve for $x$ from $p$. Now, do it again we have 
$$
\widetilde{\widetilde{y}} = qp - \widetilde{y} = y(q)
$$
where I've omitted some details, but you can reproduce it, no problem.

- - -

**Method of Legendre Transform.** 

Back to 
$$
T = \frac{\alpha}{2} b^{2} + \frac{\beta}{4} (b^{2})^{2},\quad  b^{2}:= b_ {i}b_ {i}
$$
and the canonical momentum reads 
$$
\pi_ {i} = \frac{\partial T}{\partial b_ {i}} = \alpha b_ {i} + \beta b^{2} b_ {i},\quad  b^{2}:=b_ {i}b_ {i}.
\tag{5}
$$

Perform the Legendre transform to $T$ we get 
$$
H:= \pi_ {i}b_ {i}-T = \frac{\alpha}{2}b^{2} - \frac{3}{4}(b^{2})^{2}.
$$
So far it seems to lead to nowhere

**Algebraic substitution.** 