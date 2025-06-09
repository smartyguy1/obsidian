When does $Ax=b$ have solutions $\pmb{x}$, and how can we describe those solutions?

# Solvability conditions on b
We again use the example:
$$
A = \begin{bmatrix}1 & 2 & 2 & 2 \\ 2 & 4 & 6 & 8 \\ 3 & 6 & 8 & 10\end{bmatrix}.
$$
Here, $R_{3}= R_{2}+R_{1}$, so we know that it $Ax=b$ the third component of $b=\begin{bmatrix}b_1 \\ b_2 \\ b_3\end{bmatrix}$ , $b_{3}=b_{2}+b_{1}$. ==If  $b_{3}$ does not satisfy this the system has no solutions.== 
If a combination of rows of $A$ gives the zero row, then the same combinations of the entries of $\pmb{b}$ must equal zero too.

One way to find out the solvability is to use elimination on the augmented matrix.
$$
\begin{bmatrix}1 & 2 & 2 & 2  & b_1 \\ 2 & 4 & 6 & 8 & b_2 \\ 3 & 6 & 8 & 10 & b_3\end{bmatrix} \rightarrow \dots \rightarrow \begin{bmatrix}1 & 2 & 2 & 2 & b_1 \\ 0 & 0 & 2 & 4 & b_{2}-2b_{1} \\ 0 & 0 & 0 & 0 & b_{3}-b_{2}-b_{1}\end{bmatrix}
$$
If $A\pmb{x}=\pmb{b}$ has a solution, then $b_{3}-b_{2}-b_{1}=0$ For example we could choose $\pmb{b} = \begin{bmatrix}1 \\ 5 \\ 6\end{bmatrix}$.
From an [[Column Space and Nullspace#^4bb7f7|earlier lecture]], we know that $Ax=b$ is solvable exactly when b is in the column space $C(A)$. We have these two conditions on $\pmb{b}$ but in fact they are equivalent.

# Complete Solution

In order to find all solutions to $Ax=b$ we first check that the equation is solvable, then find a particular solution. *We get the complete solution of the equation by adding the particular solution to all the vectors in the nullspace.*

## A particular solution
One way to find a particular solution is to set all **free variables** to zero, then solve for the pivot variables.
For our example matrix $A$ we let $x_{2}=x_{4}=0$ to get the system of equations:
$$
\begin{align}
x_{1}+2x_{3} & \ = \ 1 \\
2x_{3} & \ = \ 3
\end{align}
$$
which has the solution $x_{3}= \frac{3}{2}$, $x_1 = -2$. Our particular solution is:
$$
x_{p}=\begin{bmatrix}-2 \\ 0 \\ 3/2 \\ 0\end{bmatrix}
$$
## Combined with nullspace

The general solution to $Ax=b$ is given by $\pmb{x}_{complete}=\pmb{x}_{p}+\pmb{x}_{n}$, where $\pmb{x}_{n}$ is a generic vector in the nullspace. 
$$
\begin{align*}
Ax_{p} &= b \\
Ax_{n} &= 0 \\
&\implies A(\pmb{x}_{p}+\pmb{x}_{n}) = b\\
\text{Or}\\
A\pmb{x}_{complete} &= b
\end{align*}
$$

This is true for every $\pmb{x}_{n}$ in the nullspace.
In in the [[Pivot Variables, Special Solutions|last lecture]] we learned that the nullspace of $A$ is the collection of all combinations of the special solutions $\begin{bmatrix}-2 \\ 1 \\ 0 \\ 0 \end{bmatrix}$ and $\begin{bmatrix}2 \\ 0 \\ -2 \\ 1\end{bmatrix}$. So the complete solution to the equation $A\pmb{x} = \begin{bmatrix}1 \\ 5 \\ 6\end{bmatrix}$ is :
$$
\pmb{x}_{complete}=
\begin{bmatrix}-2 \\ 0 \\ 3/2 \\ 0\end{bmatrix}+
c_{1}\begin{bmatrix}-2 \\ 1 \\ 0 \\ 0\end{bmatrix} + c_{2}\begin{bmatrix}2 \\ 0 \\ -2 \\ 1\end{bmatrix},
$$
where $c_1$ and $c_2$ are real numbers.
The nullspace of $A$ is a 2-D subspace of $\mathbb{R}^4$, and the solutions to the equation $Ax=b$ form a plane parallel to that through $x_{p}=\begin{bmatrix}-2 \\ 0 \\ 3/2 \\ 0\end{bmatrix}$.

# Rank

^61fcc2

The rank of a matrix equals the number of pivots of that matrix. If $A$ is an $m$ by $n$ matrix of rank $r$, we know $r \leq m$ and $r\leq n$.

## Full column rank

If $r=n$, then from the [[Pivot Variables, Special Solutions|previous lecture]] we know that nullspace has dimension $n-r=0$ and contains only the zero-vector. There are no free variables or special solutions.
If $Ax=b$ has a solution, it is unique; ==there is either 0 or 1 solution.== 
We know $r\leq m$, so if $r=n$ the number of columns of the matrix is less than or equal to the number of rows. The [[Pivot Variables, Special Solutions#^5cdbe8|reduced row echelon form]] of the matrix will look like $R=\begin{bmatrix}I \\ 0\end{bmatrix}$. For any vector $\pmb{b}$ in $\mathbb{R}^m$ that's not a linear combination of the columns of $A$, there is no solution to $Ax=b$.

## Full row rank
If $r=m$, then reduced matrix $R=\begin{bmatrix}I  & F\end{bmatrix}$ has no rows of zeros and so are no requirements for the entries of $\pmb{b}$ to satisfy. $Ax=b$ is solvable for every $\pmb{b}$. There are $n-r=n-m$ free variables, so there are $n-m$ special solutions to $A\pmb{x}=\pmb{0}$.

## Full row and column rank
If $r=m=n$ is the number of pivots of $A$, then $A$ is an invertible square matrix and $R$ is the identity matrix. The nullspace has dimension 0, and $Ax=b$ has a unique solution for every $\pmb{b}$ in $\mathbb{R}^m$. 

## Summary:

|                            | $r=m=n$ | $r=n<m$                            | $r=m<n$                           | $r<m,r<n$                                |
| -------------------------- | ------- | ---------------------------------- | --------------------------------- | ---------------------------------------- |
| $R$                        | $I$     | $\begin{bmatrix}I\\0\end{bmatrix}$ | $\begin{bmatrix}I&F\end{bmatrix}$ | $\begin{bmatrix}I&F \\ 0&0\end{bmatrix}$ |
| no. of solutions to $Ax=b$ | 1       | 0 or 1                             | $\infty$                          | $0$ or $\infty$                          |

![[2024-07-17-Note-18-05.pdf]]