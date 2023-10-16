---
layout: post
title: Some numerical Methods in Solving ODE
subtitle: 
date: 2023-10-14
author: Baiyang Zhang
header-img: img/background1.jpg
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

These methods can be adapted or combined in various ways depending on the specific problem at hand. Moreover, the choice of method often depends on the nature of the ODE (e.g., stiffness), desired accuracy, computational cost considerations, and the specific properties that need to be preserved (e.g., conservation laws).

Many modern computational packages and software (like MATLAB, Mathematica, and SciPy in Python) provide built-in functions that implement these methods, which makes it easier for users to solve ODEs without delving deeply into the numerical intricacies of each method.
### The shooting method

The shooting method is a numerical technique used to solve boundary value problems (BVPs) for ordinary differential equations (ODEs). *It's especially useful for second-order ODEs, but can be applied to higher-order equations as well*.

Here's a basic overview of the shooting method:

**The Problem:**
Suppose you have a second-order ODE given as:
$$y''(x) = f(x, y, y'),$$
with boundary conditions:
$$ y(a) = y_ a $$
$$ y(b) = y_ b $$

**The Challenge:**
Directly solving the BVP using typical ODE solvers is difficult because standard solvers require initial conditions (values of $y$ and $y'$ at a starting point), rather than boundary conditions at two separate points.

**The Shooting Method's Approach:**

1. **Guess an Initial Slope**: Choose an initial guess for the derivative $y'(a)$, let's call it $y'_ a$.

2. **Solve as an IVP**: Using the known value $y(a) = y_ a$ and the guessed $y'(a) = y'_ a$, solve the ODE as an initial value problem (IVP) over the interval $[a, b]$ using standard techniques, like the Runge-Kutta method.

3. **Check the Endpoint**: Once you've solved the ODE using your initial guess, check the value of \(y(b)\) from this solution. Compare it to the desired boundary condition \(y_b\).

4. **Adjust the Guess**: If \(y(b)\) from your solution is close to \(y_b\), then you're done. If not, adjust your guess for \(y'(a)\) and solve the IVP again. This is typically done using a root-finding algorithm like Newton's method or the secant method.

5. **Iterate**: Repeat steps 2-4 until \(y(b)\) from your solution is sufficiently close to \(y_b\), or until a set number of iterations have been reached.

### Why It's Called the "Shooting Method":
The method's name comes from the idea that you're "shooting" from one boundary towards the other. Your first "shot" might miss the target (the second boundary condition). By adjusting your aim (the initial derivative guess) and shooting again, you try to hit the target. The process is repeated until you're close enough to the target, similar to adjusting one's aim when firing at a target in archery or marksmanship.

While the shooting method can be effective, it's not guaranteed to work for all BVPs, especially when the underlying ODEs are highly nonlinear or when appropriate initial guesses are hard to ascertain. In such cases, other methods like the finite difference method or collocation methods might be more appropriate.