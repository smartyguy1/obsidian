# Computing the nullspace

Suppose:
$$
A = \begin{bmatrix}1 & 2 & 2 & 2 \\ 2 & 4 & 6 & 8 \\ 3 & 6 & 8 & 10\end{bmatrix}
$$
(Note that the columns of this matrix $A$ are not independent.) Our algorithm for computing the [[Column Space and Nullspace|nullspace]] of this matrix uses the method of [[Elimination With matrices|elimination]], despite the fact that $A$ is not invertible. 

We don't need to use an augmented matrix because the right-side(the vector $\pmb{b}$) is $\pmb{0}$ in this computation.

*The row operations used in elimination don't change the solution of $A\pmb{x}=\pmb{b}$ so they don't change the nullspace.*(They do affect the column space.)

First Step of elimination:
$$
A = \begin{bmatrix}1 & 2 & 2 & 2 \\ 2 & 4 & 6 & 8 \\ 3 & 6 & 8 & 10\end{bmatrix} \longrightarrow \begin{bmatrix}1 & 2 & 2 & 2 \\ 0 & 0 & 2 & 4 \\ 0 & 0 & 2 & 4\end{bmatrix}
$$
==We don't find a pivot in the second column, so out next pivot is the 2 in the 3rd column of the 2nd row:==
$$
\begin{bmatrix}\pmb{1} & 2 & 2 & 2 \\ 0 & 0 & \pmb{2} & 4 \\ 0 & 0 & 2 & 4\end{bmatrix} \longrightarrow \begin{bmatrix}\pmb{1} & 2 & 2 & 2 \\ 0 & 0 & \pmb{2} & 4 \\ 0 & 0 & 0 & 0\end{bmatrix} = \large{U}
$$
The matrix $U$ is in *echelon*(staircase) form. The 3rd row is zero because row 3 was a linear combination of rows 1 and 2; it was eliminated. ^b5db2e

The rank of a matrix $A$ equals the number of pivots it has. In this example, the rank of $A$ (and of $U$) is 2.

## Special Solutions

Once we've found $U$ we can use back-substitution  to find the solution $\pmb{x}$ to the equation $U\pmb{x}=\pmb{0}$. ==In our example, columns 1 and 3 are *pivot columns* containing pivots, and columns 2 and 4 are *free columns*. We can assign any value to $x_2$ and $x_4$; we call these *free variables*==. **Suppose $x_2=1$ and $x_{4}= 0$** Then:
$$
2x_{3}+4x_{4}=0 \implies x_{3}=0
$$
and:
$$
x_{1}+2x_{2}+2x_{3}+2x_{4} = 0 \implies x_{1}= -2
$$
So one solution is $\pmb{x}=\begin{bmatrix}-2 \\ 1 \\ 0 \\ 0\end{bmatrix}$ (because the 2nd column is just twice the 1st). Any multiple of this vector is in the nullspace.
==Letting a different free variable equal 1 and setting the other free variables equal to zero gives us other vectors in the nullspace.==For eg:
$$
\pmb{x}=\begin{bmatrix}2 \\ 0 \\ -2 \\ 1\end{bmatrix}
$$
has $x_{4}=1$ and $x_{2}=0$. ==The nullspace of $A$ is the collection of a all linear combinations of these ''special solution'' vectors.==
We can say,
$$
N(A) = c\begin{bmatrix}-2 \\ 1 \\ 0 \\ 0\end{bmatrix} + d\begin{bmatrix}2 \\ 0 \\ -2 \\ 1\end{bmatrix}
$$
==The [[Solving Ax=b; Row Reduced form R#^61fcc2|rank]]  $r$ of $A$ equals the number of pivot columns, so the number of free columns is $n-r$==; $n$ = the no. of variables. This gives the **number of special solution vectors** and the **dimension of the nullspace**.

# Reduced row echelon form

^5cdbe8

==By continuing to use the method of elimination we can convert $U$ to a matrix $R$ in *reduced row echelon form*(rref form), with pivots equal to 1 and zeroes above and below the pivots.== Echelon is derived from the word echelle meaning ladder. and we can see that the pivots form a kind of stairs.
$$
U = \begin{bmatrix}1 & 2 & 2 & 2 \\ 0 & 0 & 2 & 4 \\ 0 & 0 & 0 & 0\end{bmatrix} \rightarrow \begin{bmatrix}1 & 2 & 0 & -2 \\ 0 & 0 & 2 & 4 \\ 0 & 0 & 0 & 0\end{bmatrix} \rightarrow \begin{bmatrix}1 & 2 & 0 & -2 \\ 0 & 0 & 1 & 2 \\  0& 0 & 0 & 0\end{bmatrix} = R 
$$
$$\begin{align*}
(1) & \ R_{1}\rightarrow R_{1}-R_{2}\\
(2) & \ R_{2}\rightarrow \frac{1}{2}R_{2}
\end{align*}
$$
![[Pasted image 20240723163147.png]]
*(2) was to get 1s at the pivot positions*.
By exchanging some columns, R can be rewritten with a copy of the identity matrix in the upper left corner, possibly followed by some free columns on the right. If some rows of $A$ are linearly dependent, the lower rows of the matrix $R$ will be filled with zeros:
$$
R= \begin{bmatrix}I & F \\ 0 & 0\end{bmatrix}
$$
(Here $I$ is an $r$ by $r$ square matrix.) and for the given example: $F = \begin{bmatrix}2 & -2 \\ 1 & 2\end{bmatrix}$ 
If $N$ is the *nullspace matrix* $N = \begin{bmatrix}-F \\ I\end{bmatrix}$ then $RN=O$.(Here $I$ is an $n-r$ by $n-r$ square matrix and O is an $m$ by $n-r$ matrix.) The columns of $N$ are the special solutions.

![[2024-07-16-Note-18-52.pdf]]