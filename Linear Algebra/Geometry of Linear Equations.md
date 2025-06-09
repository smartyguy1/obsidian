The fundamental problem of linear algebra is to solve n equations in n variables.
For ex: 
We have 2 equations
$$\begin{align}
 2x  -y = 0 \\
-x + 2y = 3
\end{align}
$$
This system is two-dimensional ($n = 2$) 

# Row Picture

On plotting the points that satisfy each equation, the intersection of the plots(if they do intersect) represents the solution to the equations.

![[Pasted image 20240707190629.png]]
The given lines intersect at the point $(1,2)$. 

# Column Picture
In the picture we rewrite the system of linear equations as a single equation by turning coefficients in the column of the system into vectors:
$$
 x\begin{bmatrix} \space2 \\ -1 \end{bmatrix}
 + y\begin{bmatrix}-1 \\ \space2 \end{bmatrix}
 = \begin{bmatrix}\space0 \\ \space3 \end{bmatrix}
$$
Given two vectors c and d and scalars $x$ and $y$, the sum $x\pmb{c}+y\pmb{d}$ is called a ==Linear Combination.==
We want to find numbers x and y so that the linear combination gives the vector $\begin{bmatrix}0\\3\end{bmatrix}$ which we will call $b$.

# Matrix Plane
We write the system of equations:
$$
\begin{align}
2x-y=0\\-x+2y=3
\end{align}
$$
as a single equation by using matrices and vectors:
$$
\begin{bmatrix} 2 & -1 \\ -1 & 2\end{bmatrix}
\begin{bmatrix} x\\y \end{bmatrix}
=
\begin{bmatrix}0\\3\end{bmatrix}
$$
The matrix $A = \begin{bmatrix}2 & -1 \\ -1 & 2\end{bmatrix}$ is called the **coefficient matrix**. The vector $x = \left[\begin{matrix}x\\y \end{matrix}\right]$ is the vector of unknowns. The values on the RHS form the vector $\pmb{b}$ 
$$
A\pmb{x} = \pmb{b}
$$
## Matrix Multiplication

Another way of multiplying matrices is to think of the entries of $x$ as the coefficients of a linear combination of column vectors of the matrix. [[Multiplication and Inverse Matrices|More]]

$$
\begin{bmatrix}2 &5 \\1 &3\end{bmatrix}\begin{bmatrix}1\\2\end{bmatrix}= 1\begin{bmatrix}2\\1\end{bmatrix}+2\begin{bmatrix}5\\3\end{bmatrix} = \begin{bmatrix}12\\7\end{bmatrix}
$$
# Linear Independence
In the column and matrix pictures, $$A\pmb{x}=\pmb{b}$$
If this equation has a solution for every value of $\pmb{b}$ , then the linear combination of the vectors can fill the $xy$-plane (or space in 3-Dimensional case). Then the the column vectors are *linearly independent*.

If it doesn't then we say that $A$ is a *singular matrix*. In this singular case its column vectors are *linearly dependent*. All linear combinations of those vectors lie on a point or a line(in 2-D case) or on a point,line or plane(in 3-D case). The combinations don't fill the whole *vector space*.