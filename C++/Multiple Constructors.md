In C++, We can have more than one constructor in a class with same name, as long as each has a different list of arguments. This concept is known as **Constructor Overloading** and is quite similar to function overloading.

- Overloaded constructors essentially have the same name (exact name of the class) and are different by the number and type of arguments.
- A constructor is called depending upon the number and type of arguments passed.
- While creating the object, arguments must be passed to let compiler know, which constructor needs to be called.

```C++
#include <iostream>
usng namespace std;

class construct
{
public:
	float area;

	contruct(){
		area=0;
	}

	construct(int a, int b){
		area = a*b;
	}

	void disp(){
		cout<< area << endl;
	}
};

int main(){
	construct o;
	construct o2(10,20);

	o.disp();
	o2.disp();
	return 0;
}
```
