- The C keyword `typedef` provides a way to create a shorthand or rewritten name for data types.
- The basic Idea is to first define a type in the normal way, then alias it to something else.
```C
typedef <old name> <new name>;
```

# Strings
[[Arrays#^c8164c|Recall]] that a string is simply an array of characters. For eg: `string s ="HI!"` can be represented as follows:
![[Pasted image 20240722144149.png|400]]
==`s` is a pointer that tells the compiler where the beginning of a string is in memory.==
We can also write:
```C
#include <stdio.h>

int main(void)
{
	char *s = "HI!";
	printf("%s\n", s);
}
```
This will present the string that starts at the location of `s`. This code effectively removes the training wheels of the `string` data type offered by `cs50.h`. This is raw C code, without the scaffolding of the cs50 library.

The string data type is created using `typedef`:
```C
typedef char* string;
```

# [[Pointers|Pointer]] Arithmetic

- We can access each character of a string as follows:
```C
#include <stdio.h>

int main(void)
{
	char *s = "HI!";
	printf("%c\n", s[0]);
	printf("%c\n", s[1]);
	printf("%c\n", s[2]);
}
```
Notice that we are printing each character at the location on `s[n]`.
- Further, we can modify our code as :
```C
#include <stdio.h>

int main(void)
{
	char *s = "HI!";
	printf("%c\n", *s);
	printf("%c\n", *(s + 1));
	printf("%c\n", *(s + 2));
}
```
==Notice that the first character at the location of `s` is printed. Then, the character at the location `s+1` is printed and so on.==


