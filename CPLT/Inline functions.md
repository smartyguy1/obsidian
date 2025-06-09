
```c++
int add (int a, int b)
{
    //Code here
}

add(5, 6)
```
A function is used to reduce core redundancy as well as to save memory space. When a function is invoked, a bunch of tasks are performed like matching arguments, matching returns and passing the control from calling to definition and vice-versa.

But when the function definition consists of hardly one or two simple statements then the bunch of tasks appear to be time consuming.
Hence in order to save the time, C++ has the concept of inline functions.

When a function is declared inline, the function body is replicated at function falling place.

Example:
```C++
#include <iostream>
using namespace std;
inline int Square(int a){
    return a*a;
}
inline int cube(int a){
    return a*a*a;
}

int main(){
    cout<< "Square of 5" << Square(5);
    cout<< "Cube of 3 " << cube(3);
    return 0;
}

```
# Rules for inline functions
The compiler may not perform inlining in a few circumstances.
- If a function contains a loop(`for`, `while`, `do while`)
- If a function is recursive
- If a function return type is other than `void` and the return statement doesn't exist in the function calling 
- If a function contains `switch` or go-to statement

# Inline function and [[C++ OOPs|Class]]
```C++
class operation
{
    int a, b, add;
    Public:
        void get();
        void sum(); 
};

inline void operation::get(){
    cout << "enter two numbers ";
    cin >> a >> b;
}

inline void operation::sum(){
    add= a+b;
    cout << a;
}

int main(){
    operation s;
    s.get();
    s.sum();
}
```
