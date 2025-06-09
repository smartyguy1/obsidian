Consider a Physical System that stores information, let us call it X.
Assume X can be in one of finite number of [[Definitions#^f73ba6|Classical Sates]]
Let us denote denote this classical state set by $\Sigma$ 

For example:
>- If X is a bit then $\Sigma$ = {0,1}
>- If X is an outcome of a die $\Sigma$ = {1,2,3,4,5,6}
>If X is a switch of a fan then $\Sigma$ = {High, Medium, Low, Off}

There has to be at least 1 classical state that the system can be in and there has to be at least 2 classical states if the system is going to be useful at all for storing information.

There May be uncertainty about the classical state of a system where each classical state has some probability associated with it.

For example: If X is a bit, the Probability of it being 0 is 1/4 and it being 1 is 3/4, 
$$
Pr(X = 0) = \frac{1}{4}\ and\ \Pr(X = 1)\ = \frac{3}{4} 
$$
This is a ==Probabilistic State==

A [[Definitions#^62779f|Succinct]] way to represent probabilistic state is by a ==column vector==
$\begin{pmatrix} \frac{3}{4} \\ \frac{1}{4}  \end{pmatrix}$ Here the $a_{11}$ element represents $P(X = 0)$ and $a_{21}$  $P(X = 1)$

==This Vector is a Probability Vector==
- All entries are non-ve real numbers.
- The sum of the entries is 1.
- There is one entry for each classical state of the system we are talking about
# Dirac Notation(First Part)
Let $\Sigma$ be any classical state set, and assume the elements of $\Sigma$ have been placed in correspondence with the integers 1,....,$|\Sigma|$. ($|\Sigma|$ this means the number of elements within the set)
(We can choose any order but the important thing is that we stick to it.)

We denote the column vector by $\ket{a}$(read as ket a) having a 1 in the entry corresponding to $a \in \Sigma$ , with 0 for all other entries.
For example if X is a bit
>$\Sigma = {0,1}$ , then
>$$
\ket{0} = \begin{pmatrix} 1 \\ 0 \end{pmatrix} \text{ and  } \ket{1} = \begin{pmatrix} 0 \\ 1 \end{pmatrix} 
$$

Example2:
> if $\Sigma$ = {clover, Diamond, Heart, Spade}, then we might choose to order These states like this: C, D, H, S. This yields.
> $$
\ket{C} = \begin{pmatrix} 1\\0\\0\\0 \end{pmatrix} \text{ } \ket{D} = \begin{pmatrix} 0\\1\\0\\0 \end{pmatrix} \text{ } \ket{H} = \begin{pmatrix} 0\\0\\1\\0 \end{pmatrix} \text{ } \ket{S} = \begin{pmatrix} 0\\0\\0\\1 \end{pmatrix} \text{ }
$$

Vectors of this form are called ==standard basis vectors==
==Every vector can be expressed uniquely as a linear combination of standard basis vectors.==
Example:
>$$
\begin{pmatrix} \frac{3}{4} \\ \frac{1}{4}  \end{pmatrix} = \frac{3}{4} \ket{0} + \frac{1}{4}\ket{1}
$$

# Measuring Probabilistic States
What happens when we measure a system X while it is in some Probabilistic sate?
We see a classical state, chosen at random according to the probabilities.
>(For the sake of the mathematical framework we think of it this way, that the definitive classical state on measurement is chosen at random according to the probabilities.)

Suppose we see the classical state $a \in \Sigma$
This changes the probabilistic state of X (from out viewpoint): having recognized that X is in the classical date $a$, we now have
$$
Pr(X = a) =1
$$
The probabilities do not have any significance now since we know the state of X and there is no uncertainty about this.

==We can say that X is in a probabilistic state where the probability of it being in a state a in 1==
This probabilistic state is represented by the vector $\ket{a}$.


To another person who didn't happen to see what the state of X was when we measured it, the probabilistic state wouldn't change because we measured it.

# Classical Operations
## Deterministic Operations
Every function $f: \Sigma \rightarrow \Sigma$  describes a Deterministic Operation that transforms the classical state $a$ into $f(a)$ , for each $a \in \Sigma$ 

Given any function $f: \Sigma \rightarrow \Sigma$ , there is a (unique) matrix M satisfying
$M \ket{a} = \ket{f(a)}$    (for every $a \in \Sigma$)

This matrix has exactly one 1 in each column, and 0 in all other entries.

$$
M(b,a) = \left\{\begin{array}{rcl}1 & b = f(a)\\ 0 & b \ne f(a) \end{array}\right.
$$
This describes a matrix whose row corresponds to $b$ and column corresponds to $a$.

The action of this operation is described by matrix-vector multiplication:
$$
\nu \longmapsto  M\nu
$$
Example
>