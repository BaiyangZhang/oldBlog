---
layout: post
title: Note on Numerical Methods in Solving ODE
subtitle: 
date: 2023-10-16
author: Baiyang Zhang
header-img: img/background2.jpg
catalog: true
tags:
---

In my line of work I constantly need to solve unsolvable ODEs and PDEs, unsolvable in the sense that it is impossible to get an analytical solution. What we do is to turn to numerical methods for help. For instance, just recently I need to solve a modified version of the Skyrme equation (the equation of motion resulted from the Skyrme model). I thought it would be helpful to summarize what I've learnt here. 

Various numerical methods have been developed to tackle different types of ODEs (initial value problems, boundary value problems, linear, nonlinear, etc.). Here are some of the most popular numerical methods for solving ODEs:

1. **Euler's Method**:
   - This is the simplest one-step method.
   - It's based on a linear approximation of the solution.
   - While straightforward and instructive for educational purposes, it's rarely used in practice due to its low accuracy and stability issues.

2. **Runge-Kutta Methods**:
   - These are a family of iterative methods.
   - The 4th order Runge-Kutta (often called RK4) is particularly popular due to its balance between accuracy and computational cost.
   
3. **Leapfrog (or Midpoint) Method**:
   - A second-order method that is particularly useful in cases where energy conservation is crucial, such as in molecular dynamics simulations.

4. **Predictor-Corrector Methods**:
   - These methods predict a solution using an explicit method and then correct it with an implicit method.
   - Examples include the Adams-Bashforth (predictor) and Adams-Moulton (corrector) methods.

5. **Backward Differentiation Formulas (BDF)**:
   - These are implicit multi-step methods.
   - Commonly used for stiff ODEs.

6. **Multistep Methods**:
   - These methods use values at multiple previous time steps.
   - Examples include the Adams methods.

7. **Symplectic Integrators**:
   - These are used for Hamiltonian systems where preserving the symplectic structure (related to conservation of energy) is essential.

8. **Implicit Methods**:
   - Used frequently for stiff equations where explicit methods require prohibitively small time steps.
   - Examples include the backward Euler method and the trapezoidal rule.

9. **Shooting Method**:
   - Primarily used for boundary value problems (BVPs).
   - Converts a BVP into an initial value problem (IVP) and then solves the IVP.

10. **Relaxation Methods**:
   - Also for boundary value problems.
   - Iteratively refines an initial guess to the solution.

11. **Finite Difference Method**:
   - Converts differential equations into difference equations, which can then be solved algebraically.
   - Often used for both ODEs and PDEs.

12. **Collocation Methods**:
   - This approach seeks an approximate solution by considering values at specific points (collocation points).

13. Continuation method, which we will go to detail later.


- - -

These methods can be adapted or combined in various ways depending on the specific problem at hand. Moreover, the choice of method often depends on the nature of the ODE (e.g., stiffness), desired accuracy, computational cost considerations, and the specific properties that need to be preserved (e.g., conservation laws).

Many modern computational packages and software (like MATLAB, Mathematica, and SciPy in Python) provide built-in functions that implement these methods, which makes it easier for users to solve ODEs without delving deeply into the numerical intricacies of each method.

**Stiffness.**

Imagine you're on a winding road with both smooth curves and sharp turns. If you're driving a car along this road at a constant speed, the smooth curves can be navigated quite easily, but the sharp turns require more caution and precision.

Similarly, in the context of differential equations, there can be parts of the solution that change very slowly (smooth curves) and others that change extremely rapidly (sharp turns). When a differential equation has solutions with widely differing rates of change over its domain, we say that the equation is "stiff." When you're solving a stiff differential equation using numerical methods (like the Euler method or the Runge-Kutta method), you'll notice that the rapid changes require very small step sizes for accurate solutions. However, the slow-changing parts don't need such small steps. If you choose a step size suitable for the rapidly changing sections (very small), the computation can become inefficient because you're using more steps than necessary for the slow-changing sections. On the other hand, if you choose a larger step size suitable for the slow-changing sections, the solution can become unstable or highly inaccurate in the rapidly changing sections.

To efficiently and accurately solve stiff differential equations, specialized numerical methods have been developed, known as "stiff solvers." These solvers are designed to adaptively handle the challenges posed by stiffness, allowing for stable and efficient computation.

### Some parameters

I collected the following values from the Adkins:Nappi:1984 paper[^1],  
$$
m_ {\pi} = 108 \text{ MeV}, \quad  e=4.82,\quad  F_ {\pi} = \frac{m_ {\pi}}{0.263 e}
$$
which gives us 
$$
\begin{align}
m_ {1} &= 0.526, \\
m_ {2} &= 1.052.
\end{align}
$$
### The shooting method

The shooting method is a numerical technique used to solve boundary value problems (BVPs) for ordinary differential equations (ODEs). *It's especially useful for second-order ODEs, but can be applied to higher-order equations as well*.

Here's a basic overview of the shooting method:

**The Problem:**
Suppose you have a second-order ODE given as:
$$y''(x) = f(x, y, y'),$$
with boundary conditions:
$$ y(a) = y_  a $$
$$ y(b) = y_  b $$

**The Challenge:**
Directly solving the BVP using typical ODE solvers is difficult because standard solvers require initial conditions (values of $y$ and $y'$ at a starting point), rather than boundary conditions at two separate points.

**The Shooting Method's Approach:**

1. **Guess an Initial Slope**: Choose an initial guess for the derivative $y'(a)$, let's call it $y'_  a$.

2. **Solve as an IVP**: Using the known value $y(a) = y_ a$ and the guessed $y'(a) = y'_  a$ then solve the ODE as an initial value problem (IVP) over the interval $[a, b]$ using standard techniques, like the Runge-Kutta method.

3. **Check the Endpoint**: Once you've solved the ODE using your initial guess, check the value of $y(b)$ from this solution. Compare it to the desired boundary condition $y_ b$.

4. **Adjust the Guess**: If $y(b)$ from your solution is close to $y_ b$, then you're done. If not, adjust your guess for $y'(a)$ and solve the IVP again. This is typically done using a root-finding algorithm like Newton's method or the secant method.

5. **Iterate**: Repeat steps 2-4 until $y(b)$ from your solution is sufficiently close to $y_ b$, or until a set number of iterations have been reached.

The method's name comes from the idea that you're "shooting" from one boundary towards the other. Your first "shot" might miss the target (the second boundary condition). By adjusting your aim (the initial derivative guess) and shoot again, you try to hit the target. The process is repeated until you're close enough to the target, similar to adjusting one's aim when firing at a target in marksmanship.

While the shooting method can be effective, it's not guaranteed to work for all BVPs, especially when the underlying ODEs are highly nonlinear or when appropriate initial guesses are hard to ascertain. Unfortunately, the solving of the modified Skyrme equation seems to fall in the category, as I am about to go to details right now.

With the parameters listed in the previous chapter, I tried to solve the equation of motion using shooting method with the following codes 

```matlab
bc1 = f[0] == Pi;
bc2 = f[50] == 0;

approximateSolution = Pi (1 - Tanh[r]);

initialGuessY = 
  approximateSolution /. 
   r -> 0;  (*Evaluate approximate solution at x=0*)
initialGuessYPrime = 
  D[approximateSolution, r] /. r -> 0;  (*Evaluate derivative at x=0*)

shootingMethod = {"Shooting", 
   "StartingInitialConditions" -> {f[0] == initialGuessY, 
   f'[0] == initialGuessYPrime}};

solutionTest1 = Module[{\[Eta] = 1, m1 = 0.526`, m2 = 1.052`},
	 shootingMethod = {"Shooting", 
    "StartingInitialConditions" -> {f[0] == Pi, f'[0] == -6}};
  NDSolve[{eom, bc1, bc2}, f, {r, 0, 50}, PrecisionGoal -> 7, 
   AccuracyGoal -> 7]]
```

where eom is short for the equation of motion, given by
$$
\begin{align}
\text{eom} =&-2 r^4 f''(r)-4 \eta  r^2 f''(r) \sin ^2(f(r))+4 \eta  r^3 f'(r)^3-4 r^3 f'(r)^3-4 r^3 f'(r)-2 \eta  r^2 f'(r)^2 \sin (2 f(r)) \\
&+6 \eta  r^4 f'(r)^2 f''(r)-6 r^4 f'(r)^2 f''(r)+2 \text{m1}^2 r^4 \sin (f(r))+2 \text{m2}^2 r^4 \sin (f(r)) \\
&-\text{m2}^2 r^4 \sin (2 f(r))+2 r^2 \sin (2 f(r))+\sin (2 f(r))-\sin (2 f(r)) \cos (2 f(r)) \\
&==0.
\end{align}
$$

However the computation takes a long time and yields a nonsensical result, 
![](/img/eom.png)

which clearly doesn't make any sense. Thus we have to consider a different method, the so-called `continuation method` or `homotopy method`.

[^1]:Nuclear Physics B233 (1984) 109-115, doi: 10.1016/0550-3213(84)90172-x

