Data Structures are a way of storing data. We structure data in different ways depending on what data we have and what we want to do with it.

C allows a way by which we can create our own [[Data Types and Variables|data-types]] or more precisely data structures via a `struct`. We could create a data-type that stores a person's name and phone number in the following way.

```C
#include <stdio.h>
#include <cs50.h>
#include <string.h>
//This creates a data type called person that can store strings name and number.
typedef struct
{
	string name;
	string number;
}
person;

int main(void)
{
	person people[3]; //this creates an array of data-type person
	
	people[0].name = "Carter";
	//this dot notation allows us to access the attributes of the data structure 
	people[0].number = "+1-617-495-1000";
	// this stores the the name and number into an element of array 'people'
	// of data type person
	
}```
