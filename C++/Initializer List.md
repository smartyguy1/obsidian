A constructor initializer list in C++ is a special syntax used to initialize member variables of a class before the body of the constructor is executed. It is specified after the constructor's parameter list and before the opening curly brace of the constructor body, using a colon followed by a comma-separated list of initializations.
Syntax:
```c++
  ClassName(parameters) : member1(value1), member2(value2) {

      // Constructor body

  }
```

 

# Benefits:
- Ensures efficient initialization of class members, especially for const or reference members, which must be initialized at the time of their creation.
- Avoids unnecessary default construction and reassignment for members.
- Allows initialization of base class constructors in derived classes.

 
Example:
```c++

  class Example {

      int x;

      const int y;

  public:

      Example(int a, int b) : x(a), y(b) {

          // Constructor body

      }

  };

```