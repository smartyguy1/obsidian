# Why use Data types? 
Having different data types helps in performing different types of operations that are only limited to a certain type of data. (For eg. we can add to integers but not two characters or strings)
1. **Int (Integer):** 
     1. Contain Integer Numbers
     2. Always Takes up 4 bytes(32bits) of memory space
     3. Range is *approx* from -2^(-31) to  2^31 -1
     4. ==This can be increased by using *long ints* or *long long ints*== 
     
     **Unsigned Integers**:
	     1.  'unsigned' is a qualifier that can be applied to certain types (including int)
         2. This doubles the +ve range of of variables of that type at the cost  of disallowing any -ve values.
        3. unsigned ints range from 0 to 2^32 -1
2. **Char(character)**:
	- Used for variables storing single characters.
	- Characters Always take up 1 byte of memory (8bits).
	- With the help of ASCII mappings of characters(A,B,C,etc..) to +ve no.s were developed.
	- Character range from -128 to 127 ( char corresponding to these numbers).
	- C originally does not have a string type to store words or sentences, so ==we create strings using [[Arrays#^14f4e3| Arrays]] of *chars*.==
3. **Float**(decimals): ^a0e480
	- Used for variables that will store floating-point values, also known as ==Real Numbers==.
	- Takes up 4 bytes of space(32bits).
	- It's a little complicated to describe the range of a float but it is safe to say that with 32 bits of precision(some might be used for integer part and some for decimal) ==precision will be limited==.
	- Floating-point decimal values generally do not have an exact binary representation. This is a side effect of how the CPU represents floating point data. For this reason, you may experience some loss of precision, and some floating-point operations may produce unexpected results.^Floating-point-Imprecision
4. **Double** (floats but better):
	- They are *double precision*. They take up 8bytes(64 bits) of memory.
	- ==Doubles allow much more precise real numbers==.
5. **Void**:
	- Is a type, but not a data type.
	- ==[[Functions]] can have void return type, which just means they don't return value(but do some operation)==
	- The parameters of a func can also be void. It simply means the func takes no parameters.
	- void can be thought of as like a placeholder for 'Nothing'. Though it is much more complex than that. ^506d44

***Additional types***:
	1. **bool(boolean value)**:
		- True/  False.^bool
	2. **String**:
		- Used for variables that will store a series of characters, which programmers typically call a string. ^e7bda0

# Ways of creating a variable:
	A.
```c
	int number; // declaration
	number = 10; //assignment
	char letter; //declaration
	letter = 'h'; //assignment
```
	 B.
```c
	int number = 10; //initialization
	char letter = 'h'; //initialization
```

```c
	// multiple variabeles of the same type can be declared together
	int hieght, width;
	float sqrt2, sqrt3, pi;
```
# Truncation(loss of data due to data type limitation):

This happens mostly when an operation on an int type variable that mathematically has a float type result. However, since the operation was done on an integer, the result will also be an integer.(Remember the GIF function in maths)
for eg:
	The output of the following code is 0 instead of 0.33(and so on) this is because the compiler was only concerned with the integer part if the value and did not calculate the decimals
```c
	int x = 1;
	int y = 3;
	int z = x/y;
	float f = x/y
	printf("%i", z) // output : 0
	printf("%f", f) // output : 0.00000
```
This can be prevented by following methods
```c
		float q = (float) x/ (float) y
		printf("%f", q) 
```
==This is called ***Type Casting*** (Converting one data type to another.)==
This outputs 0.3333 followed by some other numbers[[#^a0e480| why?]] ^066d8f

# Scope

^c2b4cb

A variable only *exists* within the realm of the [[Functions|function]] it is defined in. ==We cannot use a variable defined in a certain function outside without defining it or passing it into another function==. This **realm** is known as the **scope** of the variable.

If we want to use a variable in multiple functions or outside the main function we can declare it outside the function. 
example:
```C
#include <stdio.h>

int N;

int main(void)
{
	//code
}

int func(int num)
{
	//code
}
```
This way the scope of the variable 'N' is the whole code that is written and is not limited to just a certain function. ==N is now called a Global Variable==

==For the most part local variables are passed **by value** in function calls.When a variable is passed by value the function receives a copy of the variable and not the variable itself.== ^96940a

This means that the passed variable remains unchanged no matter what operations are performed on the copy of it in the called function definition.