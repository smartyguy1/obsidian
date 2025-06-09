
There are multiple ways of dynamically allocating 2D arrrays:
# Through 1-D arrays:
We can create a 1-D array but access the elements like a 2-D arrays using pointer arithmetic.
Example:
```C
#include <stdio.h>
#include <stdlib.h>
int main(void)
{
	int r = 3;
	int c = 3;
	int* arr = int* malloc(r*c*sizeof(int));
	//Putting values :
	for(int i=0; i< r*c; i++)
		arr[i] = i+1;
	// Accessing values
	for(int i=0; i<r; i++)
	{
		for(int j =0; j<c; j++)
		{
			printf("%d ", arr[r*c + j]);
		}
		printf("\n");
	}
}
```

# Making an array of pointers

We can create an array of pointers of `r` size.
Example:
```C
#include <stdio.h>
#include <stdlib.h>

int main(void)
{
	int r =3, c =4, i, j;
	int* arr[r];
	
	for(i=0; i<r; i++)
		arr[i] = (int*)malloc(c * sizeof(int));
	
	//Note that arr[i][j] is same as *(*(arr+i)+j)
	int count =0;
	for(i=0; i<r; i++)
		for(j = 0; j<c; j++)
			arr[i][j] = ++count; /* count++ increments the value but returns
			the original value while ++count returns the incremented value*/ 
	
	for(i=0; i<r; i++)
		for(j = 0; j < c; j++)
			printf("%d ", arr[i][j]);
	
	
	/*Remember we need to free the dynamically allocated memory*/
	for(i=0; i<r; i++)
		free(arr[i]);
}
```

# Using pointer to a pointer
We can create an array of pointers also dynamically using a double pointer(pointer to a pointer)

```C
#include <stdio.h>
#include <stdlib.h>

int main(void)
{
	int r=3, c=4, i,j,count;
	int** arr = (int**)malloc(r * sizeof(int*));
	
	for (i=0; i<r; i++)
		arr[i] = (int*)malloc(c * sizeof(int));
	// Note that arr[i][j] is the same as *(*(arr+1)+j)
	
	count =0;
	for(i=0; i<r; i++)
		for(j=0; j<c; j++)
			arr[i][j] = ++count;
	
	//Print the values
	for(i=0; i<r; i++)
		for(j=0;j<c; j++)
			printf("%d ", arr[i][j]);
	
	for(i=0; i<r; i++)
		free(arr[i]);
}
```