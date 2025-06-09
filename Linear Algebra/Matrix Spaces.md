# New vector spaces
## 3 by 3 matrices
[[The Four Fundamental Subspaces#^66a4a3|Earlier]], we were looking at the space $M$ of all $3\times3$ matrices. We identified some subspaces,
- Symmetric $3\times3$ matrices $S$
- The upper triangular $3\times3$ matrices $\large{u}$
- The intersection $D$ of these two spaces - the space of diagonal $3\times3$ matrices.

The dimension of $M$ is 9; we must choose 9 numbers to specify an element of $M$. The space $M$ is very similar to $\mathbb{R}^9$. A good choice of basis is:
$$
\begin{bmatrix}1 & 0 & 0 \\ 0 & 0 & 0 \\ 0 & 0 & 0\end{bmatrix}, \ \begin{bmatrix}0 & 1 & 0 \\ 0 & 0 & 0 \\ 0 & 0 & 0\end{bmatrix}, \ \begin{bmatrix}0 & 0 & 1 \\ 0 & 0 & 0 \\ 0 & 0 & 0\end{bmatrix}, \ \dots \ \begin{bmatrix}0 & 0 & 0 \\ 0 & 0 & 0 \\ 0 & 0 & 1\end{bmatrix}
$$
The subspace of symmetric matrices $S$ has dimensions 6. When choosing an element of $S$ We pick 3 numbers on the diagonal and 3 in the upper right which tells us what must appear in the lower half. One set of basis for $S$ is:
$$
\left\{ \begin{bmatrix}1 & 0 & 0 \\ 0 & 0 & 0 \\ 0 & 0 & 0\end{bmatrix}, \begin{bmatrix}0 & 1 & 0 \\ 1 & 0 & 0 \\ 0 & 0 & 0\end{bmatrix}, \begin{bmatrix}0 & 0 & 1 \\ 0 & 0 & 0 \\ 1 & 0 & 0\end{bmatrix},\begin{bmatrix}0 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 0\end{bmatrix}, \begin{bmatrix}0 & 0 & 0 \\ 0 & 0 & 1 \\ 0 & 1 & 0\end{bmatrix}, \begin{bmatrix}0 & 0 & 0 \\ 0 & 0 & 0 \\ 0 & 0 & 1\end{bmatrix}\right\}
$$
The dimension of $\LARGE{\text{u}}$ is again 6; we have the same amount of freedom in selecting the entries of upper triangular matrix as we did in choosing symmetric matrix. A basis for $\Huge{\text{u}}$ is:
$$
\left\{\begin{array}{c,c}
\begin{bmatrix}1 & 0 & 0 \\ 0 & 0 & 0 \\ 0 & 0 & 0\end{bmatrix}, \begin{bmatrix}0 & 1 & 0 \\ 0 & 0 & 0 \\ 0 & 0 & 0\end{bmatrix},
\begin{bmatrix}0 & 0 & 1 \\ 0 & 0 & 0 \\ 0 & 0 & 0\end{bmatrix},
\begin{bmatrix}0 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 0\end{bmatrix},
\begin{bmatrix}0 & 0 & 0 \\ 0 & 0 & 1 \\ 0 & 0 & 0\end{bmatrix},
\begin{bmatrix}0 & 0 & 0 \\ 0 & 0 & 0 \\ 0 & 0 & 1\end{bmatrix}
\end{array}\right\}
$$
This happens to be the subset of the basis we chose for $M$, but there is no basis for $S$ that is a subset of the basis we chose for $M$.
The subspace $D = S\cap \Large{\text{u}}$ has dimension 3. Because of the way we chose bases for $\Large{\text{u}}$ and $S$, a good basis for $D$ is the intersection of those bases.

Is $S\cup \Large{\text{u}}$ $\subset M$ ? No, *this is like taking 2 lines in $\mathbb{R}^2$ and asking if together they form a subspace*; we have to fill in between them. 
If we take all possible sums of elements of $S$ and elements of $\Large{\text{u}}$ we get the *sum* $S+\Large\text{u}$. This **is** a subspace of $M$. In fact, $S+\Large\text{u}=\normalsize M$. For unions and sums follow this rule:
$$
\text{dim }S + \text{dim }\Large\text{u}\normalsize = \text{dim }S  \cup \Large\text{u}\normalsize \ + \text{dim } S  \cap \Large\text{u}
$$
## Differential Equations

Another example of a vector space that's not $\mathbb{R}^n$ appears in differential equations.
We can think of the solutions $y$ to $\frac{d^{2}y}{dx^{2}}+y=0$ as the elements of a nullspace.
Some solutions are:
$$
\begin{align*}
y=\cos{x}, && y=\sin{x}, && y=e^{ix}
\end{align*}
$$
The complete solution is:
$$
y=c_{1}\cos{x}+c_{2}\sin{x},
$$
where $c_{1}$ and $c_{2}$ can be any complex numbers. This solution is a 2-D vector space with basis vectors $\cos{x}$ and $\sin{x}$. 
*Even though they don't "look like" vectors, we can build a vector space from them because they can be added and multiplied by a constant*

## Rank 4 matrices

Now let $M$ be the space of $5\times17$ matrices. The subset of $M$ containing all rank 4 matrices is not a subspace, even if we include the zero matrix, because the sum of two rank 4 matrices may not have rank 4.

In $\mathbb{R}^4$, the set of all vectors $\pmb{v}=\begin{bmatrix}v_{1} \\ v_{2} \\ v_{3} \\ v_{4}\end{bmatrix}$ for which $v_{1}+v_{2}+v_{3}+v_{4}=0$ is a subspace.
It contains the zero vector and is closed under addition and scalar multiplication. It is the nullspace of the matrix $A=\begin{bmatrix}1 & 1 & 1 & 1\end{bmatrix}$. Because $A$ has rank 1, the dimension of this nullspace is $n-r=3$. The subspace has basis of special solutions:
$$
\begin{bmatrix}-1 \\ 1 \\ 0 \\ 0\end{bmatrix}, \begin{bmatrix}-1 \\ 0 \\ 1 \\ 0\end{bmatrix}, \begin{bmatrix}-1 \\ 0 \\ 0 \\ 1\end{bmatrix}
$$
The column space of $A$ is $\mathbb{R}^{1}$. The left nullspace contains only the zero vector, has dimension 0 and its basis is the empty set. The row space of $A$ also has dimension 1.

## Rank 1 matrices

The rank of a matrix is the dimension of its column (or row) space. The matrix
$$
A = \begin{bmatrix}1 & 4 & 5 \\ 2 & 8 & 10\end{bmatrix}
$$
has rank 1 because each of its columns is a multiple of the first colum.
$$
A=\begin{bmatrix}1 \\ 2\end{bmatrix}\begin{bmatrix}1 & 4 & 5\end{bmatrix}
$$
==Every rank 1 matrix $A$ can be written as $A=\pmb{UV}^{T}$, where $\pmb{U}$ and $\pmb{V}$ are column vectors. We'll use rank 1 matrices as building blocks for more complex matrices.==
## Small world graphs
In this class, a *graph* $G$ is a collection of nodes joined by edges:
$$
G = \{\text{nodes, edges}\}
$$
A typical graph appears like :
![[Pasted image 20240808181547.png]]

![[Matrix Spaces;Rank1;Small World Graphs.pdf]]