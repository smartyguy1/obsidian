C++, function overloading allows you to define multiple functions with the same name but different parameters. It is a form of [[OOPs|compile time polymorphism]] in which a function can perform different jobs based on the different parameters passed to it. It is a feature of object-oriented programming that increases the readability of the program.

## Different Ways of Function Overloading

A function in C++ can be overloaded in three different ways:
- By having different number of parameters.
- By having different types of parameters.
- By having both different number and types of parameters.

### Different number of parameters
```c++
#include <iostream>
using namespace std;

// Two functions taking different number
// of parameters
int multiply(int a, int b);
int multiply(int a, int b, int c);

int main() {
    
    // Calling multiply function with
    // different number of arguments
    cout << multiply(10, 2) << endl;
    cout << multiply(5, 6, 4);

    return 0;
}

// Definition of functions
int multiply(int a, int b) {
    return a * b;
}
int multiply(int a, int b, int c) {
    return a * b * c;
}
```
### Different Types of Parameters
```c++
#include <iostream>
using namespace std;

// Function with different arguments type
int add(int a, int b);
double add(double a, double b);

int main() {
    
    // Calling add function with different
    // argument type
    cout << add(10, 2) << endl;
    cout << add(5.3, 6.2);

    return 0;
}

// Function definitions
int add(int a, int b) {
    return a + b;
}
double add (double a, double b) {
    return a + b;
}
```

### Different Number and Types of Parameters
```c++
#include<iostream>
using namespace std;

// Functions overloaded with different
// argument number and types
int add(int a, double b);
double add(double a, int b, int c);

int main() {
    
    // Calling both overloaded versions
    cout << add(10, 2.5) << endl;
    cout << add(5.5, 6, 12);
    return 0;
}

// Function definitions
int add(int a, double b) { 
    return a + (double)b;
}  
double add(double a, int b, int c) {
    return a + (double)b + (double)c;
}
```
