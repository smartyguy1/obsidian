Static data members are class members that are declared using `static` keywords. A static member has certain special characteristics which are as follows:

- Only one copy of that member is created for the entire class and is shared by **all** the objects of that class, no matter how many objects are created.
- It is initialized before any object of this class is created, even before the main starts outside the class itself.
- It is visible, i.e. can be controlled with the class access specifiers
- Its lifetime is the entire program.
- A static data member can only be initialized outside the class definition.

Static data members are useful for maintaining data shared among all instances of a class.

```c++
// C++ Program to demonstrate
// the working of static data member
#include <iostream>
using namespace std;

// creating a dummy class to define the static data member
// it will inform when its type of the object will be
// created
class stMember {
public:
    int val;
    // constructor to inform when the instance is created
    stMember(int v = 10): val(v) {
        cout << "Static Object Created" << endl;
    }
};

// creating a demo class with static data member of type
// stMember
class A {
public:
    // static data member
    static stMember s;
    A() { cout << "A's Constructor Called " << endl; }
};

stMember A::s = stMember(11);

// Driver code
int main()
{

    // Statement 1: accessing static member without creating
    // the object
    cout << "accessing static member without creating the "
            "object: ";
    // this verifies the independency of the static data
    // member from the instances
    cout << A::s.val << endl;
    cout << endl;

    // Statement 2: Creating a single object to verify if
    // the seperate instance will be created for each object
    cout << "Creating object now: ";
    A obj1;
    cout << endl;

    // Statement 3: Creating multiple objects to verify that
    // each object will refer the same static member
    cout << "Creating object now: ";
    A obj2;
    cout << "Printing values from each object and classname"
         << endl;

    cout << "obj1.s.val: " << obj1.s.val << endl;
    cout << "obj2.s.val: " << obj2.s.val << endl;
    cout << "A::s.val: " << A::s.val << endl;

    return 0;
}

```

### `static` vs `const` data members in C++

_(and what happens when you combine them)_

| Aspect                          | `static` data member                                                                                                                                                              | `const` (non‑static) data member                                                                              |
| ------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- |
| **Lifetime / storage**          | Exactly **one** copy shared by _all_ objects of the class; exists for the entire program run.                                                                                     | Each **object** gets its own separate copy; created and destroyed with that object.                           |
| **Access syntax**               | Prefer `ClassName::member`, but can also use `obj.member`.                                                                                                                        | Always through an object (except when using pointers‑to‑member).                                              |
| **Initialization location**     | ‑ If integral or `enum` type ⇒ can be initialized **inside the class** (`inline`) since C++17.‑ Otherwise provide a **definition** in a .cpp file or use `inline static` (C++17). | Must use **constructor initializer list** (or in‑class brace initialization since C++11).                     |
| **Mutability**                  | Mutable by default (unless also `const`). Same value for everyone unless you change it.                                                                                           | Value fixed **per object** at construction; cannot change after that.                                         |
| **Typical roles**               | • Counters, shared configuration• Lookup tables• Class‑wide constants (`inline static const`)                                                                                     | • Immutable per‑object data (ID, creation timestamp)• Compile‑time literals used by templates/metaprogramming |
| **Memory footprint per object** | **0 bytes** per object (only one global copy).                                                                                                                                    | Costs **size of the member** inside every object.                                                             |

---

#### Code snapshots

```cpp
class Widget {
public:
    // 1. shared across all Widgets
    inline static int totalCreated = 0;      // C++17 one‑liner

    // 2. constant per Widget
    const int id;                            // has to be set in ctor

    Widget() : id(++totalCreated) {}         // id fixed per object
};
```

- `Widget::totalCreated` lives once; every constructor call increments it.
    
- `id` is `const` for each instance—once assigned, it never changes.
    

---

#### `static const` together

```cpp
class Math {
public:
    static const double pi;          // declaration
};
inline const double Math::pi = 3.141592653589793;   // definition
```

- **`static const`** gives one read‑only copy shared by all.
    
- For _integral_ or `enum` types you can even write:
    
    ```cpp
    static const int answer = 42;   // no separate definition needed
    ```
    
    and use `answer` in `case` labels or template parameters.
    

---

### Quick decision guide 🧭

|Need|Use|
|---|---|
|Same value for every instance & maybe modifiable|`static`|
|Same value for every instance & immutable|`static const` or `inline static const` (since C++17)|
|Different value per instance that never changes after construction|`const`|
|Different value per instance that can change|(plain) non‑static, non‑const|

---

**Remember**:

- `static` affects **how many copies exist** and where they live.
    
- `const` affects **whether the value can change** after it’s set.  
    Combine them to suit your design—`static` for sharing, `const` for immutability.