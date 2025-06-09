# Functions in C:
They are also known as methods, procedures and subroutines.

We call it the black box because if we are not writing the function we don't need to know about the underlying implementation.

Functions in C are characterised based on the type of value that they return.
\[Note that it is mandatory for the function to have a [[Data Types and Variables || data type]] when defining it]

There can also be functions that return no value but are just blocks of code to be run when called(variable that calls a block of code). These are [[Data Types and Variables#^506d44|Void]] type functions.

Remember that the *int main (void)* function (which is the main function) is an integer type function. This is because it return a value 0 to the compiler after running meaning to stop the program. 

# Defining a Function:
A function can be defined using the following syntax:
```
return_type func_name(prompt)
```
A function can have specific variables that need to be passed, the *prompt* contains the definition and other characteristics of the variables. If you don't want to pass any variable you write *void* in *prompt*.

When defining a function it becomes tedious to first define it **and then**  call it since this pushes the main function further down.

To tackle this what we can do is write the function after the *int main*  function but define it before the main function.
syntax:
```C
int get_num(int num);

int main(void)
{
	//code
}
int get_num(int num)
{
	//function code..
}

```

# Why use Functions?

**1 Organization
2 Simplicity
3 Reusability**

