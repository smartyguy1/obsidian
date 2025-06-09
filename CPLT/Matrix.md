# Matrix Addition
Two matrices can be added only if they are of the same order,
$$
\begin{bmatrix}1 & 5 \\ 7 & 3\end{bmatrix} + \begin{bmatrix}12 & -1 \\ 0 & 9\end{bmatrix} = \begin{bmatrix}1+12 & 5+(-1) \\ 7+0 & 3+9\end{bmatrix}
$$
$$
= \begin{bmatrix}13 & 4 \\ 7 & 12\end{bmatrix}
$$
```C
#include <stdio.h>

int main(void)
{
	int A[][] = {{1,5},{7,3}};
	int B[][] = {{12,-1},{0,9}};
	int c[2][2];
	for(int i =0; i<2; i++)
		for(int j = 0; j<2; j++)
			c[i][j] = A[i][j] + B[i][j];
	for(int i =0; i<2; i++)
	{
		for(int j = 0; j<2; j++)
			printf("%d ",c[i][j]);
		printf("\n");	
	}
}
```