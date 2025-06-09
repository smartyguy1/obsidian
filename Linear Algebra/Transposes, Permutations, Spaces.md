# Permutations

Multiplication by a permutations matrix $P$ swaps the rows of a matrix; when applying the method of elimination we use permutation matrices to **remove zeros out of pivot positions**. ==Our factorization $A=LU$ then becomes $PA=LU$==,
where $P$ is a permutation matrix.

Recall that $P^{-1} = P^T$ ,i.e. $P^{T}P = I$.

# Transposes
- Column become rows and rows become columns
- $(A_{ij})^{T} =A_{ji}$ 
- Eg:
$$
\begin{bmatrix}1 & 3 \\ 2 & 3 \\ 4 & 1\end{bmatrix}^{T}= \begin{bmatrix}1 & 2 & 4 \\ 3 & 3 & 1\end{bmatrix} 
$$

A matrix is is symmetric if $A^{T}=A$. ==Given any matrix R(not necessarily square) the product$RR^{T}$ is always symmetric==, because $(R^{T}R)^{T}=R^{T}(R^{T})^{T}= R^{T}R$ 

# Vector Spaces

We can add vectors and multiply them by numbers, which means we can discuss *linear combinations* of vectors. These combinations follow the rules of a *vector space.*

Eg: $\mathbb{R}^2$ is a vector space, it is the set of all vectors with exactly two real number components. The vector $\begin{bmatrix}a \\ b\end{bmatrix}$  is the same as $a\hat{i}+b\hat{j}$.
Another eg: $\mathbb{R}^n$ , the set of (column) vectors with $n$ real number components.

## Closure
The collection of vectors with exactly two **positive** real valued components is **not** a vector space.

The sum of any two vectors in that collection is in the collection. However, multiplying any vector by, say $-5$, gives a vector that's not in the collection.

We say that this collection of positive vectors is *closed* under addition but not under multiplication.
==If a collection of vectors is closed under linear combinations(i.e. under addition and multiplication by any real number), and if multiplication and addition behave in a *reasonable way*, then we call that collection a vector space.==

## Subspaces

==A vector space contained inside another vector space.==
For eg: $\pmb{v}$ is any non-zero vector in $\mathbb{R}^2$. Then the set of all $c\pmb{v}$, where $c$ is a real number, forms a subspace of $\mathbb{R}^2$ (a line through O) and is closed under addition.
==A line in $\mathbb{R}^2$ that does not pass through the origin is **not** a subspace of $\mathbb{R}^2$==.
Multiplying any vector on that line by 0 gives the zero vector which does not lie on the line.
==Every subspace must contain the zero vector because vector spaces are closed under multiplication.==

The subspaces of $\mathbb{R}^2$ are:
1. all of $\mathbb{R}^{2}$
2. any line through $\begin{bmatrix}0 \\ 0\end{bmatrix}$
3. the zero vector alone (Z)
The subspaces of $\mathbb{R}^3$ are:
1. all of $\mathbb{R}^3$
2. any plane through the origin
3. any line through origin
4. the zero vector alone (Z)
## Column Space

Given a matrix $A$ with columns in $\mathbb{R}^3$, these columns and all their linear combinations form a subspace of $\mathbb{R}^3$. This is the *column space* $C(A)$. If $A = \begin{bmatrix}1 & 3 \\ 2 & 3 \\ 4 & 1\end{bmatrix}$.
the column space of $A$ is the plane through the origin $\mathbb{R}^3$ containing $\begin{bmatrix}1  \\ 2 \\ 4\end{bmatrix}$ and $\begin{bmatrix}3 \\ 3 \\ 1\end{bmatrix}$.