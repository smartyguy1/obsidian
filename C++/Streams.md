# What are streams?
In C++, a stream refers to a sequence of characters that are transferred between the program and input/output (I/O) devices. Stream classes in C++ facilitate input and output operations on files and other I/O devices. These classes have specific features to handle program input and output, making it easier to write portable code that can be used across multiple platforms.

To use streams in C++, you need to include the appropriate [[Header Files|header file]]. For instance, to use input/output streams, you would include `iostream` header file. This library provides the necessary functions and classes to work with streams, enabling you to read and write data to and from files and other I/O devices.

C++ streams are used in a wide variety of applications, from simple console programs to complex software systems. Some common use cases for C++ streams include:
1. Reading and writing to files
2. Parsing input
3. Debugging
4. Network Programming
### Stream class hierarchy

The C++ stream class hierarchy consists of a number of classes that define and provide different flows for objects in the class. The hierarchy is structured in a way that starts with the top class which is the `ios` class, followed by other classes such as the `istream`, `ostream`, `iostream`, `istream_withassign`, and `ostream_withassign` classes.

We can see that `ifstream` is inherited from `istream` and `ofstream` from `ostream`. 
![[Pasted image 20250529165921.png]]

# 1. The `istream` Class
This class is a general-purpose input stream and is used to read input from various sources, including the console and files. One example of an `istream` is `cin`, which is commonly used input stream for reading input from the console. The `istream` class provides a range of functions for handling characters, strings and objects including `get`, `getline`, `read`, `ignore`, `putback` and `cin`.

These functions enable developers to manipulate input in various ways. For example, the `get` function allows developers to read a single character from the input stream, while the `getline` functions reads an entire line of text and stores it in a string object. The `read` function is used to read a specific number of characters from the input stream and store them in a buffer. Overall, the `istream` class is an essential component of input stream handling in C++.

```c++
#include <iostream>
using namespace std;

int main(){
	char a;
	cin.get(a);
	cout << a;
	return 0;
}
```

# 2. The `ifstream` class

An `ifstream` object represents an input file stream, which is used to read data from a file. Since an `ifstream` is a type of `istream`, any operations that can be performed on an `istream` can also be performed on an `ifstream`.

To use `ifstream` we need to include the `fstream` header file.

# 3. The `ostream` Class
The `ostream` class is responsible for working with the output stream and provides all the necessary functions for managing chars, strings and objects such as `put`, `write`, `cout` etc.

# 4. The `ofstream` Class
An `ofstream` is an output file system, and works exactly like `ifstream`, except for output instead of input.

Once an `ofstream` is created, opened and checked for no failures, you use it just like `cout`:

```c++
ofstream fout("outputfile.txt");
fout << "The minimum oxyben percentage is " << mino2 << endl;
```
