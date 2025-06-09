# Four subspaces
Any *m* by *n* matrix *A* determines four subspaces(possibly containing only zero vector):
## Column space, $C(A)$
$C(A)$ consists of all combinations of the columns of *A* and is a vector space in $\mathbb{R}^m$.

## Nullspace, $N(A)$
This consists of all solutions $\pmb{x}$ of the equation $A\pmb{x}=0$ and lies in $\mathbb{R}^n$.

## Row space, $C(A^T)$ 
The combinations of the row vectors of *A* form a subspace of $\mathbb{R}^n$. 
We equate this with $C(A^T)$.

## Left  nullspace, $N(A^T)$ 
We call the nullspace of $A^T$ the *left nullspace* of A.
This is a subspace of $\mathbb{R}^m$.

# Basis and dimension
## Column space
The *r* pivot columns form a basis for $C(A)$
$$
\text{dim} \ C(A) = r
$$
## Nullspace
The special solutions to $A\pmb{X}=0$ correspond to free variables and form a basis for $N(A)$. An $m\times n$ matrix has $n-r$ free vaiables:
$$
\text{dim} \ N(A) = n-r
$$
## Row space
We could perform row reduction on $A^T$, but instead we make use of $R$, the *row reduced echelon form* of *A*.
$$
A=\begin{bmatrix}1 & 2 & 3 & 1 \\ 1 & 1 & 2 & 1 \\ 1 & 2 & 3 & 1\end{bmatrix} \rightarrow \dots \rightarrow \begin{bmatrix}1 & 0 & 1 & 1 \\ 0 & 1 & 1 & 0 \\ 0 & 0 & 0 & 0\end{bmatrix} = \begin{bmatrix}I & F \\ 0 & 0\end{bmatrix} = R
$$
==Although the column spaces of A and R are different==, the row space of *R* is the same as the row space of *A*. The rows of *R* are combinations of the rows of *A*,
and because reduction is reversible the the rows of *A* are combinations of the rows of *R*.
The first *r* rows of *R* are the "echelon" basis for the row space of *A*:
$$
\text{dim} \ C(A^T)=r
$$
## Left Nullspace
The matrix $A^T$ has *m* columns. We just saw that *r* is the rank of $A^T$, so the number of free columns of $A^T$ must be $m-r$:
$$
\text{dim} \ N(A^{T})= m-r
$$
==The left nullspace is the collection of vectors *y* for which $A^{T}y=0$. Equivalently, $y^{T}A=0$; ==here *y* and 0 are row vectors. *We say "left nullspace" because $y^T$ is on the left of A in this equation.* 
To find a basis for the left nullspace we reduce an augmented version of *A*:
$$
\left[A_{m \times n} \ \ \ I_{m \times n}\right]\rightarrow \left[R_{m\times n} \ \ \ E_{m \times n}\right]
$$
For this we get them matrix *E* for which $EA=R$.(If *A* is a square, invertible matrix then $E=A^{-1}$). In our example,
$$
EA=\begin{bmatrix}-1 & 2 & 0 \\ 1 & -1 & 0 \\ -1 & 0 & 1\end{bmatrix}\begin{bmatrix}1 & 2 & 3 & 1 \\ 1 & 1 & 2 & 1 \\ 1 & 2 & 3 & 1\end{bmatrix} = \begin{bmatrix}1 & 0 & 1 & 1 \\ 0 & 1 & 1 & 0 \\ 0 & 0 & 0 & 0\end{bmatrix} = R
$$
The bottom $m-r$ rows of $E$ describe linear dependencies of rows of *A*, because the bottom $m-r$ rows of *R* are zero. Here $m-r=1$(one zero row in R).
The bottom $m-r$ rows of *E* satisfy the equation $\pmb{y}^{T}A=0$ and form a basis for the left nullspace of *A*.

## New vector space

^66a4a3

The collection of all $3\times 3$ matrices forms a vector space; call it $M$. We can add matrices and multiply them by scalars and there's a zero matrix (additive identity). ==If we ignore the fact that we can multiply matrices by each other, they behave just like vectors.==
Some subspaces of $M$ include:
- all upper triangular matrices
- all symmetric matrices
- D, all diagonal matrices

*D* is the intersection of the first two spaces. Its dimension is 3; one basis for *D* is:
$$
\begin{bmatrix}1 & 0 & 0 \\ 0 & 0 & 0 \\ 0 & 0 & 0\end{bmatrix}, \ \begin{bmatrix}1 & 0 & 0 \\ 0 & 3 & 0 \\ 0 & 0 & 0\end{bmatrix}, \ \begin{bmatrix}0 & 0 & 0 \\ 0 & 0 & 0 \\ 0 & 0 & 7\end{bmatrix}
$$

