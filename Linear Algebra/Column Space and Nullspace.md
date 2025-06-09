# Review of subspaces

A plane $P$ containing $\begin{bmatrix}0 \\ 0 \\ 0\end{bmatrix}$ and a line $L$ containing $\begin{bmatrix}0 \\ 0 \\ 0 \\ \end{bmatrix}$ are both sub-spaces of $\mathbb{R}^3$. The union of $P\cup L$ of those two [[Transposes, Permutations, Spaces|subspaces]] is generally not a subspace, because the sub of a vector of $P$ and a vector of $L$ is probably not contained in $P\cup L$. 
The intersection $S\cap T$ is a subspaces. As both are closed under linear combination the space made by vectors common to them will be so too.

# Column Space of A

^4bb7f7

==The column space of a matrix $A$ is the vector space made up of all linear combinations of the columns of $A$.==
## Solving $Ax = b$
$$
\text{Let} \ A = \begin{bmatrix}1 & 1 & 2 \\ 2 & 1 & 3 \\ 3 & 1 & 4 \\ 4 & 1  & 5\end{bmatrix}
$$
For what vectors $\pmb{b}$ does $Ax=b$ have a solution $\pmb{x}$?
Here, $Ax=b$ does not have a solution for every choice of $b$ because solving $Ax=b$ is equivalent to solving 4 linear equations with 3 unknowns.

If there is a solution of $Ax=b$ then $b$ must be a linear combination of the columns of $A$. Only 3 columns cannot fill the entire $\mathbb{R}^4$ , some vectors $b$ cannot be expressed as the linear combinations of  columns of $A$.

Big question: What $\pmb{b}$'s allow $Ax=b$ to be solved?
A useful approach is to find the vector $\pmb{b} = A\pmb{x}$ corresponding to that solution.

==The system of linear equations $A\pmb{x}=\pmb{b}$ is *solvable* exactly when $\pmb{b}$ is a vector in 
the *column space* of $A$.==

We can see that the columns of $A$ are not *independent* as $C_{3} = C_{1}+C_{2}$ 
So, the column space of $A$ is a **2-D** subspace of $\mathbb{R}^4$. 

# Nullspace of $A$

==The *nullspace* of a matrix $A$ is the collection of all solutions $\pmb{x} = \begin{bmatrix}x_1 \\ x_2 \\ x_3\end{bmatrix}$ to the equation $A\pmb{x}=0$.==
The column space of the matrix $A$ above was a subspace of $\mathbb{R}^4$. ==The nullspace of $A$ is a subspace of $\mathbb{R}^3$ .== (since x is a 3D vector).
In our example:
$$
\begin{bmatrix}\ 1 & 1 & 2\ \\ 2 & 1 & 3 \\ 3 & 1 & 4 \\ 4 & 1 & 5 \end{bmatrix}\begin{bmatrix}x_1 \\ x_2 \\ x_3\end{bmatrix} = \begin{bmatrix}0 \\ 0 \\ 0 \\ 0 \end{bmatrix}
$$
The nullspace $N(A)$ consistes of all multiples of $\begin{bmatrix}1 \\ 1 \\ -1\end{bmatrix}$; $C_{1}+C_{2}-C_{3}$ equals the zero vector($C_{n}$ are column n). ==The nullspace is a line in $\mathbb{R}^3$.==

## Other values of b

The solutions to the equation:
$$
\begin{bmatrix}1 & 1 & 2 \\ 2 & 1 & 3 \\ 3 & 1 & 4 \\ 4 & 1 & 5\end{bmatrix}\begin{bmatrix}x_1 \\ x_2 \\ x_3\end{bmatrix} = \begin{bmatrix}1 \\ 2 \\ 3 \\ 4\end{bmatrix}
$$
do not form a subspace. The zero vector is not a solution to this equation. The set of solutions forms a line in $\mathbb{R}^3$ that passes through the points $\begin{bmatrix}1 \\ 0 \\ 0\end{bmatrix}$ and $\begin{bmatrix}0 \\ -1 \\ 1\end{bmatrix}$ but not $\begin{bmatrix}0 \\ 0 \\ 0\end{bmatrix}$.
