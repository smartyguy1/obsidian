Destructor is a member function that is invoked automatically whenever an object is going to be destroyed. Meaning, a destructor is the last function that is going to be called before an object is destroyed. 

- It is a special member function like a constructor 
- Destructor destroys the class objects created by the constructor.
- Destructor has the same name as their class name preceded by a tilde (~) symbol.
- It is not possible to define more than one destructor
- The destructor is only one way to destroy the object created by the constructor. Hence, destructor cannot be overloaded.
- It cannot be declared static or const
- It neither requires any argument nor returns any value
- It is automatically called when an object goes out of scope.
- Destructor releases memory space occupied by the objects created by the constructor
- In destructor, objects are destroyed in the reverse of an object creation.

**Example:**
```c++
// C++ program to demonstrate the execution of constructor
// and destructor

#include <iostream>
using namespace std;

class Test {
public:
    // User-Defined Constructor
    Test() { cout << "\n Constructor executed"; }

    // User-Defined Destructor
    ~Test() { cout << "\nDestructor executed"; }
};
main()
{
    Test t;

    return 0;
}
```
