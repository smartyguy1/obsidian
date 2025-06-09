
# Matrix Multiplication 
## Standard (row times column)

The standard way of describing an element $c_{ij}$ element of matrix $AB=C$
is: $\sum\limits_{k=1}^{n} \ a_{ik}b_{kj}$

### Columns
The product of matrix $A$ and column $j$ of matrix $B$ is column $j$ of $C$.
### Rows
The product of row $i$ of $A$ and matrix $B$ is row $i$ of $C$.

## Column times row

A column of $A$ is an $m \times1$ vector and a row of $B$ is a $1\times p$ vector. Their product matrix :
$$
\begin{bmatrix} \ 2 \ \\ 3 \\ 4 \end{bmatrix} \begin{bmatrix} \ 1 & 6\ \end{bmatrix} = \begin{bmatrix}\ 2 & 12\  \\ 3 & 18 \\ 4 & 24\end{bmatrix}
$$
- ==The columns of this matrix are multiples of the column of $A$==.
- ==The rows are multiples of the row of $B$.==
- ==If we think of these rows as coordinates $(2,12)$ or$(3,18)$ or $(4,24)$, all these points lie on the same line; similarly for the two column vectors.==
- This is equivalent of saying that the *row space* of this matrix is a single line, as is the *column space*.
==The product of $A$ and $B$ is the sum of these "column times row" matrices.==
$$
AB = \sum\limits_{k=1}^{n} \ \begin{bmatrix}a_{1k}\\ \vdots \\ a_{}\end{bmatrix}\begin{bmatrix}b_{k1} & \dots & b_{kn} \end{bmatrix}
$$
For example:
$$
\begin{align*}
\begin{bmatrix}\ 2 & 5 & 1 \  \\ 1 & 3 & 4 \\ 0 & 0 & 1\end{bmatrix}\begin{bmatrix}\ 1 & 2 \  \\ 3 & 4 \\ 5 & 6\end{bmatrix} &= \begin{bmatrix}\ 2\ \\ 1 \\ 0 \end{bmatrix}\begin{bmatrix}\ 1 & 2 \ \end{bmatrix} \ +
\begin{bmatrix}\ 5\ \\ 3 \\ 0\end{bmatrix}\begin{bmatrix}\ 3 & 4\ \end{bmatrix} \begin{bmatrix}\ 1\  \\ 4 \\ 1\end{bmatrix}\begin{bmatrix}\ 5&6\ \end{bmatrix}
\end{align*}
$$
Remember that normally we take row of the first matrix and column of the second but in this we focus on the ==column of the 1st matrix and row of the second==.

## Blocks
If we subdivide $A$ and $B$ into blocks that match properly, we can write the product $AB =C$ in terms of the products of the blocks.
$$
\begin{bmatrix} \ A_1 & A_2 \ \\ A_{3} & A_{4} \end{bmatrix}\begin{bmatrix} \ B_1 & B_{2}\ \\ B_3 & B_4\end{bmatrix} = \begin{bmatrix}\ C_{1} & C_{2} \ \\ C_{2} & C_{4}\end{bmatrix}
$$
Here $C_{1}=A_{1}B_{1} + A_{2}B_{3}$ 

A **Block matrix** or a **partitioned matrix** is a matrix that is interpreted as having been broken into sections called **blocks** or **submatrices**.

Intuitively, a matrix interpreted as a block matrix can be visualized as the original matrix with a collection of horizontal and vertical lines, which partition it.
$$
\left[\begin{array}{c|c}
a_{11} \ a_{22} \ a_{13} \ & b_{1}
\\ a_{21} \ a_{22} \ a_{23} \ & b_{2}
\\ \hline
 c_{1} \ \ c_{2} \ \ c_{3} \ \ & d \end{array}\right]
$$


# Inverses

^a397a0

## Square Matrices:
If $A$ is a square matrix, the most important characteristic of it s does it have an inverse $A^{-1}$. If it does, then $A^{-1}A = I = AA^{-1}$ and we say that $A$ is *invertible* or *singular*.

If $A$ is *Singular* - i.e. $A$ does not have an inverse - its determinant is zero and we can find some non-zero vector $\pmb{x}$ for which $A\pmb{x} = 0$. 
For example:
$$
\begin{bmatrix} \ 1 & 3\ \\ 2 & 6\end{bmatrix}\begin{bmatrix}\ 3\ \\ -1\end{bmatrix} = \begin{bmatrix}\ 0\ \\ 0 \end{bmatrix}
$$
Finding the inverse of a matrix is closely related to solving systems of linear equations:
$$
\begin{align*}
\begin{bmatrix}\ 1 & 3\ \\
2 & 7\end{bmatrix}  \ & \  \begin{bmatrix} \ a & c\ \\
b&d\end{bmatrix} =&\begin{bmatrix}\ 1 & 0\ \\
0 & 1\end{bmatrix}\\
A \ \ \ \  \ & \ \ \ \ A^{-1}
& I

\end{align*}
$$
This is just a special form of the equation $A\pmb{x} =\pmb{b}$.
# Gauss-Jordan Elimination

We can use the method of elimination to solve two or more linear equations at the same time. ==Just augment the matrix with the whole identity matrix $I$:==
$$
\left[ \begin{matrix} \ 1 & 3 \ \\ 2 & 7 \end{matrix}\right| \left.\begin{matrix} \ 1 & 0\ \\ 0 & 1\end{matrix} \right] \longrightarrow

\left[ \begin{matrix} \ 1 & 3 \ \\ 0 & 1 \end{matrix}\right| \left.\begin{matrix} \ 1 & 0\ \\ -2 & 1\end{matrix} \right] \longrightarrow 

\left[ \begin{matrix} \ 1 & 0 \ \\ 0 & 1 \end{matrix}\right| \left.\begin{matrix} \ 7 & -3\ \\ -2 & 1\end{matrix} \right]
$$
(Once we have used Gauss' elimination method to convert the original matrix to upper triangular form, we go on to use Jordan's idea of eliminating entries in the upper right portion of the matrix.)

$$
A^{-1} = \begin{bmatrix}\ 7  & -3\  \\ -2 & 1\end{bmatrix}
$$
We can write the results of the elimination method as product of a number of elimination matrices $E_{ij}$ with matrix $A$. Letting $E$ be the product of all $E_{ij}$, we write the result of this Gauss-Jordan elimination using block matrices: $E[A|I] = [I|E]$. But if $EA = I$, then $E = A^{-1}$.