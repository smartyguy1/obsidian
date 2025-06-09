# Linear Independence

^4eaadc

Suppose $A$ an $m\times n$ matrix with $m<n$ (so $Ax=b$ has more unknowns than equations.) $A$ has at **least one** free variable, so there are [[Column Space and Nullspace|non-zero solutions]] to $Ax=0$. A combination of the columns is zero, so the columns of this $A$ are *dependent*.

==We say vectors $x_{1}$, $x_{2}$, ...$x_{n}$ are linearly independent (or just independent) if $c_{1}x_{1}+c_{2}x_{2}+\dots c_{n}x_{n}=0$ **only when** $c_{1}$, $c_{2}$, ...$c_{n}$ are all $0$. When those vectors are the columns of $A$, the only solution to $Ax=0$ is $\pmb{x}=0$. i.e. **$N(A)$ only contains the zero vector**.==
*Two vectors are independent if they do not lie in the same line. Three are independent if they do not lie in the same plane and so on...*.

If the columns of $A$ are independent then,
- All columns are pivot columns 
- the rank of $A$ is $n$
- there are no free variables. 
If the columns of $A$ are dependent then the rank of $A$ is **less than** $n$ and there are no free variables.

# Spanning s space

^8fe573

Vectors $\pmb{v}_{1}$, $\pmb{v}_2$...$\pmb{v}_3$ span a space when the space consists of all combinations of those vectors. For example, the column vectors of $A$ span the column space of $A$.
If vectors $\pmb{v}_{1}$, $\pmb{v}_2$...$\pmb{v}_3$ span a space $S$, then $S$ is the smallest space containing those vectors.

# Basis and Dimension
 A *basis* for a vector space is a sequence of vectors $\pmb{v}_1$, $\pmb{v}_{2}$...$\pmb{v}_n$ with two properties:
 - They are [[#^4eaadc|independent]] 
 - They span **the** [[#^8fe573|vector space]].
The basis of a space tells us everything we need to know about that space.

**Example**: $\mathbb{R}^3$ 
One basis for $\mathbb{R}^3$ is $\left \{ \begin{bmatrix}1 \\ 0 \\ 0\end{bmatrix}, \begin{bmatrix}0 \\ 1 \\ 0\end{bmatrix}, \begin{bmatrix}0 \\ 0 \\ 1\end{bmatrix}\right \}$. These are independent because:
$$
c_{1}\begin{bmatrix}1 \\ 0 \\ 0\end{bmatrix}+c_2\begin{bmatrix}0 \\ 1 \\ 0\end{bmatrix} +c_{3}\begin{bmatrix}0 \\ 0 \\ 1\end{bmatrix} = \begin{bmatrix}0 \\ 0 \\ 0\end{bmatrix}
$$
is only possible when $c_1=c_2=c_3=0$. These vectors span $\mathbb{R}^3$.
As discussed in the pdf, the vectors $\begin{bmatrix}1 \\ 1 \\ 2\end{bmatrix}$, $\begin{bmatrix}2 \\ 2 \\ 5\end{bmatrix}$ and $\begin{bmatrix}3 \\ 3 \\ 8\end{bmatrix}$ do **not** form a basis for $\mathbb{R}^3$ because these are the column vectors of a matrix that has two identical rows. The three vectors though, are not linearly independent. 
==In general, *n* vectors in $\mathbb{R}^n$ form a basis if they are the column vectors of an invertible matrix.==

## Basis for a subspace
The vectors $\begin{bmatrix}1 \\ 1 \\ 2\end{bmatrix}$ and  $\begin{bmatrix}2 \\ 2 \\ 5\end{bmatrix}$ span a plan in $\mathbb{R}^3$ but they cannot form a basis for $\mathbb{R}^3$. G==iven a space, every basis for that space has the same number of vectors *n*; that is the dimension of space==. SO there are exactly *n* vectors in every basis of $\mathbb{R}^n$.

## Basis of a column space and nullspace
Suppose:
$$
A = \begin{bmatrix}1 & 2 & 3 & 1 \\ 1 & 1 & 2 & 1 \\ 1 & 2 & 3 & 1\end{bmatrix}
$$
By definition, the 4 column vectors of $A$ span the [[Column Space and Nullspace|column space]] of $A$. The 3rd and 4th column vectors are dependent on the 1st and 2nd, and the first two are independent. Therefore, the first column vectors are the pivot columns. They form a basis for the column space $C(A)$. The matrix has rank 2. In fact, for any matrix we can say:
>rank($A$) = no. of pivot columns of $A$ = dimension of $C(A)$ 

==(Note: matrices have a rank but not a dimension. Subspaces have a dimension but not a rank.)==

The column vectors of this $A$ are not independent, so the nullspace $N(A)$ contains more than just the zero vector. Because $C_3=C_1+C_2$ we know that $\begin{bmatrix}-1 \\ -1 \\ 1 \\ 0\end{bmatrix}$ is in the nullspace. Similary, $\begin{bmatrix}-1 \\ 0 \\ 0 \\ -1\end{bmatrix}$ is also in $N(A)$. These are the to special solutions to $A\pmb{x}=\pmb{0}$.
> dimension of $N(A)$ = number of free variables = $n-r$,

so we know that dimension of $N(A)$ is $4-2=2$. These two special solutions for a basis for the nullspace.

![[Independence, Basis and Dimension.pdf]]