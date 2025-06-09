The capability of a class to derive properties and characteristics from another class is called [[C++ OOPs#^6a3e81|inheritance]]. 

**Syntax:**
```
class DerivedClass : mode_of_inheritance BaseClass {
	// Body of the derived class
};
```
where mode of inheritance controls the access level of the inherited members of the base class in the derived class.

### 3 Modes of Inheritance

| Mode                           | Description                                                                                                                                                                                 |
| ------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Public Inheritance Mode**    | Public member of the base class will become public in the derived class and protected members of the base class will become protected in the derived class.                                 |
| **Protected Inheritance Mode** | Both public and protected members of the base class will become protected in the derived class.                                                                                             |
| **Private Inheritance Mode**   | Both public members and protected members of the base class will become private in the derived class. Private mode is the ***default mode** that is applied when we don’t specify any mode. |

# Types Of Inheritance in C++

The inheritance can be classified on the basis of the relationship between the derived class and the base class. In C++, we have ***5 types of inheritances:***

- Single inheritance
- Multilevel inheritance
- Multiple inheritance
- Hierarchical inheritance
- Hybrid inheritance

### 1. Single Inheritance
In single inheritance, a class is allowed to inherit from only one class. i.e. one base class is inherited by one derived class only.
![[Pasted image 20250424221621.png]]

**Example:**
```c++
#include <bits/stdc++.h>
using namespace std;

class Vehicle {
public:
    Vehicle() {
        cout << "This is a Vehicle"<< endl;
    }
};
// Sub class derived from a single base classes
class Car : public Vehicle {
public:
    Car() {
        cout << "This Vehicle is Car"<< endl;
    }
};
int main() {
    
    // Creating object of sub class will
    // invoke the constructor of base classes
    Car obj;
    return 0;
}

```
**Output**

```
This is a Vehicle
This Vehicle is Car
```
### 2. Multiple Inheritance 
Multiple Inheritance is a feature of C++ where a class can inherit from more than one class i.e. one subclass is inherited from more than one **base class**.
![[Pasted image 20250424221924.png]]

```c++
#include <bits/stdc++.h>
using namespace std;

class LandVehicle {
public:
    LandVehicle() {
        cout << "This is a LandVehicle"<< endl;
    }
};

class WaterVehicle {
public:
    WaterVehicle() {
        cout << "This is a WaterVehicle"<< endl;
    }
};

// sub class derived from two base classes
class AmphibiousVehicle : public WaterVehicle, public LandVehicle {
  public:
    AmphibiousVehicle() {
        cout << "This is an AmphibiousVehicle"<< endl;
    }
};

int main() {
    
    // Creating object of sub class will
    // invoke the constructor of base classes.
    AmphibiousVehicle obj;
    return 0;
}
```

### 3. Multilevel Inheritance
In [multilevel inheritance](https://www.geeksforgeeks.org/cpp-multilevel-inheritance/), a derived class is created from another derived class and that derived class can be derived from a base class or any other derived class. There can be any number of levels.

![[Pasted image 20250425095011.jpg]]


**Example:**
```c++
#include <bits/stdc++.h>
using namespace std;

class Vehicle {
public:
    Vehicle() {
        cout << "This is a Vehicle"<< endl;
    }
};

class fourWheeler : public Vehicle {
public:
    fourWheeler() {
        cout << "4 Wheeler Vehicles"<< endl;
    }
};

class Car : public fourWheeler {
public:
    Car() {
        cout << "This 4 Wheeler Vehical is a Car";
    }
};

int main() {
    
    // Creating object of sub class will
    // invoke the constructor of base classes.
    Car obj;
    return 0;
}
```

**Output:**
```
This is a Vehicle
4 Wheeler Vehicles
This 4 Wheeler Vehical is a Car
```

### 4. Hierarchical Inheritance
In [hierarchical inheritance](https://www.geeksforgeeks.org/cpp-hierarchical-inheritance/), more than one subclass is inherited from a single base class. i.e. more than one derived class is created from a single base class.
![[Pasted image 20250424222346.png]]

**Example:**
```c++
#include <bits/stdc++.h>
using namespace std;

class Vehicle {
public:
    Vehicle() {
        cout << "This is a Vehicle"<< endl;
    }
};

class Car : public Vehicle {
public:
    Car() {
        cout << "This Vehicle is Car"<< endl;
    }
};

class Bus : public Vehicle {
public:
    Bus() {
        cout << "This Vehicle is Bus"<< endl;
    }
};

int main() {
    
    // Creating object of sub class will
    // invoke the constructor of base class.
    Car obj1;
    Bus obj2;
    return 0;
}
```

**Output:**
```
This is a Vehicle
This Vehicle is Car
This is a Vehicle
This Vehicle is Bus
```

### 5. Hybrid Inheritance
[Hybrid Inheritance](https://www.geeksforgeeks.org/hybrid-inheritance-in-cpp/) is implemented by combining more than one type of inheritance. For example: Combining Hierarchical inheritance and Multiple Inheritance will create hybrid inheritance in C++.
![[Pasted image 20250424222503.png]]
```c++
#include <bits/stdc++.h>
using namespace std;

class Vehicle {
public:
    Vehicle() {
        cout << "This is a Vehicle"<< endl;
    }
};

class Fare {
public:
    Fare() {
        cout << "Fare of Vehicle"<< endl;
    }
};

class Car : public Vehicle {
  public:
  Car() {
      cout << "This Vehical is a Car"<< endl;
  }
};

class Bus : public Vehicle, public Fare {
  public:
  Bus() {
      cout << "This Vehicle is a Bus with Fare";
  }
};

int main() {
    
    // Creating object of sub class will
    // invoke the constructor of base class.
    Bus obj2;
    return 0;
}

```

**Output:**
```
This is a Vehicle
Fare of Vehicle
This Vehicle is a Bus with Fare
```
