In C, header files contain a set pre-defined standard library [[Functions|functions]] for us to use. 
They a file extension of .h and can be used by ```#include```.
The syntax for usage is the following:
```C
#include <filename.h> // for files in system/default directory
#include "filename.h" // for files in the same directory as the program
```

# Types of header files
There are two types:
**1. Standard Header Files/Pre-existing header files
2.Non Standard/User-defined header files

## Standard Header Files
These contain the files defined in the ISO standard of the C-language.
They are stored in the default directory of the compiler.
There are 31 standard header files in the latest version of the c-language.


| Header        | Description                                                                                                                                                                                                                                                                                                                             |
| ------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `<assert.h>`  | It contains information for adding diagnostics that aid program debugging.                                                                                                                                                                                                                                                              |
| `<errorno.h>` | It is used to perform error handling operations like errno(),strerror(),perror()                                                                                                                                                                                                                                                        |
| `<float.h>`   | It contains a set of various platform-dependent constants related to floating point values. These constants are proposed by ANSI C.                                                                                                                                                                                                     |
| `<math.h>`    | Used for performing mathematical operations like sqrt(), log2(), pow().                                                                                                                                                                                                                                                                 |
| `<signal.h>`  | It is used to perform signal handling functions like signal() and raise().                                                                                                                                                                                                                                                              |
| `<stdarg.h>`  | It is used to perform standard argument functions like va_start() and va_arg(). It is also used to indicate start of the variable-length argument list and to fetch the arguments from the variable-length argument list in the program respectively.                                                                                   |
| `<stdio.h>`   | It is used for standard input or output functions like scanf(), printf() etc                                                                                                                                                                                                                                                            |
| `<setjump.h>` | It contains standard utility functions like malloc(), realloc(), etc. It contains function prototypes for functions that allow bypassing of the usual function call and return sequence.                                                                                                                                                |
| `<string.h>`  | t is used to perform various functionalities related to string manipulation like strlen() strcmp(), strcpy(), size(), etc.                                                                                                                                                                                                              |
| `<limits.h>`  | It determines the various properties of the various variable types. The macros defined in this header limits the values of various variable types like char, int, and long. These limits specify that a variable cannot store any value beyond these limits, for example, an unsigned character can store up to a maximum value of 255. |
| `<time.h>`    | It is used to perform functions related to date() and time() and getdate(). It is also used to modify the system date and get the CPU time respectively.                                                                                                                                                                                |
| `<stddef.h>`  | It contains common type definitions used by C for performing calculations.                                                                                                                                                                                                                                                              |
| `<locale.h>`  | It contains function prototypes and other information that enables a program to be modified for the current locale on which it’s running. <br>It enables the computer system to handle different conventions for expressing data such as times, dates, or large numbers throughout the world.                                           |
## Non-Standard Header files
They are all the header files that are not part of the language's ISO standard. They are usually all the header files defined by programmers for specific use. They are manually installed by the user or maybe part of the compiler by some special vendor.

Some common header files are: 

| Header        | Description                                                               |
| ------------- | ------------------------------------------------------------------------- |
| `<cs50.h>`    | Used by cs50 students, acts like training wheels for beginner programming |
| `<gtk/gtk.h>` | Contains GNUs GUI library for C                                           |
| `<conio.h>`   | It contains some useful console functions                                 |
### Create your own header file
Step1: Write code in C and save with .h extension
Step2: Include with ```#include "file.h" ```(make sure to save the file in the same directory as the main program.)