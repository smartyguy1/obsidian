Helping functions that can modify the input or output stream. They can be included in the I/O statement to alter the format parameters of a stream. They are defined inside `iomanip` and some are also defined inside `iostream` header file.

## 1. Output Stream Manipulators

Output stream manipulators are used to control and format the output stream, such as setting the width, precision, or alignment of printed data. They allow for better presentation of output.

| Manipulator             | Description                                         | Header File |
| ----------------------- | --------------------------------------------------- | ----------- |
| **endl**                | Inserts a newline and flushes the output stream.    | iostream    |
| **flush**               | Flushes the output stream manually.                 | iostream    |
| **setw(x)**             | Sets the width of the next output field to x.       | iomanip     |
| ****setprecision(x)**** | Sets the precision for floating-point numbers to x. | iomanip     |
| ****fixed****           | Displays numbers in fixed-point notation.           | iomanip     |
| ****scientific****      | Displays numbers in scientific notation.            | iomanip     |
| ****showpoint****       | Forces the display of the decimal point.            | iomanip     |
| ****noshowpoint****     | Hides the decimal point unless necessary.           | iomanip     |
```c++
#include <iostream>
#include <iomanip>
using namespace std;

int main() {
  
    // Output a new line and flush the stream
    cout << "Hello" << endl;

    // Set width to 10 for the next output
    cout << setw(10) << 42 << endl;

    // Set precision to 3 for floating-point numbers
    cout << setprecision(3) << 3.14159 << endl;

    // Use fixed-point notation
    cout << fixed << 3.14159 << endl;

    // Use scientific notation
    cout << scientific << 3.14159 << endl;

    // Show the decimal point even for whole numbers
    cout << showpoint << 42.0;
    
    return 0;
}
```
```OUTPUT
Hello
        42
3.14
3.142
3.142e+00
4.200e+01
```
## 2. Input Stream Manipulators
Input stream manipulators are used to modify the behavior of the input stream. They help in processing input efficiently such as skipping unnecessary whitespaces with `ws`.

| ****Manipulator**** | ****Description****                            | ****Header File**** |
| ------------------- | ---------------------------------------------- | ------------------- |
| ****ws****          | Skips leading whitespaces in the input stream. | iostream            |
| ****noskipws****    | Disables skipping of leading whitespaces.      | iostream            |
```c++
#include <iostream>
using namespace std;

int main() {
    char c1, c2;

    // Input skips whitespace by default
    cin >> c1;  

    // Input the next character without skipping whitespace
    cin >> noskipws >> c2;  

    cout << "c1: " << c1 << ", c2: " << c2;
    return 0;
}
```
```INPUT
    s    x
```
```OUTPUT
c1: s, c2:
```

## 3. Boolean Manipulators
They are used to format Boolean values in output.

| ****Manipulator**** | ****Description****                        | ****Header File**** |
| ------------------- | ------------------------------------------ | ------------------- |
| ****boolalpha****   | Displays true or false for boolean values. | iostream            |
| ****noboolalpha**** | Displays 1 or 0 for boolean values.        | iostream            |
```c++
#include <iostream>
using namespace std;

int main() {
    bool value = true;

    // Display boolean as true/false
    cout << boolalpha << value << endl;

    // Display boolean as 1/0
    cout << noboolalpha << value;

    return 0;
}
```
```OUTPUT
true
1
```

## 4. Alignment and sign manipulators
These manipulators control how text and numbers are aligned or how their signs are displayed in the output.

| ****Manipulator**** | ****Description****                         | ****HeaderFile**** |
| ------------------- | ------------------------------------------- | ------------------ |
| ****left****        | Aligns output to the left.                  | iomanip            |
| ****right****       | Aligns output to the right.                 | iomanip            |
| ****internal****    | Aligns signs and base prefixes to the left. | iomanip            |
| ****showpos****     | Displays a + sign for positive numbers.     | iostream           |
| ****noshowpos****   | Hides the + sign for positive numbers.      | iostream           |
```c++
#include <iostream>
#include <iomanip>
using namespace std;

int main() {
    int n = 42;

    // Align output to the left
    cout << left << setw(10) << n << endl;

    // Align output to the right
    cout << right << setw(10) << n << endl;

    // Show positive sign for numbers
    cout << showpos << n << endl;

    // Don't show positive sign for numbers
    cout << noshowpos << n;

    return 0;
}


```
### 5. Base Manipulators
Base manipulators are used to format numbers in different bases, such as decimal, hexadecimal, or octal. They help in representing numbers in a way suited to specific applications.

| ****Manipulator**** | ****Description****                 | ****Header File**** |
| ------------------- | ----------------------------------- | ------------------- |
| ****hex****         | Formats output in hexadecimal base. | iostream            |
| ****dec****         | Formats output in decimal base.     | iostream            |
| ****oct****         | Formats output in octal base.       | iostream            |
```c++
#include <iostream>
using namespace std;

int main() {
    int n = 42;

    // Output in hexadecimal base
    cout << hex << n << endl;

    // Output in decimal base
    cout << dec << n << endl;

    // Output in octal base
    cout << oct << n;

    return 0;
}
```
```OUTPUT
2a
42
52
``````o
```