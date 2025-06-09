### **Operator Overloading in C++**

Operator overloading allows C++ operators to be redefined and customized for **user-defined types** (classes or structs). It enables objects to use standard operators like `+`, `-`, `<`, `==`, etc., just like built-in data types (int, float, etc.).

---

## **1. Why Use Operator Overloading?**

By default, C++ does not know how to apply operators to **custom objects**.  
For example, consider this class:

```cpp
class Point {
public:
    int x, y;
};
```

If you try:

```cpp
Point p1, p2, p3;
p3 = p1 + p2;  // ERROR: No overloaded operator+ for class Point
```

C++ does not know how to add two `Point` objects. To make this work, we must **overload** the `+` operator.

---

## **2. Syntax of Operator Overloading**

```cpp
return_type operator<symbol>(parameters) {
    // Implementation
}
```

- **return_type** → The type of value returned (often the same class type).
- **operator** → Specifies which operator to overload.
- **parameters** → Usually another object of the same class.
- **Implementation** → Defines the behavior.

---

## **3. Example: Overloading `+` Operator**

```cpp
#include <iostream>

class Point {
public:
    int x, y;

    // Constructor
    Point(int xVal, int yVal) : x(xVal), y(yVal) {}

    // Overloading + operator
    Point operator+(const Point& rhs) const {
        return Point(x + rhs.x, y + rhs.y); 
    }

    // Display function
    void display() {
        std::cout << "(" << x << ", " << y << ")\n";
    }
};

int main() {
    Point p1(3, 4), p2(1, 2);
    Point p3 = p1 + p2; // Calls overloaded + operator
    p3.display(); // Output: (4, 6)
}
```

### **Explanation:**

1. The function `operator+` takes another `Point` object as input.
2. It **returns a new `Point` object** whose `x` and `y` values are the sum of both `Point` objects.
3. This allows `p1 + p2` to work **just like integer addition**.

---

## **4. Overloading Comparison Operators (`<`, `>`, `==`)**

### **Example: Overloading `<` Operator**

```cpp
class Foo {
public:
    int x;
    Foo(int val) : x(val) {}

    // Overloading < operator
    bool operator<(const Foo& rhs) const {
        return x < rhs.x;
    }
};

int main() {
    Foo a(10), b(20);
    if (a < b) // Calls overloaded < operator
        std::cout << "a is smaller than b\n";
}
```

- **`const` at the end** ensures the function does **not modify** the object.
- **`const` in the parameter** ensures `rhs` is read-only.

---

## **5. Overloading `<<` (for `cout`)**

```cpp
#include <iostream>
class Point {
public:
    int x, y;
    Point(int a, int b) : x(a), y(b) {}

    // Overloading << operator
    friend std::ostream& operator<<(std::ostream& os, const Point& p) {
        os << "(" << p.x << ", " << p.y << ")";
        return os;
    }
};

int main() {
    Point p(5, 8);
    std::cout << p; // Calls overloaded << operator
}
```

- We use `friend` so that `operator<<` can access private members.
- `std::ostream&` is used for `cout` functionality.

---

## **6. Overloading `[]` (Indexing Operator)**

```cpp
class Array {
private:
    int arr[10];

public:
    int& operator[](int index) { return arr[index]; }
};

int main() {
    Array a;
    a[0] = 100;  // Works like an array
    std::cout << a[0]; // Output: 100
}
```

---

# 7. Overloading Unary Operator


##  Basic Syntax for Unary Overload

```cpp
class Type {
public:
    // Prefix form (++obj, --obj, etc.)
    Type& operator++();         // prefix increment
    Type& operator--();         // prefix decrement

    // Postfix form (obj++, obj--); dummy int parameter
    Type operator++(int);       // postfix increment
    Type operator--(int);       // postfix decrement

    // Other unary operators
    bool operator!() const;     // logical NOT
    Type operator-() const;     // unary minus
    Type operator+() const;     // unary plus
};
```

- **Member functions** are preferred for unary operators (they already have one operand: `*this`).
    
- **Return type**:
    
    - Prefix: usually `Type&` (modify and return self).
        
    - Postfix: return **old** value, so typically `Type` by value.
        

---

##  Prefix vs Postfix Example

```cpp
class Counter {
    int value;
public:
    Counter(int v = 0) : value(v) {}

    // Prefix ++
    Counter& operator++() {       // ++obj
        ++value;
        return *this;
    }

    // Postfix ++
    Counter operator++(int) {     // obj++
        Counter temp(*this);      // copy old state
        ++value;
        return temp;              // return old state
    }
};
```

---

##  Overloading Other Unary Operators

| Operator | Typical Use             | Example Overload             |
| -------- | ----------------------- | ---------------------------- |
| `-`      | Arithmetic negation     | `Complex operator-() const;` |
| `!`      | Logical NOT/empty check | `bool operator!() const;`    |
| `*`      | Dereference‑like access | `Element& operator*();`      |
| `&`      | Address‑like access     | `Pointer operator&();`       |
| `~`      | Bitwise complement      | `Bitset operator~() const;`  |
 

---

##  Const Correctness Example

```cpp
class Vector2D {
    double x, y;
public:
    Vector2D(double x_=0, double y_=0): x(x_), y(y_) {}
    // Non‑modifying unary minus
    Vector2D operator-() const {
        return Vector2D(-x, -y);
    }
};
```

---

##  Friend vs Member for Unary

- **Unary operators** almost always implemented as **member** functions—friend not needed.
    
- Use **friend** only if the operator needs access to private members **and** must be non‑member (rare for unary).
    

---

##  Quick Checklist

-  Decide prefix or postfix? Implement both if needed.
    
-  Correct return type (`Type&` vs `Type`).
    
-  Use dummy `int` for postfix signature.
    
-  Maintain intuitive behavior.
    
-  Add `const` where appropriate.
    

---
## **8. Rules for Operator Overloading**

✅ **Allowed to Overload**

- Arithmetic: `+`, `-`, `*`, `/`, `%`
- Comparison: `==`, `!=`, `<`, `>`, `<=`, `>=`
- Bitwise: `&`, `|`, `^`, `~`, `<<`, `>>`
- Assignment: `=`, `+=`, `-=`, etc.
- Others: `[]`, `()`, `->`, `<<`, `>>`

❌ **Cannot Overload**

- Scope resolution `::`
- Member access `.`
- Pointer-to-member `.*`
- `sizeof`
- `typeid`
- `new` and `delete` (though `operator new` and `operator delete` can be overloaded)

---

## **9. Summary**

- Operator overloading **makes custom objects behave like built-in types**.
- Use `const` for **read-only functions**.
- `friend` functions are used when the operator needs **access to private members**.
- Cannot change **operator precedence** or **associativity**.
