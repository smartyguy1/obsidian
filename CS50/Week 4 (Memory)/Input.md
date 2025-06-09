We can re-implement `get_int()` from `cs50.h` header file as follows:
```C
#include <stdio.h>

int main(void)
{
	int x;
	printf("x: ");
	scanf("%i", &x);
	printf("x: %i\n", x);
}
```

However attempting to re-implement `get_string()` is not easy. Consider
```C
#include <stddio.h>

int main(void)
{
	char *s;
	printf("s: ");
	scanf("%s", s);
	printf("s: %s\n", s)
}
```
Notice that `&` id not required because strings are pointers. But still the program will not function. Nowhere is this program do we [[Dynamic Memory Allocation|allocate the amount of memory required]] for our string. Indeed we don't know how long of a string may be inputted by the user.

The code can be modified as follows.
```C
#include <stdio.h>
#include <stdlib.h>

int main(void)
{
	char* s = malloc(4);
	if (s==NULL)
		return 1;
	printf("s: ");
	scanf("%s", s);
	printf("s: %s\n", s);
	free(s)
	return 0;
}
```
Notice that if a string greater then 4 bytes is provided, you *might* get an error.

- Simplifying our code as follows we can further understand this essential problem of pre-allocation:
```C
#include <stdio.h>

int main(void)
{
	char s[4];
	printf("s: ");
	scanf("%s",s);
	printf("s: %s\n", s);
}
```
Notice that if we type a string larger than 4 characters we will get an error.

- Sometimes, the compiler or the system running it may allocate more memory than we indicate. Fundamentally, though, the code is unsafe. We cannot trust that the user will input a string that fits into our pre-allocated memory.
# File I/O

^1acb0d

- You can read from and manipulate files. 
Consider the following code for `phonebook.c`:
```C
#include <cs50.h>
#include <stdio.h>
#include <string.h>

int main(void)
{
	// Open csv file
	FILE *file = fopen("phonebook.csv", "a");
	
	// Get name and number
	char *name = get_string("Name: ");
	char *number = get_string("Number: ");
	
	//Print to file
	fprintf(file, "%s,%s\n", name, number);
	
	// Close file
	fclose(file);
}
```
Notice that this code uses pointers to access the file.

- You can create a file called `phonebook.csv` in advance of running the above code. After running this program and inputting name and phone number, you will notice that this data persists in your csv file.
- If we want to ensure that `phonebook.csv` exists prior to running the program, we can modify our code as follows:
```C
#include <cs50.h>
#include <stdio.h>
#include <string.h>

int main(void)
{
	// Open CSV file
	FILE *file = fopen("phonebook.csv", "a");
	
	if(!file)
		return 1;
	
	// Get name and number
	char *name = get_string("Name: ");
	char *number = get_string("Number: ");
	
	//Print to file
	fprintf(file, "%s,%s\n", name, numnber);
	
	//Close file
	fclose(file);
}
```
Notice that this program protects against a `NULL` pointer by invoking `return 1`.
We can implement our own *copy* program. `cp.c`:
```C
#include <stdio.h>
#include <stdint.h>

typedef uint8_t BYTE;

int main(int argc, char *argv[])
{
	File *src = fopen(argv[1], "rb");
	File *dst = fopen(argv[2], "wb");
	
	BYTE b;
	
	while (fread(&b, sizeof(b), 1, src) != 0)
		fwrite(&b, sizeof(b), 1, dst);
	
	fclose(dst);
	fclose(src)
}
```
`uint8_t` is short for a type of unsigned integer of length 8 bits.
- BMPs are also assortments of data that we can examine and manipulate.
