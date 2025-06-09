**Inverse of a product** : $(AB)^{-1} = B^{-1}A^{-1}$ .
**Transpose of a product** : $(AB)^{T}= B^{T}A^T$ 
*For any invertible matrix A: $(A^{-1})^{T}= (A^T)^{-1}$ 

We've seen how to use elimination to convert a suitable matrix A into an upper triangular matrix $U$.
This leads us to the ==factorization: $A=LU$==, which is very helpful in understanding $A$.
[[Elimination With matrices|Recall]] that the elimination of the entries of $A$ can be described by multiplication by succession of matrices $E_{ij}$. So that $A\longrightarrow E_{21}A \longrightarrow E_{31}E_{21}A\longrightarrow \dots \longrightarrow U$ .In 2x2 case it looks like this:
$$
\begin{align}E_{21}\ \ \  & \ \ \ \ \ A  &  U\ \ \ \  \\
\begin{bmatrix}1 & 0\\
-4 & 1\end{bmatrix}
&\begin{bmatrix}2 & 1 \\ 8 & 7\end{bmatrix}= &\begin{bmatrix}2 & 1 \\ 0 & 3\end{bmatrix}
\end{align}
$$
We can convert this to $A=LU$ by multiplying $E_{21}^{-1}$ on both the sides:
$$
\begin{align*}
A\ \ \ \  & \  \  \ \ \ \ \ \ \  L & U \ \ \ \ \\
\begin{bmatrix}2 & 1\\
8 & 7\end{bmatrix}&=\begin{bmatrix}1 & 0\\
4 & 1\end{bmatrix}&\begin{bmatrix}2 & 1\\
0 & 3\end{bmatrix}
\end{align*}
$$
==The matrix L is a *Lower Triangular matrix*== and has ones on the diagonal.
Sometimes we will also want to factor out a diagonal matrix whose entries are the pivots:
$$
\begin{align*}
A \ \ \ &\ \ \ \ \ \ \ \ \ L & D \ \ \ & \ \ \ \ \ U'\\
\begin{bmatrix}2 & 1\\
8 & 7\end{bmatrix} &= \begin{bmatrix}1 & 0\\
4 & 1\end{bmatrix}&\begin{bmatrix}2 & 0\\
0 & 3\end{bmatrix}&\begin{bmatrix}1 & \frac{1}{2}\\
0 & 1\end{bmatrix} 
\end{align*}
$$
In the 3x3 case, if $E_{21}E_{31}E_{21}A = U$ then $A = E_{21}^{-1}E_{31}^{-1}E_{32}^{-1}U = LU$ 
For example, suppose $E_{31}$ is the identity matrix:
$$
\begin{align*}
E_{32} \ \ \ \ \ & \ \ \ \ \ \ \ \ \ E_{21} & E \ \ \ \ \ \ \ \ \ \\
\begin{bmatrix}1 & 0 & 0\\
0 & 1 & 0\\
0 & -5 & 1\end{bmatrix}&\begin{bmatrix}1 & 0 & 0\\
-2 & 1 & 0\\
0 & 0 & 1\end{bmatrix} &= \begin{bmatrix}1 & 0 & 0\\
-2 & 1 & 0\\
10 & -5 & 1\end{bmatrix}
\end{align*}
$$
The 10 at $e_{31}$ arises because we subtracted twice the 1st row from the 2nd row, then subtracted 5 times the new 2nd row from the third.

==The factorization $A =LU$ is preferable than $EA=U$ because the combination of row subtractions does not have the effect on $L$ that it did on $E$.==
Here the multipliers don't interfere with each other, so it is preferred more.
So, we can say:
==In $A=LU$ if no exchanges, the multipliers go directly into $L$.==
Note that singular matrices can also have $A=LU$ compositions.

# How expensive is elimination?

Some computer applications require inverting very large matrices. How hard will the computer word?
When using elimination to find factorization $A=LU$ we just saw that we can build $L$ as we go by keeping track of tor subtractions. We only have to remember $L$ and (the matrix that will become)$U$; we don't have to store $A$ or $E_{ij}$ in the computer's memory.
It requires a total of $n^2$ operations (including multiplying and subtracting) to eliminate entries in the first column and $(n-1)^{2}$ for the second and so on.
So the total number of operations needed to factor $A$ into $LU$ is on the order of $n^3$ :
$$
1^{2}+2^{2}+\dots+(n-1)^{2}+n^{2}=\sum\limits_{i=1}^{n}i^{2}\approx \ \int_{0}^{n}x^{2}\ dx = \frac{1}{3}n^{3}
$$
Or we can say factoring using elimination in $O(n^3)$ \[[[Running time|Explanation]]]

# Row exchanges

What if there are row exchanges, i.e. if there's a zero in a pivot position?

To swap two rows, we multiply on the left by a *permutation matrix*. For eg:
$$
P_{12} = \begin{bmatrix}0 & 1 & 0 \\ 1 & 0 & 0 \\ 0 & 0 & 1\end{bmatrix}
$$
$P_{12}$ swaps the 1st and the 2nd rows of a 3x3 matrix(it swaps columns if it is multiplied on the right of the matrix).
==The inverse of any permutation matrix $P$ is $P^{-1} = P^T$ ==
There are $n!$ different ways to permute the rows of a $n\times n$ matrix(including the permutation that leaves all rows fixed).
==So there are $n!$ permutation matrices and these form a *multiplicative group*.==


