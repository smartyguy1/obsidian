# Fields:
A field **F** is a set together with some operations on the objects in that set which behave like ordinary addition, subtraction, multiplication and division of numbers in the sense that they obey the given rules:
- Addition is commutative: $x+y=y+x$
- Addition is Associative: $x+(y+z)=(x+y)+z$
- There is a unique element 0 (zero) such that $x+0 = x$
- To each $x$ in **F** there corresponds a unique element $(-x)$ in **F** such that $x+(-x)=0$.
- Multiplication is Commutative: $xy=yz$ 
- There is a unique non-zero element 1 (one) in **F** such that $1x=x$.
- To each non-zero $x$ in  **F** there corresponds a unique element $x^{-1}$ such that $xx^{-1} = 1$ 
- Multiplication distributes over addition; that is, $x(y+z) = xy+xz$ 
These are true for all $x$, $y$ and $z$ in **F**.

# Theorem 1:
**Equivalent Systems of linear equations have exactly the same solutions**.

Two systems of equations are **equivalent** if each equation in each system is a **linear combination** of the equations in the other system.

# Theorem 2:
**To each elementary row operation $e$ there corresponds an elementary row operation $e_1$ (of the same type as $e$) such that $e_1(e(A))=e(e_1(A))=A$ for each $A$. In other words, the inverse operation (function) of an elementary operation exists and is an elementary operation of the same type.** [[Elimination With matrices#^c22642|see here]]

# Row-equivalent/ Equivalent Matrices
If $A$ and $B$ are $m\times n$ matrices over the field F, we say that B is **row-equivalent** to A if B can be obtained from A by finite a sequence of elementary row operations.

# Theorem 3:
**If A and B are row equivalent $m\times n$ matrices, the homogeneous systems of linear equations $AX=0$ and $BX=0$ have exactly the same solutions.**

Since row-operations are reversible and B is obtained from A using elementary row-operations, each equation in the system $BX=0$ will be a linear combination of the equations in $AX=0$ And from Theorem 1 We know these two systems are equivalent.
