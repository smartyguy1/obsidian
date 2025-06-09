We can use pointers to get access to a block of **Dynamically allocated memory** at runtime

Dynamically allocated memory comes from a pool of memory known as the **heap**. Prior to this point all memory we've been working with has been coming from a pool of memory known as the **stack**.
![[Pasted image 20240723150624.png]]

# malloc

- We get this dynamically-allocated memory by making a call to the C standard library function `malloc()`, passing as its parameter the number of bytes requested.
- After obtaining memory for you(if it can), `malloc()` will return a pointer to that memory.
- If `malloc` can't give you memory, it'll hand you back `NULL`.
```C
// Statically obtain an integer
int x;
// dynamically obtain an integer
int *p = malloc(sizeof(int));

// array of floats on the stack
float stack_array[x];
float* heap_array = malloc(x * sizeof(float));
```
- Dynamically allocated memory is not automatically returned to the system for later use when the function in which it's created finishes execution.

- Failing to returns memory back to the system when you're finished with it results in  a **memory leak** which can compromise your system's performance.

- When you finish working with dynamically-allocated memory, you must `free()` it.
```C
char* word = malloc(50* sizeof(char));
//do stuff with word

// now we're done working with that block
free(word);
```

## Three Golden Rules:
1. Every block of memory that you `malloc` must subsequently be `free()` d.

2. Only memory that you `malloc()` should be `free()` d.

3. Do not `free()` a block of memory more than once.


# Valgrind
- Valgrind is a tool that can check to see if there are memory-related issues with your programs wherein you untilized `malloc`. Specifically, it checks to see if you `free` all the memory allocated.
- Consider the code `memory.c`:
```C
#include <stdio.h>
#include <stdlib.h>

int main(void)
{
	int *x = malloc(3*sizeof(int));
	x[1] = 72;
	x[2] = 73;
	x[3] = 33;
}
```
Notice that running this program does not cause any errors. While `malloc` is used to allocate enough memory for an array, the code fails to `free` that allocated memory.

- If you type `make memory` followed by `valgrind ./memory`, you will get a report from valgrind that will report where memory has been lost as a result of your program. One error that valgrind reveals is that we attempted it assign the value off `33` at the 4th position of the array, where we only allocated an array of size `3`. Another error is that we never freed `x`.
- We can modify our code as follows:
```C
#include <stdio.h>
#include <stdlib.h>

int main(void)
{
	int *x = malloc(3 * malloc(int));
	x[0] = 72;
	x[1] = 73;
	x[2] = 33;
	free(x);
}
```
Notice that running valgrind again now results in no memory leaks.

# Garbage Values
When you ask the compiler for a block of memory that you allocated was previously utilized by the computer. Accordingly, you may see *junk* or *garbage values*. This is a result of getting a block of memory but not utilizing it.
For eg: the following code for `garbage.c`
```C
#include <stdio.h>

int main(void)
{
	int scores[1024];
	for (int i=0; i<1024; i++)
		printf("%i\n", scores[i]);
}
```
Notice that running this code will allocate `1024` locations in memory for your array, but the `for` loop will likely show that not all values therein are`0`. It's always best practice to be aware of the potential for garbage values when you do not initialize blocks of memory to some other value like zero or otherwise.

# Swap
- In the real world, a common need in programming is to swap two values. Naturally, it's hard to swap two variables without a temporary holding space. In practice, you can type `code swap.c` and write those code:
```C
#include <stdio.h>

void swap(int a, int b);

int main(void)
{
	int x=1;
	int y=2;
	printf("x is %i, y is %i\n", x,y);
	swap(x,y);
	printf("x is %i, y is %i\n", x,y);
}

void swap(int a, int b)
{
	int temp = a;
	a = b;
	b = temp;
}
```
Notice that while the code runs, it does not work. The values even after being sent to the `swap()` function do not pass. [[Data Types and Variables#^c2b4cb|Why?]]
The values of `x` and `y` created in the curly `{}` braces of the `main` function only have the scope of the `main` function.
![[Pasted image 20240723160513.png|500]]
![[Pasted image 20240723160436.png|500]]
Notice that *global* variables, live in one place in memory. Various functions are stored in the `stack` in another area of memory.
The function `main` and `swap` are two separate *frames* or areas of memory. Therefore, we cannot pass the values from one function to another to change them.

Modify the code as follows:
```C
#include <stdio.h>

void swap(int *a, int *b);

int main(void)
{
	int x =1;
	int y=2;
	printf("x in %i, y is %i", x,y);
	swap(&x,&y);
	printf("x in %i, y is %i", x,y);
}

void swap(int *a, int *b)
{
	int temp = *a;
	*a = *b;
	*b = temp;
}
```
Instead of the variables, the function takes [[Pointers]] that contain the addresses of `a` and `b`. Therefore, the `swap` function can know where to make changes to the actual `a` and `b` from the main function.
We can visualize it as:
![[Pasted image 20240723161240.png|500]]

# Overflow
- **Heap overflow**: when the heap is overflowed, touching areas of memory we are not supposed to.
- **Stack Overflow**: When too many functions are called, overflowing the amount of memory available.
- Both of these are **buffer overflows**
