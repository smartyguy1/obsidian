A friend [[C++ OOPs#^60bda3|class]] can access private and protected members of other classes in which it is declared as a friend. It is sometimes useful to allow a particular class to access private and protected members of other classes.

**For Example: **
```c++
// C++ Program to demonstrate the
// functioning of a friend class
#include <iostream>
using namespace std;

class GFG {
private:
    int private_variable;

protected:
    int protected_variable;

public:
    GFG()
    {
        private_variable = 10;
        protected_variable = 99;
    }

    // friend class declaration
    friend class F;
};
// Here, class F is declared as a
// friend inside class GFG. Therefore,
// F is a friend of class GFG. Class F
// can access the private members of
// class GFG.
class F {
public:
    void display(GFG& t)
    {
        cout << "The value of Private Variable = "
             << t.private_variable << endl;
        cout << "The value of Protected Variable = "
             << t.protected_variable;
    }
};

// Driver code
int main()
{
    GFG g;
    F fri;
    fri.display(g);
    return 0;
}

```
Here `F` is declared as a friend class inside class `GFG`. Class `F` has access to the private members of class `GFG` but not the other way around. For that we would have to also declare `GFG` as a friend class inside  class `F`.

**Output:**
```
The value of Private Variable = 10
The value of Protected Variable = 99
```
# Friend Function 

Like a friend class, a friend function can be granted special access to private and protected members of a class in C++. They are not the member functions of the class but can access and manipulate the private and protected members of that class for they are declared as friends.

A friend function can be:
1. A Global Function
2. A member function of another class

### 1. Global Function as Friend Function

**Example:**
```c++
// C++ program to create a global function as a friend
// function of some class
#include <iostream>
using namespace std;

class base {
private:
    int private_variable;

protected:
    int protected_variable;

public:
    base()
    {
        private_variable = 10;
        protected_variable = 99;
    }
      // friend function declaration
    friend void friendFunction(base& obj);
};
// friend function definition
void friendFunction(base& obj)
{
    cout << "Private Variable: " << obj.private_variable << endl;
    cout << "Protected Variable: " << obj.protected_variable;
}
// driver code
int main()
{
    base object1;
    friendFunction(object1);

    return 0;
}

```

**Output:**
```
Private Variable: 10
Protected Variable: 99
```

### 3. Member Function of Another Class as a Friend Function
We can declare a member function of another class as a friend function by using the scope resolution operator(`::`).

**Example:**
```c++
// C++ program to create a member function of another class
// as a friend function
#include <iostream>
using namespace std;

class base; // forward definition needed
// another class in which function is declared
class anotherClass {
public:
    void memberFunction(base& obj);
};

// base class for which friend is declared
class base {
private:
    int private_variable;

protected:
    int protected_variable;

public:
    base()
    {
        private_variable = 10;
        protected_variable = 99;
    }
    // friend function declaration
    friend void anotherClass::memberFunction(base&);
};
// friend function definition
void anotherClass::memberFunction(base& obj)
{
    cout << "Private Variable: " << obj.private_variable << endl;
    cout << "Protected Variable: " << obj.protected_variable;
}
// driver code
int main()
{
    base object1;
    anotherClass object2;
    object2.memberFunction(object1);

    return 0;
}
```

**Output**
```
Private Variable: 10
Protected Variable: 99
```
## Advantages of Friend Functions

- A friend function is able to access members without the need of inheriting the class.
- The friend function acts as a bridge between two classes by accessing their private data.
- It can be used to increase the versatility of overloaded operators.
- It can be declared either in the public or private or protected part of the class.
## Disadvantages of Friend Functions

- Friend functions have access to private members of a class from outside the class which violates the law of data hiding.
- Friend functions cannot do any run-time polymorphism in their members.