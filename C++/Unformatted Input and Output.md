In C++, Using objects `cin` and `cout` for the input and the output of data of various types is possible because of overloading of operator `>>` and `<<` to recognize all the basic C++ types.

## `put()` and `get()` functions

The Class `istream` and `ostream` have predefined functions `get()` and `put()`, to handle single character input and output operations. The function `get()` can be used in two ways, such as `get(char*)` and `get(void)` to fetch characters including blank spaces, newline characters and tab. The function `get(char*)` assigns the value to a variable and `get(void)` to return the value of the character.

```syntax
char data;

// get() return the character value and assign to data variable
data = cin.get();
//or
cin.get(data)

//Display the value stored in data variable
cout.put(data);
```

```c++
// C++ program to illustrate the
// input and output of data using
// get() and puts()
#include <iostream>
using namespace std;

// Driver Code
int main()
{
    char data;
    int count = 0;

    cout << "Enter Data: ";

    // Get the data
    cin.get(data);

    while (data != '\n') {
        // Print the data
        cout.put(data);
        count++;

        // Get the data again
        cin.get(data);
    }

    return 0;
}
```
**Output:**
![[Pasted image 20250529194959.png]]

## `getline()` and `write()` functions
In C++, the function `getline()` and `write()` provide a more efficient way to handle line-oriented inputs and outputs. 
`getline()` function reads the complete line of text that ends with the new line character(`\n`). This function can be invoked using the `cin` object.

**syntax:**
```
cin.getline(variable_to_store_line, size);
```

The reading is terminated by the `\n` character. The new character is read by the function, but it does not display it. Instead, it is replaced with a `NULL character`. After reading a particular string and `cin` automatically adds the newline character at end of string.

The `write()` function displays the entire line in one go and its syntax is similar to the `getline()` function only that here `cout` object is used to invoke it.

The `write()` function does not stop displaying the string automatically when a `NULL` character occurs. If the size is greater than the length of the line then, the `write()` function displays beyond the bound of the line

```c++
// C++ program to illustrate the
// input and output of file using
// getline() and write() function
#include <iostream>
#include <string>
using namespace std;

// Driver Code
int main()
{
    char line[100];

    // Get the input
    cin.getline(line, 10);

    // Print the data
    cout.write(line, 5);
    cout << endl;

    // Print the data
    cout.write(line, 20);

    cout << endl;

    return 0;
}
```

Also, the `getline()` function first adds the `\n` character in its calculation of the size of the line and then adds the number of characters. So where its written `cin.getline(line, 10)` it actually reads the first 9 characters of the line.