Virtual base classes are used in virtual inheritance as a way of preventing multiple “instances” of a given class appearing in an inheritance hierarchy when using multiple inheritances.

## Why?
![[Pasted image 20250424223847.png| 300]]

**Example:**
```c++
#include <iostream> 
using namespace std; 

class A { 
public: 
	void show() 
	{ 
		cout << "Hello from A \n"; 
	} 
}; 

class B : public A { 
}; 

class C : public A { 
}; 

class D : public B, public C { 
}; 

int main() 
{ 
	D object; 
	object.show(); 
}
```
**Output:**
```
prog.cpp: In function 'int main()':  
prog.cpp:29:9: error: request for member 'show' is ambiguous  
  object.show();  
         ^  
prog.cpp:8:8: note: candidates are: void A::show()  
   void show()  
        ^  
prog.cpp:8:8: note:                 void A::show()
```

### How to resolve this issue?   
To resolve this ambiguity when class ****A**** is inherited in both class ****B**** and class ****C****, it is declared as ****virtual base class**** by placing a keyword ****virtual**** as :

```
Syntax 1:  

class B : virtual public A   
{  
};  

Syntax 2:  

class C : public virtual A  
{  
};
```

