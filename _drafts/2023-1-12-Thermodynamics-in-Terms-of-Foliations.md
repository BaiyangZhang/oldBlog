---
layout:     post   				    # 使用的布局（不需要改）
title:     Thermodynamics-in-Terms-of-Foliations			# 标题 
subtitle:   A Heristic aproach
date:       2023-1-12 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/mathArt5.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - Geometry
    - physics
    - Holonomy
    - Notes
---

>Disclaimer: Nothing in this note is original. Including the figures.

Around 1909, Caratheodory was urged by Max Born to come up with an axiomatic treatment of thermodynamics. As a result, Caratheodory made use of Frobenius's theorem and constructed a rather mathematical treatment of thermodynamics. In this note we will only superficially look at the theory.

Consider a system of fluids separated into $n$ chambers by "diathermous" membranes, namely membranes that allow only the passage of heat, not fluids, as shown in the figure below. Each chamber has its own pressure and volume, denoted by $p_{i}$ and $v_{i}$. 

![fluid](/img/chamber.png)

We assume that each state of the system is a `thermal equilibrium` state. We assume that the membranes are stretchy enough so that in the equilibrium state the pressure is uniform between different chambers, $p_{1}=p_{2}-\dots=p_{n}$. The equations of state (for instance, $p_{i}v_{i}=n_{i}RT$)  will allow us to eliminate all but one pressure, say $p_{1}$. Then the state is described by $n+1$ parameters, $p_{1},v_{1},\dots,v_{n}$. The uniform temperature is given by the n-tuple from the equation of state. It is important to assume that there is a global `internal energy` function $U$ of the system that can be used instead $p_{1}$. The equilibrium state is then described by $n+1$ parameters,
$$
v_{0}:= U,v_{1},\dots,v_{n}.
$$
Each $v_{0}$ will fix a point in the `state space`, namely the space of all the possible states. The state space then would be a $n+1$ dimensional manifold. 

Next consider a sequence of states, forming a continuous change of the states, the change is slow enough that each state during the change is itself an equilibrium state. Such a slow change of states traces a curve in the state space. Such transition is sometimes called `quasi-static`. 

We shall also consider non-quasi-static transitions, such as "stirring". In the space of states, such a transition starts at some point $x$ and ends at some other points $y$, but since there is no sequence of equilibrium states intermediating the initial and final states, there is no path in the state space joining $x$ to $y$ (since each point in the state space represents a equilibrium state by construction). These corresponds to irreversible processes. Schematically, we shall draw such transitions by a *dash line* joining $x$ to $y$.

On the state manifold (the manifold of state space), we assume the existence of a `work 1-form` $W$, describing the work done *by* the system due to a change of volume.
$$
W := \sum_{i=1}^{n} p_{i} \,dv_{i} = \sum_{i=1}^{n} p_{i}(U,v_{1},\dots,v_{n})\, dv_{i}.
$$
Recall that when a form is closed, the integral of it along some boundary is always zero, thanks to the Stokes theorem. It is important to note that here the work 1-form $W$ is not supposed to be closed, thus if the system undergoes a loop of state transition, the total energy done by the system may not be zero. The line integral of $W$ is in general dependent upon the path joining the endpoint states.

We also assume the existence of a `heat 1-form` 
$$
Q:= \sum_{i=1}^{n} Q_{i}(U,v_{1},\dots,v_{n})\,dv_{i}
$$
representing the heat added or removed from the system. At first glance it seems strange that $Q$ should depend on $dv_{i}$, we will say more about it later. Again, $Q$ is not supposed to be closed, and we shall always assume that $Q$ never vanishes. Note that in some other texts $Q$ is derived, rather than postulated as here. 

**Remark.** In some textbooks the 1-form $W$ and $Q$ are denoted by $d$ with a bar crossing the upper part, to show that they are different from usual $dQ$ and $dW$. It is very misleading, since that in the language of differential forms, $dW$ would be an exact form, but the work 1-form is in no means exact. The same goes for the heat 1-form.

**The first law of thermodynamics** says that 
$$
dU = Q-W.
$$
**This is the conservation of energy**.

- - -

Next we show some elementary changes of states, and how the look like in the state space.

1. Heating at constant volume. It is shown as $\gamma_{I}$ in the figure below. The work 1-form vanishes when evaluated on the tangent $\dot{\gamma}_{I}$. The conservation of energy says that $dU = Q$.
2. Quasi-static adiabatic process. There is no heat added to the system, thus $Q=0$ along the path. It is shown by $\gamma_{I I}$.
3. Stirring at constant volume. Since it is not quasi-static we cannot represent it by a curve in the state space. We can only schematically represent it by connecting $x$ and $y'$ with a dashed curve. $Q,W$ make no sense for this process.  

![transition](/img/transition.jpg)


