
—

—

### When is a function measurable?

In physics, it is very unlikely that one would have to deal with nonmeasurable functions, but still, we should rigorously define what is measurability. 

Suppose that we want to measure the length of the set of all the real numbers, namely the real number axis. Any interval if endowed with certain length, there is no problem mearing that. The union of some measurable intervals also has a well-defined length, there is no problem measuring that as well. The intersection of some measurable intervals are trickier, what if the intersection is just a point? Can you measure the length of a point? Is it zero? Hmmm, let's postpone the discussion on that. What about the complement of a measurable interval? Obviously, **if the full set is measurable**, then the complement of an interval should also be measurable. In light to be these discussions, we define the so-called $\sigma$-algebra,

A class $\mathcal{A}$ of subsets of $X$ is said to be a $\sigma$-algebra (sigma algebra) in $X$ if 
1. $X$ belongs to $\mathcal{A}$, meaning there is no element in $X$ left,
2. any **countable** unions of elements of $\mathcal{A}$ belongs to $\mathcal{A}$,
3. the complement of any elements in $\mathcal{A}$ is also in $\mathcal{A}$.

Note that the so-called sigma algebra is a class of sets with extra structures, so it makes sense to say something is in the sigma algebra.

From these properties it follows that 
- $\emptyset$ is in $\mathcal{A}$ since the complement of $\emptyset$ is $\mathcal{A}$ which is in $\mathcal{A}$. 
- If $A,B$ belong to $\mathcal{A}$, then $A - B = A\cap(B^C)$ is in $\mathcal{A}$, 
- If $A,B$ belong to $\mathcal{A}$, then $A \Delta B$ is also in $\mathcal{A}$, where $A\Delta B$ is the symmetric difference of $A$ and $B$, namely all the elements that are either in $A$ or $B$ but not in both $A$ and $B$. In set language, $A\Delta B = (A-B)\cup(B-A)$.

You will find that the definition of sigma algebra is similar to the definition of topology. However there is an essential difference: the complement of a sigma algebra is in the sigma algebra, while in topology the complement of an open set is defined to be a closed set, **not** a open set. Confusingly in topology some sets can be both open and closed, someone even invented a word, clopen. 

