A constructor is a member function that is executed automatically whenever an object is created. (The term *constructor* is sometimes abbreviated *ctor*, especially in comments in program listings.)

In C++, **constructors** are special member functions of a class that are **automatically called when an object of the class is created**. They are mainly used to **initialize objects**.

They are similar to `__init__()` method in [[Classes|python classes]] 

---

### 🔧 What is a Constructor?

A constructor has the **same name as the class** and **no return type** (not even `void`).

### 🔄 Purpose of a Constructor:

- Initialize class members when an object is created.
    
- Can set default values.
    
- Can perform any setup steps needed when the object is created.
    

---

### 🛠️ Example:

```cpp
#include <iostream>
using namespace std;

class Car {
public:
    string brand;
    int year;

    // Constructor
    Car(string b, int y) {
        brand = b;
        year = y;
    }

    void display() {
        cout << "Brand: " << brand << ", Year: " << year << endl;
    }
};

int main() {
    Car myCar("Toyota", 2020); // Constructor is called here
    myCar.display();
    return 0;
}
```

---

### 🧰 Types of Constructors:

1. **Default Constructor**
	A [default constructor](https://www.geeksforgeeks.org/default-constructors-in-cpp/) is a constructor that doesn’t take any argument. It has no parameters. It is also called a zero-argument constructor. The compiler automatically creates an implicit default constructor if the programmer does not define one.
	
	If you define **any constructor**, the default one is not provided unless you explicitly define it.
	
    ```cpp
    Car() {
        brand = "Unknown";
        year = 0;
    }
    ```
    
2. **Parameterized Constructor** :
	Parameterized constructors make it possible to pass arguments to constructors. Typically, these arguments help initialize an object when it is created. To create a [parameterized constructor](https://www.geeksforgeeks.org/parameterized-constructor-in-cpp/), simply add parameters to it the way you would to any other function.
    
3. **Copy Constructor**
	A [copy constructor](https://www.geeksforgeeks.org/copy-constructor-in-cpp/) is a member function that initializes an object using another object of the same class. Copy constructor takes a reference to an object of the same class as an argument.
    
    ```cpp
    Car(const Car &obj) {
        brand = obj.brand;
        year = obj.year;
    }
    ```
4. **Move Constructor**:
	The [move constructor](https://www.geeksforgeeks.org/move-constructors-in-c-with-examples/) is a recent addition to the family of constructors in C++. It is like a copy constructor that constructs the object from the already existing objects., but instead of copying the object in the new memory, it makes use of move semantics to transfer the ownership of the already created object to the new object without creating extra copies.

---

### 🚨 Notes:

- If you don’t define any constructor, C++ automatically provides a **default constructor**.
    
- If you define **any constructor**, the default one is not provided unless you explicitly define it.
