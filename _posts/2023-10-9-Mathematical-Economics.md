---
layout: post
title: Lecture Notes on Mathematics in Economics
subtitle: 
date: 2023-10-09
author: Baiyang Zhang
header-img: img/background2.jpg
catalog: true
tags:
---

### Syllabus

**Semester**: Fall 2023

**Duration:** 40 Real hours (54 teaching hours), 3 real hours per class, 14 classes / 7 weeks 

**Lecturer**: Dr. Baiyang Zhang

**Office Address:** N/A

**Email**: [byzhang@henu.edu.cn](mailto:james.fisher@henu.edu.cn)

**Lecture Schedule**: Monday and Wednesday, 2:30 - 5:30

**Classroom:** Monday at Teaching building Room 3502, Wednesday at Room 109 at the School of Economics

**Textbooks and References:**

1. “*Fundamental Methods of Mathematical Economics*” by Chiang and Wainwright

2. “*Introduction to Probability*” by Grinstead and Snell

3. "*Introduction to Linear Algebra*" by Strang.

**Course Objectives:**  This course will include the basics of analysis, derivatives and integration, linear algebra, optimization, and probability, with the goal of preparing students for further course work within the School of Economics.

**Assessment Policy:** The assessments for this course will one final, in addition to several homeworks. Each item is scored on a percentage basis. The final score for the class is the weighted sum of the items’ scores.  The weights are as follows: final accounts for 70% of the final grade, and the homeworks account for the remaining 30% of the final grade.

In general, the final grade is an A when the final score is 85% or better, a B when the final score is between 70% and 84.9%, a C when the final score is between 60% and 69.9%, a D when the final score is between 50% and 59.9%, and an F when the final score is below 50%.  Assessment and final grades, however, may be curved to the benefit of the students.

**Tentative Weekly Schedule:**

CW = Chiang and Wainwright, GS = Grinstead and Snell, W = Wooldridge.

Additional review sessions may be scheduled in advance of exams.

|**Lecture**|**Topics**|**Reading**|
|----------|----------|----------|
| 1  | Introduction and Basics of Analysis | CW, Ch. 1 and 2|
| 2-4 | Linear Algebra  | CW, Ch. 4 and 5|
| 5-6 | Derivatives | CW, Ch. 5, 6, and 7|
| 7 | Integrals | CW, Ch. 13|
| 8-10 |Unconstrained Optimization | CW, Ch. 9, 10, and 11|
| 11 | Constrained Optimization with Equality Constraints | CW, Ch. 12|
| 12 | Probability Distributions and Combinatorics | GS, Ch. 1, 2 and 3|
| 13 | Common Distributions and Conditional Probability | GS, Ch. 4 and 5|
| 14 | Expected Values | GS, Ch. 6|

- - -

## Lecture 1

### Introduction and Basics of Analysis

**Mathematical Economics versus Econometrics** 

Econometrics is concerned mainly with the measurement of economic data. Hence it deals with the study of empirical observations using statistical methods of estimation and hypothesis testing. Indeed, empirical studies and theoretical analyses are often complementary and mutually reinforcing. On the one hand, theories must be tested against empirical data for validity before they can be applied with confidence. On the other, statistical work needs economic theory as a guide, in order to determine the most relevant and fruitful direction of research.

**Economic Models**

A model is essentially and necessarily an abstraction from the real world. The sensible procedure is to pick out what appeals to our reason to be the primary factors and relationships relevant to our problem and to focus our attention on these alone. 

**Mathematics from a bird's eye view**

Explain: Algebra, Geometry, and Analysis.

Most people who have done some high school mathematics will think of algebra as the sort of mathematics that results when you substitute letters for numbers. Algebra will often be contrasted with arithmetic, which is a more direct study of the numbers themselves. 

There is, however, a different contrast, between algebra and geometry, which is much more important at an advanced level. The high school conception of geometry is that it is the study of `shapes` such as circles, triangles, cubes, and spheres together with concepts such as rotations, reflections, symmetries, and so on. Thus, the objects of geometry, and the processes that they undergo, have a much more visual character than the equations of algebra. 

Some parts of mathematics involve manipulating symbols according to certain rules: for example, a true equation remains true if you “do the same to both sides.” These parts would typically be thought of as algebraic, whereas other parts are concerned with concepts that can be visualized, and these are typically thought of as geometrical.

One is more symbolic and the other more pictorial.

The word “analysis,” used to denote a branch of mathematics, is not one that features at high school level. However, the word “calculus” is much more familiar, and differentiation and integration are good examples of mathematics that would be classified as analysis rather than algebra or geometry. The reason for this is that they involve limiting processes. For example, the derivative of a function f at a point x is the limit of the gradients of a sequence of chords of the graph of $f$ , and the area of a shape with a curved boundary is defined to be the limit of the areas of rectilinear regions that fill up more and more of the shape. 

Thus, as a first approximation, one might say that a branch of mathematics belongs to analysis if it involves limiting processes, whereas it belongs to algebra if you can get to the answer after just a finite sequence of steps.

**Branches of Mathematics**

- Algebra. Deals with number systems, polynomials, and more abstract structures such as groups, fields, vector spaces, and rings. 
- Number theory.
- Algebraic geometry
- Analysis
    - The study of PDE, ODE.
    - Dynamics. What happens when you take a simple process and do it over and over again?
- Logic
	- Set theory
	- Category theory
- Combinatorics
- Theoretical Computer Science
- Probability
- Mathematical Physics

- - -

1. *Math as a language with its own vocabulary and syntax.* 
2. *Introduction of set theory, including the basic concepts and operations that can be done to them.*
3. *Introduce the concept of function and functional. They are nothing but various maps from one set to another.* 
4. The number system. Explain integers, rational numbers, real numbers and complex numbers. $\mathbb{R},\mathbb{N}, \mathbb{Z}, \mathbb{Q}$. 

## Lecture 2


"You can't add apples and oranges." In a strange way, this is the reason for vectors. We have two separate numbers $v_  {1}$ and $v_  {2}$. The pair produces a two-dimensional vector $\vec{v}$. Explain the following concepts:
- column,
- components.

We don't add $v_  {1}$ and $v_  {2}$, but we do add vectors of the same type. Explain vector addition. We want to add apples with apples. 

Explain what is a scalar, and scalar multiplication. 

Given two vectors $\vec{v}$ and $\vec{w}$, explain the linear combination of them. 

This big view, taking all the combinations of $\vec{v}$ and $\vec{w}$, is linear algebra at work.

Illustrate the addition of vectors using arrows.

Introduce 
- dot product,
- length.

The dot product is gonna be needed when defining the action of a matrix on a vector. 

After introducing the product rules in two different ways, we introduce the linear equations. 

### Lecture 3

**Linear combination:**

Imagine you have a collection of building blocks, and each block represents a different item. A "linear combination" is like creating a new structure using these blocks, where you decide:

1. **How many of each block to use**: This is similar to multiplying the block (or item) by a number.
2. **How to combine them**: Essentially, you're just adding these multiplied blocks together.

Let's use a simpler example:

Imagine you have two types of fruit: apples and bananas. 

A "linear combination" of apples and bananas could be:

- 3 apples + 2 bananas
- 5 apples + 1 banana
- 2 apples - 4 bananas (Yes, in mathematics, you can have negative bananas! Just think of it as owing bananas to someone.)

In each of these cases, the number of apples and bananas you decide to use (3, 2, 5, 1, etc.) are called "coefficients". 

When it comes to mathematics and vectors, the idea is the same. You're combining different vectors using certain coefficients to produce a new vector. But the basic idea is just like combining apples and bananas!

- - -

There are many ways to look at a matrix. 

1. **Table of Numbers**: At its core, a matrix is like a table or grid filled with numbers. Think of it like a spreadsheet or a bingo card. Each number sits in its own little box, and these boxes are organized into rows and columns.

2. **Collection of Column Vectors**: Imagine each column in that table as a list of numbers. This list can be seen as a "column vector". So, a matrix can be thought of as a collection of these column vectors, standing side by side. For example, a matrix with three columns is like having three lists (or column vectors) put together.

3. **Collection of Row Vectors**: Similarly, you can think of each row in the matrix as a separate "row vector". So, another way to view a matrix is as a stack of these row vectors, one on top of the other.

4. **Transformation Machine**(we will go to more details in this class): This is a more advanced way to think about matrices, especially in linear algebra. Imagine you have a point on a graph. A matrix can act as a "machine" where you input your point, and out comes a new point. This new point might be stretched, squished, rotated, or even flipped compared to the original. In essence, the matrix transformed it!

5. **System of Equations**(topic of this class too): If you've ever dealt with multiple equations at once (like trying to figure out both the price of a burger and fries when given combined costs), matrices can represent these systems. Each row could represent a different equation, and the numbers in that row represent the coefficients of variables in that equation.

6. **Storage and Organization**: In computer science and data analysis, matrices can be used to store data. For instance, consider ratings given by users to movies on a streaming platform. Each row might represent a user, each column might represent a movie, and the number in a specific box represents the rating that user gave to that movie.

These are just some of the many ways to look at matrices. Depending on the subject (like physics, computer graphics, or economics), matrices might take on other interesting interpretations!

- - -

**The multiplication of matrices**

**The Basics**:

Matrix multiplication is not just multiplying numbers. Instead, it's a combination of multiplication and addition. Remember, the way you multiply matrices is quite different from multiplying regular numbers, so it's essential to understand the steps and rules.

**The Key Rule**:

For two matrices to be multiplied, the number of columns in the first matrix must be equal to the number of rows in the second matrix. This is a crucial rule. 

If Matrix A has dimensions of $m \times n$ (meaning $m$ rows and $n$ columns) and Matrix B has dimensions of $p \times q$ (meaning $p$ rows and $q$ columns), then for A and B to be multipliable, $n$ must equal $p$. The resulting matrix will have dimensions $m \times q$.

**How to Multiply**:

Let's consider two simple matrices:

Matrix A:
$$
\begin{pmatrix}
1 & 2 \\
3 & 4
\end{pmatrix}
$$
Matrix B:
$$
\begin{pmatrix}
2 & 1 \\
0 & 3
\end{pmatrix}
$$

To multiply them:

1. **First element of the result (top-left corner)**:
   - Take the first row of Matrix A: (1, 2).
   - Take the first column of Matrix B: (2, 0).
   - Multiply corresponding elements and add them up: (1×2) + (2×0) = 2.

2. **Second element in the first row (top-right corner)**:
   - Take the first row of Matrix A: (1, 2).
   - Take the second column of Matrix B: (1, 3).
   - Multiply corresponding elements and add them up: (1×1) + (2×3) = 7.

3. **First element in the second row (bottom-left corner)**:
   - Take the second row of Matrix A: (3, 4).
   - Take the first column of Matrix B: (2, 0).
   - Multiply and add: (3×2) + (4×0) = 6.

4. **Second element in the second row (bottom-right corner)**:
   - Take the second row of Matrix A: (3, 4).
   - Take the second column of Matrix B: (1, 3).
   - Multiply and add: (3×1) + (4×3) = 15.

The resulting matrix is:

$$
\begin{pmatrix}
2 & 7 \\
6 & 15
\end{pmatrix}
$$
**Visualization**:

Imagine Matrix A's rows as horizontal hands reaching out, and Matrix B's columns as vertical hands reaching up. When these hands "high-five", they form the elements of the resulting matrix by the rule we just discussed.

**Practice**:

The best way to get comfortable with matrix multiplication is to practice. Start with smaller matrices, understand the patterns, and then work with larger ones.

Remember, the rule of matching columns of the first matrix to rows of the second is crucial. If they don't match, the matrices can't be multiplied.

- - -

### Example: Production in a Shoe Factory

Imagine you run a small shoe factory. You produce two types of shoes: sneakers and boots.

**Vectors**:
1. **Production Vector** for a given week:
   - Sneakers: 100 pairs
   - Boots: 50 pairs

   We can represent this as:
   $$
   \text{Shoes} = \begin{bmatrix} 100 \\ 50 \end{bmatrix}
   $$

2. **Cost Vector** for producing each type of shoe:
   - Cost to produce one pair of sneakers: $20
   - Cost to produce one pair of boots: $40

   This can be represented as:
   $$
   \text{Cost} = \begin{bmatrix} 20 \\ 40 \end{bmatrix}
   $$

**Matrix**:
Let's say, to produce each shoe, you need two main raw materials: leather and rubber. We can create a **Material Requirement Matrix** that tells us how much of each material is required to produce one unit of each shoe type.

For example:
- Each pair of sneakers requires 1 unit of leather and 2 units of rubber.
- Each pair of boots requires 3 units of leather and 1 unit of rubber.

This matrix is:
$$
\text{Materials} = \begin{bmatrix} 1 & 2 \\ 3 & 1 \end{bmatrix}
$$
Where the first column corresponds to the requirements for sneakers and the second column to boots.

**Matrix Multiplication**:

Now, suppose you want to find out how much raw material (leather and rubber) you'll need for the entire week's production.

To do this, you'd multiply the Material Requirement Matrix by the Production Vector:
$$
\text{Total Materials} = \text{Materials} \times \text{Shoes}
$$

Multiplying, we get:
$$
\text{Total Materials} = \begin{bmatrix} 1 & 2 \\ 3 & 1 \end{bmatrix} \times \begin{bmatrix} 100 \\ 50 \end{bmatrix} = \begin{bmatrix} 200 \\ 350 \end{bmatrix}
$$

So, you'll need:
- 200 units of leather (100 for the sneakers and 150 for the boots)
- 350 units of rubber (200 for the sneakers and 150 for the boots)

This simple example demonstrates the power of vectors and matrices in understanding and organizing economic production. By extending this model with more products and more inputs, students can grasp the importance and utility of linear algebra in economics.