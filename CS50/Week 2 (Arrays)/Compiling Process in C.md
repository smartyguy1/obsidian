In vscode, a standard compiler is used called *clang* or ```clanguage```.
The command ```make hello``` executes clang compiler to create a file that can be run by the user. VScode has been preprogrammed such that ```make``` will run numerous command-line-arguments along with clang for convenience of the user. 

To manually use clang:
```clang -o file.c file ```
If we run this for the given program we'll get an error which indicates that the compiler does not know where to find the cs50 library.(Even though we wrote ```#include <cs50.h>``` it will not recognise *get_string* function because the header file only contains the declaration of the functions, to get the code of those functions the compiler must access the cs50 library.)
 
if we run ```clang -o file.c file -lcs50``` the program executes without any errors.
This command tells the compiles to "link" the cs50 library to file.c(**-lcs50 stands for link cs50.**)

We do not need to do the similar thing for *stdio.h* because it is a standard library, and is present in the default directory of the compiler i.e. the compiler knows where to find it. That is not the case with the *cs50.h* library. 

When Compiling a C program it follows 4 important steps before it runs. These are:
**1.)Preprocessing
2.)Compiling(confusing but just gulp it)
3.)Assembling
4.)Linking
Consider this code:
```C
	#include <cs50.h>
	#include <stdio.h>
	int main(void)
	{
	   string name = get_string("What's your name? ");
	   printf("hello, %s\n", name);
	}
```

A compiler will convert this code to the following machine code.
![[Pasted image 20240701182330.png]]
# Preprocessing
First the [[Header Files ]] (referenced by '#', eg: ```#include <cs50.h>```) are effectively copied and pasted into your code.(We can think of header statement as a reference to another file of code that contains useful function definition(more on that [[Header Files|later]])) 
This is a cue for the compiler to get the files that are referenced, anywhere from your computer.
# Compiling
This is where our program is converted to [[Pasted image 20240701184057.png|assembly code]]. 
*Funfact: Before C was developed, this was the main programming language and programmers used to write their code in assembly code.*
# Assembling
At this stage our assembly code is converted to [[Pasted image 20240701182330.png|machine code]]machine code(0s and 1s)

# Linking
At the final stage the the machine code of our program and all the header files is linked together into one file which can now be executed.