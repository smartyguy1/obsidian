# Memory
We may [[Arrays#^5da109|recall]] the artist rendering of concurrent blocks of memory. Applying [[Pixels and Hexadecimals#^c11312|Hexadecimal]] notation, we can visualize these as follows:
![[Pasted image 20240720163820.png|500]]
Let us write a program to store a value in memory
```C
#include <stdio.h>

int main(void)
{
	int n =50;
	printf("%i\n",n);
}
```
- You can visualize how this variable is stored as follows:
![[Pasted image 20240720164019.png|500]]
- The c language has 2 powerful operators that relate to memory:
```
& Provides the address of something stored in memory.
* Instructs the compiler to go to a location in memory.
```
- We can leverage this knowledge by modifying our code as follows:
```C
#include <stdio.h>

int main(void)
{
	int n= 50;
	printf("%p\n", &n);
}
```
`%p` allows us to view the address of a location in memory. `&n` can be literally translated as "the address of `n`". Executing this code will return an address of memory beginning with `0x`.

# Pointers
- A pointer is a variable that contains the address of some value. Most [[Definitions#^62779f|succinctly]], a pointer is an address in your computer's memory.
- Consider the following code:
```C
int n = 50;
int *p = &n; // pointer p that *points* to n
```
Notice that `p` is a pointer that contains the address of an integer `n` .

- The `&` operator is called **The address extraction operator**.
	- If `x` is an `int`-type variable, then `&x` is a pointer-to-`int` whose ==value is the address of `x`==.
	- If `arr` is an array of doubles, then `&arr[i]` is a pointer-to-`double` whose value is the address of the `i`th element of `arr`.
		- An array's name, then, is actually just a pointer to its first element

- To work with the location the pointer points to, **dereference** the pointer.
	- If we have a pointer-to-`char` called `pc` then `*pc` is the data that lives at the memory address stored inside the variable `pc`.
	- **Used in this context** `*` is known as the **dereference operator**. It "goes to the reference" and access the data at that memory location, allowing you to manipulate it at will.
		- We can then interpret the code `int* p` when defining a pointer as, ==The value of p is an address we can dereference using `*`. If we do, we'll get an `int` at that location.==

- pointers provide an alternative way to pass data between functions.
	- Recall that up to this point we have passed all data [[Arrays|by value]], with one exception.

- If we use pointers instead, we have the power to pass the actual variable itself
	- That means that a change made in one function can impact what happens in a different function.
	- Previously, this wasn't possible!

We can imagine memory as a big array of byte-sized cells

Recall that [[Arrays]] are not only useful for storage of information but also for so-called **random access**.
	We can access individual elements of the array by indicating which index location we want.


Similarly, each location in memory has an **address**.

+ As we start to work with pointers, just keep this image in mind:
![[Pasted image 20240721153122.png|500]]

A **pointer** then is a data item whose:
- *value* is a memory address
- *type* describes the data located at that memory address
==As such, pointers allow data structures and/or variables to be shared among functions== 

- The simplest pointer available to us in C is the `NULL` pointer.(It points to nothing)
- ==When you create a pointer and don't set its value immediately, you should **always** set the value to `NULL`==
- We can check whether a pointer is `NULL` using `==`.

- If we dereference a pointer-to-`NULL` ==we will encounter a segmentation fault==.
	- This is good as its defends against accidental dangerous manipulation of unknown pointers.
		- That's why it is recommended to set your pointers to `NULL` immediately if you aren't setting them to a known, desired value.

