In C++, input and output are performed in the form of a sequence of bytes or more commonly known as [[Streams|streams]]

- Input stream
- Output stream
### Standard Output Stream - cout
The C++ `cout` is the instance of the `ostream` class. The data needed to be displayed on the screen is inserted in the standard output stream (cout) using the insertion operator(`<<`)
```c++
#include <iostream>
using namespace std;

int main() {
	// Printing the given text using cout
	cout << "GeeksforGeeks";
	return 0;
}
```

### Standard Input Stream - cin
The C++ `cin` statement is the instance of the class `istream` and is used to read input from the standard input device which is usually a keyboard. The extraction operator(`>>`) is used. Also remember that `cin` stops reading as soon as it encounters a whitespace character after a non-whitespace character.
```c++
#include <iostream>
using namespace std;

int main(){
	string name;
	// Taking input from user and store
	// it in variable
	cin >> name;
	// Output the entered name
	cout << "Name entered: " << name;
	return 0;
}
```
```OUTPUT
Vishal Kumar
Name entered: Vishal
```

### Un-buffered Standard Error Stream - `cerr`
The C++ `cerr` is the standard error stream that is used to output the errors. This is also an instance of the `ostream` class. `cerr` is Un-buffered, so it is used when one needs to display the error message immediately. It does not have any buffer to store the error message and display it later.

When using `cout` you can redirect the output to file but using `cerr` the output doesn't get stored in file.

```C++
#include <iostream>
using namespace std;

int main(){
	cerr << "An error occured";
	return 0;
}
```
```Error
An error occured
```
### Buffered Standard Error Stream - `clog`

This is also an instance of `ostream` class and used to display errors but unlike `cerr` the error is first inserted into a buffer and is stored in the buffer until it is not fully filled, or the buffer is not explicitly flushed(using `flush()`). The error message will be displayed on the screen too.

```c++
#include <iostream>
using namespace std;

int main(){
	clog<< "An error occurred";
	return 0;
}
```
```Error
An error occurred
```