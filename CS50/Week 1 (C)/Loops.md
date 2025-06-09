# For loops:
Syntax: 
```c
	for (int i = 0; i <n; i++)
	{
		//code..
	}
```
We can see 3 sections inside *for*.The first one is only read once and the other 2 are read after every turn. 2nd block is bool type that decides whether conditions are met to run the loop and 3rd is a command that is run at the end of every loop.

# While Loops:
There are two ways of using While loops
First:
	Syntax:
```c
	bool condition = True;
	while(condition)
	{
		//code
	}
```
Second:
	Syntax
```c
	do
	{
		//code..
	}
	while(condition); //Dont forget the semicolon
```
Here the first the program run the code in *do* and then checks if the condition(s) passed in *while* is met. If they are, then the same code run again until the condition(s) fail to meet.

It is safe to say that both loops need a[[Data Types and Variables#^e7bda0| Boolean]] value that serves as a condition that needs to be filled every time a loop is run.