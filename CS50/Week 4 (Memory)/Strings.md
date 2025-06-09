# String Comparison
- A string character is simply an array of characters identified by its first byte.
- Earlier we considered comparing integers using `==` operator. In case of strings however we cannot use this method
- Utilizing `==` to compare strings will attempt to compare the memory locations of the strings instead of the characters therein. Accordingly, we recommended the use of `strcmp`
- To illustrate this,
```C
#include <stdio.h>
#include <cs50.h>

int main(void)
{
	//get two strings
	char *s = get_string("s: ");
	char *t = get_string("t: ");
	
	//compare strings addresses
	if (s == t)
		printf("Same\n");
	
	else
		printf("Different\n");
}
```

Notice that typing `HI!` for both strings still results in the output `Different`.

Let us visualise what's happening:
![[Pasted image 20240722150517.png|500]]
Here we can see that `s` and `t` are actually pointers and on using `==` we are comparing the position of the stored strings in memory which are obviously different since they are both separate strings stored in separate positions in memory.

- Using `strcmp` instead of `==` we can correct the above code.
- We can see the locations of these two strings with a small modification:
```C
#include <stdio.h>
#include <cs50.h>

int main(void)
{
	// Get two strings
	char *s = get_string("S: ");
	char *t = get_string("T: ");
	
	//Print strings' addresses
	printf("%p\n", s);
	printf("%p\n", t);
}
```
Notice that the `%s` has been changed to `%p` in the print statement.

# Copying
- A common need in programming is to copy one string to another
However we can't use `=` operator when using pointers. Why?
```C
#include <stdio.h>
#include <ctype.h>
#include <cs50.h>
#include <string.h>

int main(void)
{
	// Get a string
	string s = get_string("s: ");
	
	// Copy string's address
	string t = s;
	
	// Capitalize first letter
	t[0] = toupper(t[0]);
	
	// Print string twice
	printf("s: %s\n", s);
	printf("t: %s\n", t);
}
```
Notice that `string t = s` copies the address of `s` to `t`. This does not accomplish what we are desiring. The string is not copied - only the address is.

- We can visualize it as follows:![[Pasted image 20240722151848.png|500]]
- So `s` and `t` are still pointing at the same blocks of memory. This is not an authentic copy of a string. Instead, these are two pointers pointing at the same string.
- Before this, its important to ensure that we don't experience a *segmentation fault* through our code, where we attempt to copy `string s` to `string t`, where `string t` does not exist. We can employ `strlen` function to assist with that:
```C
#include <stdio.h>
#include <cs50.h>
#include <ctype.h>
#include <string.h>

int main(void)
{
	// Get a string
	string s = get_string("s: ");
	
	// Copy string's address
	string t = s;
	
	// Capitalize first letter in string
	if (strlen(t) > 0)
		t[0] = toupper(t[0]);
	
	// Print string twice
	printf("s: %s\n", s);
	printf("t: %t\n", t);
}
```
Notice that `strlen` is used to make sure `string t` exists. If it does not, nothing will be copied.

To be able to make an authentic copy of the string, we will need to introduce two new building blocks. 
- ==First, `malloc` allows the programmer to allocate a block of a specific size of memory.==
- ==Second, `free` allows us to tell the compiler to *free up* that block of memory we previously allocated.==
- ==To use these we need to include the header file, `stdlib.h`==
To create an authentic copy:
```C
#include <stdio.h>
#include <cs50.h>
#include <ctype.h>
#include <stdlib.h>
#include <string.h>

int main(void)
{
	// Get a string
	char *s = get_string("s: ");
	// Allocate memory for another string
	char *t = malloc(strlen(s)+1);
	// Copy string into memory, including '\0'
	for (int i=0, n=strlen(s); i<=n; i++)
		t[i] = s[i];
	// Capitalize copy
	t[0] = toupper(t[0]);
	// Print strings
	printf("s: %s\n", s);
	printf("t: %t\n", t);
}
```

The C language has a built-in function to copy strings called `strcpy`. It can be implemented as follows:
```C
#include <cs50.h>
#include <ctype.h>
#include <stdio.h>
#include <string.h>
#include <stdlib.h>

int main(void)
{
	// Get a string
	char *s = get_string("S: ");
	
	// Allocate memory for another string
	char *t = malloc(strlen(s)+1);
	
	// Copy string into memory
	strcpy(t,s);
	
	// Capitalize copy
	t[0] = toupper(t[0]);
	
	// Print strings
	printf("s: %s\n", s);
	printf("t: %s\n", t);
}
```

