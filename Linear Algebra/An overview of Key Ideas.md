# Vectors
What do we do with vectors? Take combinations
Given vectors $\pmb{u}, \pmb{v}$ and $\pmb{w}$ we can form the linear combination $x_1\pmb{u}+x_2\pmb{v}+x_{3}\pmb{w}= \pmb{b}$
An example in $\mathbb{R}^3$ would be:
$$
\pmb{u} = \begin{bmatrix}1 \\-1\\ 0\end{bmatrix}, \pmb{v} = \begin{bmatrix}0 \\ 1 \\ -1\end{bmatrix}, \pmb{w} = \begin{bmatrix}0 \\ 0 \\ -1 \end{bmatrix}
$$
The collection of all multiples of $u$ forms a line through the Origin. The collection of all combinations of $\pmb{u},and\space \pmb{v}$ forms a plane. Taking all *combinations* of some vectors creates a *subspace*.

# Matrices
Create a matrix $A$ with vectors  $\pmb{u}, \pmb{v}$ and $\pmb{w}$ in its **columns**
$$
A = \begin{bmatrix}1&0&0\\-1&1&0\\0&-1&1\end{bmatrix}
$$
The product:
$$
A\pmb{x} = \begin{bmatrix}1&0&0\\-1&1&0\\0&-1&1\end{bmatrix} \begin{bmatrix}x_1\\x_2\\x_3\end{bmatrix} = \begin{bmatrix}x_1\\-x_1+x_2\\-x_2+x_3\end{bmatrix}
$$
is the same as writing the above algebraic equation $x_1\pmb{u}+x_2\pmb{v}+x_{3}\pmb{w}= \pmb{b}$
The product of a matrix and a vector is a combination of the columns of the matrix.

The matrix $A$ is a *difference matrix* because the components of $A\pmb{x}$ are differences of the components of the vector $\pmb{x}$.
==With this we have changed our perspective from multiplying vectors by numbers to multiplying a matrix by the numbers.==

For any input vector $\pmb{x}$, the output of the operation "multiplication by $A$" is some vector $\pmb{b}$:
$$
A\begin{bmatrix}1\\4\\9\end{bmatrix} = \begin{bmatrix}1\\3\\5\end{bmatrix}
$$
Another question is to start with a vector $\pmb{b}$ and ask "For what vectors $\pmb{x}$ does $A\pmb{x} = \pmb{b}$?" 
This means solving the equation:
$$A\pmb{x} = \begin{bmatrix}1&0&0\\-1&1&0\\0&-1&1\end{bmatrix} \begin{bmatrix}x_1\\x_2\\x_3\end{bmatrix} = \begin{bmatrix}x_1\\-x_1+x_2\\-x_2+x_3\end{bmatrix} = \begin{bmatrix}b_1\\b_2\\b_3\end{bmatrix}$$

is equivalent to solving
$$
\begin{align} x_{1}  =  b_{1}\\ x_{2}- x_{1} = b_{2}\\x_3- x_{2}= b_3\end{align}
$$
This gives the matrix
$$
\begin{bmatrix}x_1\\x_2\\x_3\end{bmatrix} = \begin{bmatrix}b_1\\b_1+b_2\\b_1+b_2+b_3\end{bmatrix}
$$
From this we can see that:
$$
\pmb{x} = \begin{bmatrix}1&0&0\\1&1&0\\1&1&1 \end{bmatrix}\begin{bmatrix}b_1\\b_2\\b_3\end{bmatrix}
$$
or $\pmb{x}=A^{-1}\pmb{b}$. So if the matrix $A$ is invertible, we can multiply on both sides by $A^{-1}$ to find the unique solution $\pmb{x}$ to $A\pmb{x}=\pmb{b}$. 
==We can say that $A$ represents a transform $\pmb{x} \to \pmb{b}$ that has an inverse transform $\pmb{b}\to\pmb{x}$ .==
If $\pmb{b} = \begin{bmatrix}0\\0\\0\end{bmatrix}$ then $x = \begin{bmatrix}0\\0\\0\end{bmatrix}$.
What if we replace the column $\pmb{w}$ with $\pmb{w*}$ 
Then A becomes C.
$$
C = \begin{bmatrix}1&0&-1\\-1&1&0\\0&-1&1\end{bmatrix}
$$
Then 
$$
C\pmb{x} = \begin{bmatrix}1&0&-1\\-1&1&0\\0&-1&1\end{bmatrix}\begin{bmatrix}x_1\\x_2\\x_3\end{bmatrix} = \begin{bmatrix}x_1-x_3\\x_2-x_1\\x_3-x_2\end{bmatrix}
$$
Now our systems of three equation in three unknowns becomes circular.
Where before $A\pmb{x}=\pmb{0}$ implied $\pmb{x}=0$, in this case there are non-zero vectors for which $C\pmb{x}=\pmb{0}$. For any vector $\pmb{x}$ with $x_1=x_2=x_{3}$, $C\pmb{x}=0$ . This is a significant difference; we can't multiply both sides of $C\pmb{x} = 0$ by inverse to find a non-zero solution.
$$
\begin{align}x_1-x_{3}= b_1\\x_2-x_1=b_{2}\\ x_3-x_2=b_3\end{align}
$$
If we add these equations together we get:
$$
0=b_1+b_2+b_3
$$
This tells us that $C\pmb{x} = \pmb{b}$ is has a solution only when the components of $\pmb{b}$ add up to zero.
*In a physical system, this might tell us that the system is stable as long as the forces on it are balanced.*

# Subspaces
Geometrically the above result means that the columns of $C$ lie on the same plane(They are *Dependent*; the columns of $A$ are*Independent*). There are many vectors in $\mathbb{R}^3$ which do not lie on this plane. Those Vectors cannot be written as a linear combination of the columns of $C$ and so ==correspond to values of $\pmb{b}$ for which $A\pmb{x}=\pmb{b}$ has no solution.==
==The linear combinations of the columns of $C$ form a plane in $\mathbb{R}^3$ .==
The plane of combination of  $\pmb{u},\pmb{v}, \pmb{w*}$ can be described as "all vectors $C\pmb{x}$". 

We know that vectors $\pmb{b}$ for which $C\pmb{x} = \pmb{b}$ satisfy the condition $b_1+b_2+b_3=0$. 

So the plane of all combinations of $\pmb{u}$ and $\pmb{v}$ consists of all vectors whose components sum to 0.

If we take the combinations of $\pmb{u}, \pmb{v}$ and $\pmb{w}$. We get the entire space $\mathbb{R}^3$;
We say that $\pmb{u}, \pmb{v}, \pmb{w}$ form a *basis* for $\mathbb{R}^3$.

==A basis for $\mathbb{R}^n$ is a collection of n independent vectors in $\mathbb{R}^n$==

==Equivalently, a basis is a collection of $n$ vectors whose combinations cover the whole space. Or, a collection of columns form a basis whenever a matrix which has those columns is **Invertible**.==

==A **vectors space** is a collection of vectors that is closed under linear combinations.==
==A**Subspace** is a vector space inside another vector space.==A plane through the origin in $\mathbb{R}^3$ is an example of a subspace.
==A Subspace could be equal to the space its contained in.(like sets $A\subseteq{A}$); the smallest subspace contains only the zero vector==

The Subpaces of $\mathbb{R}^3$ are:
- The origin
- a line through the origin
- a plane through the origin
- all of $\mathbb{R}^3$.

Matrices can also be rectangular. However, rectangular matrices are not invertible, but the matrix $A^TA$ (where $A$ is a rectangular matrix) may be invertible.