`Command-line arguments` are those arguments that are passed to your program at the command line. For example, all those statements you typed after `clang` are considered command line arguments. You can use these arguments in your own programs.
 
Consider the following code.

```C
#include <cs50.h>
#include <stdio.h>

int main(int argc, string argv[])
{
    if (argc == 2)
    {
        printf("hello, %s\n", argv[1]);
    }
    else
    {
        printf("hello, world\n");
    }
}
```
Here we two arguments passed into the main function:
**int argc** stores the number command-line arguments passed.
**string argv[]** (argument vector)stores all the command-line arguments we passed.\[Note that everything in argv is stored as a string even numbers]

Getting back to the code, we have used the index 1 because at index 0 there is command we use to run the program ```./file``` . 

If in the command-line I write ```./file Bhanu``` it'll give the output ```hello, Bhanu```(since the number of arguments is 2) but if I write ```./file Bhanu Chouhan``` it'll give ```hello, world```(since the number of arguments is now 3).