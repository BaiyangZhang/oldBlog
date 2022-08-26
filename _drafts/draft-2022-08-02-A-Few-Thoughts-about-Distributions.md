---
layout:     post   				    # 使用的布局（不需要改）
title:      A few thoughts about distributions 				# 标题 
subtitle:    #副标题
date:       2022-08-02 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/functionalAnalysis.png 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - math
    - functional analysis
    - distribution
---


## There are so much more to integrals...

The concept of integral is deceptively simple --  at least for me when I just learnt about the Riemann integral. I used to think that integral is just summation at its finest. For example, if one is given the velocity as a function of time $v(t)$ and one want to know the total distanced traveled, one just integrate velocity from initial to final time, 

$$\text{distance} = \int_{t_i}^{t_f} {v}(t) dt.$$

The idea is that, time is split into infinite intervals, each time slice has length $\Delta t$, so short that the velocity is assumed to be a constant in any time slice, and we just sum up the distance travelled in each time slice. In the $\Delta t \to 0$ limit, this should give us the accurate result,  
$$\sum_i {v}(t_i) \Delta t \to \int_{t_i}^{t_f} {v}(t) dt, \quad \sum \Delta t \to \int dt.$$  
That is the basic idea of Riemann integral. It makes total sense. The same picture seems to be sufficient for multi-variable integrals as well --- just change $dt$ to $dx_{1} dx_{2} \dots$ or something like that. But when I begin to learn more about it, a more subtle picture begin to emerge. Thanks to Terence Tao[^1], I learnt that there are actually three different kinds of integrals. We will first list them and then elaborate about their differences. The three different kinds of integrals are

[^1]: The Princeton Companion of Mathematics, III.16.

- The *indefinite integral* $\int f$ (also knows as the antiderivative, for obvious reasons). 
- The *unsigned definite integral*, $\int_{[a,b]} f(x) \, dx$ where $[a,b]$ denotes the interval from a to b, but should be regarded as a set of all the elements in between.
- The *signed definite integral* $\int_{a}^b f(x) \, dx$, where the change of $a \leftrightarrow b$ will flip the sign of the integral.

The indefinite integral is connected with the signed definite integral via the fundamental theorem of calculus. The signed definite integral can be used to, for instance, calculate the work required to move a point from a to b, where $f(x)$ is the force in the positive x direction. If you reverse the direction of the force but keep unchanged the points a and b, the work required is also reversed. The unsigned definite integral is used to, for instance, calculate the total mass of a string, where $f(x)$ is the density. The string is divided into infinite infinitesimal pieces each with mass $dx f(x)$, and summing it over gives the total mass, the key point is that it doesn't matter in what order we sum it over, you could sum it over from a to b or from b to a, the total mass is the same positive definite number. So the key difference between the signed and unsigned integral is the concept of **direction**, or **orientation**. The unsigned integral is blind to the orientation of the manifold on which the integral is performed, while the signed integral is sensitive to the orientation. Another example of orientation-sensitive integral is the magnetic flux through a surface, each point on a surface has a normal vector, which denotes the orientation of the surface, when reversed, the flux also flips the sign.

These three different kinds of integrals are almost the same in single-variable calculus, and it seems to be a matter of convenience as to which kind of integral to use. However, when move to multi-variable calculus, things become more complicated, also more interesting. Different kinds of integrals will generalize to different things, the indefinite integral, or anti-derivative, generalizes to the notion of a *solution to a differential equation*, or I guess one could call it anti-differential-equation for fun.  It appears more often as anti-something, meaning that if you differentiate it, you get something else. The signed integral generalizes to the integration of forms, which is arguably the most important application in physics.  The notion of differential form is also of fundamental importance in differential geometry, geometry and de Rham cohomology. This topic is super fun but it's for another day, here I will only mention one interesting fact about differential form.

We know that in calculus of two variables, the integration is against $dx dy$, namely the integral is of the form $\int f(x,y) \, dx dy$. To perform a change of coordinates to, say, $r,\theta$, we need Jacobi determinant  
$$\left|    \begin{matrix} 
\frac{\partial x}{\partial r} & \frac{\partial x}{\partial \theta}\\
\frac{\partial y}{\partial r} & \frac{\partial y}{\partial \theta}
\end{matrix} \right|$$ so that  
$$
\int f(x,y) \, dx dy = \int f(r,\theta) \,\left|    \begin{matrix} 
\frac{\partial x}{\partial r} & \frac{\partial x}{\partial \theta}\\
\frac{\partial y}{\partial r} & \frac{\partial y}{\partial \theta}
\end{matrix} \right| dr d\theta. 
$$
We also know that the Jacobi determinant gets a minus sign under the exchange $x \leftrightarrow y$, so it would seem that   
$$
dxdy =\left| \begin{matrix} 
\frac{\partial x}{\partial r} & \frac{\partial x}{\partial \theta}\\
\frac{\partial y}{\partial r} & \frac{\partial y}{\partial \theta}
\end{matrix} \right| dr d\theta = -\left| \begin{matrix} 
\frac{\partial x}{\partial r} & \frac{\partial x}{\partial \theta}\\
\frac{\partial y}{\partial r} & \frac{\partial y}{\partial \theta}
\end{matrix} \right|(x\leftrightarrow y)) dr d\theta = - dydx.
$$
However, by no means the above relation should hold for $dx dy$ since multiplication is abelian! One solution is to remember that always take the absolute value of the Jacobi determinant, it works but it is ugly and we would loose the information of the orientation of the manifold (that is, if the manifold is oriented at all). Another solution is to adopt a new understanding of $dx dy$. That's the solution given by differential forms. In differential forms, we define formally the measure as $dx \wedge dy$, it is anti-symmetric by definition, namely $dx\wedge dy = - dy \wedge dx$. The change of coordinates would look like  
$$
dx\wedge dy =\left| \begin{matrix} 
\frac{\partial x}{\partial r} & \frac{\partial x}{\partial \theta}\\
\frac{\partial y}{\partial r} & \frac{\partial y}{\partial \theta}
\end{matrix} \right|
dr\wedge d\theta = -\left| \begin{matrix} 
\frac{\partial x}{\partial r} & \frac{\partial x}{\partial \theta}\\
\frac{\partial y}{\partial r} & \frac{\partial y}{\partial \theta}
\end{matrix} \right|(x\leftrightarrow y)) dr\wedge d\theta = - dy\wedge dx.
$$
Problem solved! Sadly I can't say more about differential forms here, interested reader are referred to tons of great textbooks written on this subject.

Next, we will talk about the generalization of unsigned definite integral. That leads us to the measure theory.


## Some measure theory

Introduce the measure theory here, the $\sigma$-algebra, where $sigma$ stands for the union, and the measurable sets $\mathfrak{m}$. 

## Distributions against Test function in $l^n$ and $L^n$


Classically, function are defined set-theoretically. For example, on the Wiki page of function it says 

>In mathematics, a function from a set X to a set Y assigns to each element of X exactly one element of Y. The set X is called the domain of the function and the set Y is called the codomain of the function. Functions were originally the idealization of how a varying quantity depends on another quantity. For example, the position of a planet is a function of time. Historically, the concept was elaborated with the infinitesimal calculus at the end of the 17th century, and, until the 19th century, the functions that were considered were differentiable (that is, they had a high degree of regularity). The concept of a function was formalized at the end of the 19th century in terms of set theory, and this greatly enlarged the domains of application of the concept.
>
>A function is most often denoted by letters such as $f$, $g$ and $h$, and the value of a function f at an element $x$ of its domain is denoted by $f(x)$; the numerical value resulting from the function evaluation at a particular input value is denoted by replacing $x$ with this value; for example, the value of $f$ at $x = 4$ is denoted by $f(4)$. When the function is not named and is represented by an expression $E$, the value of the function at, say, $x = 4$ may be denoted by $E\rvert_x=4$. For example, the value at $4$ of the function that maps $x$ to $(x+1)^{2}$ may be denoted by $\left.(x+1)^{2}\right\rvert _{x=4}$ (which results in 25).
>
>A function is uniquely represented by the set of all pairs (x, f (x)), called the *graph* of the function, a popular means of illustrating the function. When the domain and the codomain are sets of real numbers, each such pair may be thought of as the Cartesian coordinates of a point in the plane.

The most important operation for a function is *evaluation*.

Two evaluations are not defined for test functions in $L^2(\Omega)$. First is the evaluation. *Evaluation is not important for test functions*! Second is the *point-wise operations between two functions*, such as point-wise multiplication or division or additions or subtraction, precicely because evaluation is not defined!

There are various kinds of functions, they could be very smooth hence quite special, or very general but don't have any of the nice properties such as smoothness or continuity.

So what is Dirac $\delta$ function? It's better to consider it as an abstract things that, when given a function, it spits out a real or complex number.

First explain the name, why are they called distributions. Then introduce it as the dual space of test functions. 

Distributions can also be treated as the weak limit of functions. Explain what is weak limit and strong limit in a vector space. Example 1, $\sin(nx)$ on $[0,2\pi]$ weakly converges to $0$. In this sense, the inner product is degenerate, it's not a psudo-Riemann space.

## Schwartz functions and tempered distribution. What are they and why we need them.

Mention Parseval's theorem.

Some functions are integrable, $\int dx |f(x)|<\infty$, but their Fourier transform are not, $\int dk \tilde{f}(k) \to \infty$. Give an example.

Introduce the space of Schwartz functions and tempered distributions.

Finally, as an example, we can understand better the equality $\frac{1}{1+i\epsilon} = \text{p.v.} \frac{1}{x}  - i\pi \delta(x)$.

