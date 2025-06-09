We know what kind [[Data Types and Variables|data-types]] there are such as int, bool, float, double etc. Each datatype requires a certain amount of system resources. Our computers have a finite memory, each variable occupies a certain part of the memory depending on the data-type. 
When we have multiple variables it becomes tedious to use each separately.
==_Arrays_ are a way of storing data **back-to-back** in memory such that this data is easily accessible.==

# Define Arrays in C
Arrays can be defined using the following syntax
```C
int array1[3];
```
This gives us an array names *array1* which has space for 3 int values.
We can similarly make arrays of other data-types. ==However, an array can only contain elements of the same data-type.==

Arrays have the similar properties to variables in the way we use them(==Think of them as variables for a *collection* of data==)

==Note that we cannot assign one array to another. We must use a loop to carry over each element of the array one at a time to other array.==

We can also pass arrays to functions like we would do with variables.==However Unlike Variables they are not [[Data Types and Variables#^96940a|Passed-by-value]]. Instead they are passed by **Reference**, the callee(another array that has called the array) doesn't receive a copy but instead receives the actual array.==

The following example will illustrate the difference
```C
#include <stdio.h>

void set_array(int arr[3]);
void set_int(int num);

int main(void)
{
	int x = 10;
	int arr1[3] = {0,1,2};
	set_array(arr1);
	set_int(x);
	printf("%d, %d", x, arr1[0]); // outputs 10, 22 and not 10, 0 or 23, 0
	
}

void set_array(int arr[3])
{
	arr[0] = 22;
}

void set_int(int num)
{
	num = 23;
}
```
# Using Arrays
```C
#include <cs50.h>
#include <stdio.h>

int main(void)
{
    // Get scores
    int scores[3];
    scores[0] = get_int("Score: ");
    scores[1] = get_int("Score: ");
    scores[2] = get_int("Score: ");
    
    // Print average
    printf("Average: %f\n", (scores[0] + scores[1] + scores[2]) / 3.0);
}
```
Notice that the counting of the **index** of the array starts from 0 and ends with n-1(n being the size of the array).
==Index is the position of a value that is used to access the given value inside an array.(Like the index of a book)==
However, we can go outside the bounds of the indexes assigned to the array(i.e. the program will compile without any errors) but on running the program we might suffer a **Segmentation Fault** because now we are trying to access something in memory that is outside our bounds which is very dangerous.

# Strings

^c8164c

Strings are arrays multiple *char*s (char datatypes). String is an array of characters begins with the first character and ends with a special character (`\0`) called the **NUL** character. 
[[Pasted image 20240702145857.png|Consider the following image of an array ]]
Imagining this in decimal would look like [[Pasted image 20240702150011.png|this]].
So an array of size n will contain n values + a special NUL value.
Notice that characters are replaced by their ASCII counterparts. ^5da109

We can print this numbers using the same code we used to get the values in the array but replace the `%c` with `%i` .
```C
#include <stdio.h>
#include <string.h>

int main(void)
{
	char scores[3] = {'H', 'I', '!'};
	for (int i =0; i<3; i++)
	{
		printf("%c", scores[i]);
	}
	printf("\n");
	
	for (int j =0;j<3, j++)
	{
		printf("%i", scores[i]);
	}
}
```
We can further create an array of strings (or array of arrays which is called a two dimensional array)
for example:
```C
#include <stdio.h>
#include <cs50.h>

int main(void)
{
	string words[2];
	
	words[0] = "HI!";
	words[1] = "BYE!";
	
	for (int i = 0; i < 2; i++)
	{
		printf("%c\n", words[i]);
	}
	
}
```
It is a common issue of finding the size of an array in C. However, in case of strings we can utilise the existence of the NUL character to get he length of the string(or the number of characters in the string).For example
```C
#include <stdio.h>
#include <cs50.h>

int get_size(string s);

int main()
{
	string name = get_string("Name: ");
	int size = get_size(name);
	printf("\n%i", size);
}

int get_size(string s)
{
	int n = 0;
	while(s[0]!='\0')
	{
		n++
	}
	return n;
}
```
We can also use a function ```strlen()``` from the string.h library. 

```C
#include <stdio.h>
#include <cs50.h>
#include <string.h>

int main(void)
{
	string name = get_string("Name: ");
	int size = strlen(name);
	printf("%i", size);
}
```

`ctype.h` is another useful library.[Documentation here](https://manual.cs50.io/#ctype.h)
We can use a library function ```toupper()``` to convert lower case characters to upper case. (This function ignores characters that are already in upper case so we don't have to worry about it.)
For example:
```C
#include <stdio.h>
#include <cs50.h>
#include <string.h>
#include <ctype.h>

int main(void)
{
	string name = get_string("Name: ");
	printf("After: ");
	for (int i =0, size = strlen(name); i<size; i++)
	{
		printf("%c", toupper(name[i]));
	}
}
```
This prints the name in uppercase. 
