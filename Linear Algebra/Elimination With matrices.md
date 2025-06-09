# Method Of Elimination
*Elimination* is the technique most commonly used by computer software to solve systems of linear equations. It finds a solution $\pmb{x}$ to $A\pmb{x}=\pmb{b}$ whenever the matrix A is invertible. 
$$
A = \begin{bmatrix}1&2&1\\3 &8&1 \\0&4&1 \end{bmatrix} \space and \space \pmb{b} = \begin{bmatrix}2 \\ 12 \\ 2\end{bmatrix} 
$$
**First We'll try to create an upper triangular matrix through row transformations and make sure that no zeros are created at the pivots (or the diagonal elements) in that case we'll exchange the rows to not have a zero in the pivot position.**
==If there is a zero in the pivot position and no non-zero value below it, then the matrix $A$ is not invertible. Then Elimination cannot be used to find a unique solution to the system of equations-it doesn't exist.==
$$
\begin{bmatrix}1&2&1 \\ 3&8&1 \\ 0&4&1\end{bmatrix}\to \begin{bmatrix}1&2&1 \\ 0&2&-2 \\ 0&4&1\end{bmatrix}\to\begin{bmatrix}1&2&1 \\ 0&2&-2 \\ 0&0&5\end{bmatrix} = \large{U}
$$



So we got from $A$ to $U$. We repeat the same transformations with the vector $b$ and get $c = \begin{bmatrix}2 \\ 6 \\ -10\end{bmatrix}$.
Now the Equation $U\pmb{x}= c$ is easy to solve with *back substitution*.
$$
\begin{bmatrix}1&2&1\\0&2&-2 \\0&0&5 \end{bmatrix}\begin{bmatrix}x \\ y \\ z \end{bmatrix} = \begin{bmatrix}2 \\ 6 \\ -10\end{bmatrix}
$$
We get $z= -2, y=1,x=2$. This is also a solution to the original equation $A\pmb{x} = \pmb{b}$.

The determinant of $U$ is the product of the pivots.

# Elimination Matrices

The product of a matrix(3x3) and a column vector (3x1) is a column vector(3x1) that is a linear combination of the columns of the matrix.

The product of a row (1x3) and a matrix (3x3) is a row (1x3) that is a linear combination of the rows of the matrix.

We can subtract 3 times row 1 of matrix $A$ from row 2 of $A$ by calculating the matrix product:
$$
\begin{bmatrix}1&0&0 \\ -3&1&0 \\ 0&0&1\end{bmatrix}\begin{bmatrix}1&2&1 \\ 3&8&1 \\ 0&4&1\end{bmatrix} = \begin{bmatrix}1&2&1 \\ 0&2&-2 \\ 0&4&1\end{bmatrix}
$$
The matrix that we pre-multiplied $A$ by is known as *Elimination Matrix*.

The elimination matrix used to eliminate the $a_{mn}$ entry is denoted by $E_{mn}$.
The above calculation takes us to $E_{21}A$.

Then the three elimination steps leading to $U$ were: $E_{32}(E_{31}(E_{21}A)) = U$, where $E_{31} = I$ (since the entry at that position is already $0$.)

Thus, $E_{32}(E_{21}A) =U$. Matrix multiplication is *Associative*, so we can also write $(E_{32}E_{21})A=U$. 

The product $E_{32}E_{21}$ tells us how to get from $A$ to $U$. The inverse of the matrix $E_{32}E_{21}$ tells us how to get from $U$ to $A$. We can represent this product by $E$.

If we solve $U\pmb{x} = EA\pmb{x} = E\pmb{b}$, then it is also true that $A\pmb{x} = \pmb{b}$. This is why the method of elimination works: all steps can be reversed.

A *Permutation matrix* exchanges two rows of a matrix; for example,
$$
p = \begin{bmatrix}0&1&0 \\ 1&0&0 \\ 0&0&1\end{bmatrix}
$$
This matrix represents $R_{2}\leftrightarrow R_{1}$.
The matrix $PA$ has its 2nd and 1st rows exchanged.

The matrix $P$ is constructed by exchanging the rows of the Identity matrix.

==To exchange the columns of the matrix, multiply on the right(as in $AP$) by a permutation matrix.==
(==matrix multiplication is not commutative).==

# Inverses

^c22642

In the first step in solving $Ax=b$ . We can undo the row transformation (pre-multiplication by $E_{21}$) by pre-multiplying with $E^{-1}_{21}$. Here $E_{21}^{-1}$ is an [[Multiplication and Inverse Matrices#^a397a0|inverse]] of $E_{21}$

$$\begin{align}
E_{21} = \begin{bmatrix}1&0&0 \\ -3&1& 0\\0& 0&1\end{bmatrix}
\\
\\E^{-1}_{21} = \begin{bmatrix}1&0&0 \\ 3&1& 0\\0& 0&1 \end{bmatrix}
\end{align}
$$


