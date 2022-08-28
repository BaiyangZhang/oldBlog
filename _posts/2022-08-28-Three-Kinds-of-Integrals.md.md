---
layout:     post   				    # 使用的布局（不需要改）
title:      Three Kinds of Integrals				# 标题 
subtitle:   The signed, unsigned and indefinite     #副标题
date:       2022-08-28				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/mathArt3.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - math
    - functional analysis
    - Integral
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