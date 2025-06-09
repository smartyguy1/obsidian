Recursion is a concept within programming where a [[Functions|function]] calls itself. We saw this earlier ![[Search Algorithms#^4c30d1|Search Algorithms]]
==In general but not always, recursion replaces loops in non-recursive functions.==

Recursion has two cases that could apply:
**1. The Base case**, which when triggered will terminate the **recursive** process
**2. The recursive case**, which is where the recursion will actually occur
*Note that a function can have more than one base case or recursive case.

Here we call search within itself. We can implement this in the practice program we made in Week1(mario).
```C
#include <stdio.h>
#include <cs50.h>
void print(int h);

int maim(void)
{
	height = get_int("Height: ");
	print(height);
}

void print(int h)
{
	if (h<=0)
	{
		return;
	}
	
	print(h) // keeps calling the function until it reaches 0
	//which is 0 at the point this line isn't executed but the next code is.
	//following this the program is executed for all the other values.
	
	for (int i = 0; i<h; i++)
	{
		printf("#");
	}
	printf("\n");
	
}
```
The output when input is 4:
```
#
##
###
####
```
