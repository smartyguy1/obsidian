# Introduction to Tokens
In C programming a token is the smallest element of a program that is meaningful to the compiler. 
1. **Keywords:** Keywords are reserved words predefined by the C language which have a special meaning and cannot be used as <u>identifiers.</u> Example: `int`, `return`, `void`, `if`, `else`, `while`, `for`.  K
	Uses:
	- Keywords are used to define the structure and control flow of a C program.

2. **Identifiers:**  These are names given to various program elements like variables, functions, arrays etc.
	Rules for naming identifiers:
	- Must begin with a letter(uppercase or lowercase) or an underscore
	- Cannot use keywords as identifiers
	- C is case sensitive

3. **Constants:** These are fixed values that do not change during the execution of a program. Eg: [[Data Types| Integer]] constants (`const int`), Floating point constants(`const float`), character constant(`const char`), [[Strings|string]] constant

4. **Operators:** They are symbols that perform operations on variables and values. 
	Types of Operators:
	1. Arithmetic Operators (`+`, `-`, `*`, `/`)
	2. Relational Operators (`==`, `!=`, `<=`, `>=`)
	3. Logical Operators( `&&`, `||`, `!`)
	4. Bitwise operations(`&`, `|`, `-`, `<<`, `>>`)
	5. Assignment Operators (`=`, `+=`, `-=`, `*=`, `/=`, `%=`)
	6. Increment and Decrement Operators (`++`, `--`)
	7. Conditional Operators(`?: (ternary operator)`)
	8. Comma Operator (`,`)

5. **Special Symbols:** Characters that have special meanings in C. And are used for various purposes like grouping, punctuation etc. Eg: 