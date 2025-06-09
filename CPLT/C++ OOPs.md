Conecepts of OOPs
![[OOPs diagram-1.excalidraw]]

**Object**: Any entity that has a state and behavior is known as an object. It is an active entity. It is an instance of a class. When a class is defined, no memory is allocated. But when it is initiated (class object is created), memory is allocated

**Class**: It is a collection of objects. It is a passive identity. It is a user defined data-type which has data members and member functions. ^60bda3
```
class_box
{
	Private:
		Data members
		int a,b,c;
	Public:
		Member functions
		
}b1,b2,b3
```

**Inheritance**: When one class accesses the property of another class, it is called inheritance.
![[OOPs diagram - 2.excalidraw]] ^6a3e81

**Syntax**
```
Class A
{

}

Class B: Public A
{

}
```
**Polymorphism**: When one task is performed by different ways, we call this property polymorphism.
For example: 
A person at the same time can have different characters like a Father, a husband, an employee. So the same person possesses different types of behaviors in different situations. This is called polymorphism
![[OOp diagram -3.excalidraw]]
**Abstraction**: Hiding internal details and showing functionality. For example in a phone call we don't know the internal processes involved in placing that call. In C++ we use abstract class and interface to achieve abstraction. ^049e21

**Encapsulation**: Binding or wrapping code and data together into a single unit. For example: a physical capsule is wrapped with different medicines.

**Dynamic Binding:** In dynamic binding a code could be executed in response to function call is decided at run-time. C++ has virtual functions to support this concept.

**Message Passing:** Objects communicate with one another by sending and receiving information to each other through message passing.
![[OOPs diagram -4.excalidraw]]

### Procedure oriented programming:
![[Opps diagram -5.excalidraw]]
Sub-routines/modulus/procedural

Examples of POP languages: 
C, Pascal, COBOL

### Object Oriented programming 
![[Oops diagram 6.excalidraw]]
## Data hiding
It is a technique that protects the internal details of an object by limiting access to it.
Data hiding has 3 access-specifiers.
**Public**,**Private** and **Protected**.


```
Class A
{
  Private:
     int var;
  Public:
     void takeinput():
     { 
       cin >> var;
     }
     void display ():
    {
       cout < var;
    }
     
}

main()
{
   A obj;
   obj.takeninput();
   obj.display();
}
```

Compile error if `obj.var = 5`
## Difference between POP and OOP

| POP                                                                                                                                                                                 | OOP                                                                                                                                                                                                  |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Programming method that uses step by step approach to break down a program. It focuses on functions required for computation rather than the data itself. Example: C, Pascal, COBOL | It can be defined as a programming model which is based upon the concept of objects. Objects contain data in the form of attributes and code in the form of methods. For example: C++, Java, Python. |
| It follows a top down approach                                                                                                                                                      | It follows a bottom up approach                                                                                                                                                                      |
| There is no access specifier in procedural programming                                                                                                                              | It has access specifiers like private, public and protected.                                                                                                                                         |
| Adding new data and functions is not easy                                                                                                                                           | Adding new data and functions is easy                                                                                                                                                                |
| Overloading is not possible                                                                                                                                                         | Overloading is possible                                                                                                                                                                              |
| There is no concept of data hiding and inheritance                                                                                                                                  | The concept of data hiding and inheritance is used                                                                                                                                                   |
| The function is more important than data                                                                                                                                            | Data is more important than function                                                                                                                                                                 |
| Based on unreal world                                                                                                                                                               | Based on real world                                                                                                                                                                                  |
| Used for designing medium sized programmes                                                                                                                                          | Used for designing large and complex programmes                                                                                                                                                      |
| Code reusability is absent                                                                                                                                                          | Code reusability is present                                                                                                                                                                          |
