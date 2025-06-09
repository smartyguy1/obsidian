# Constructor Overloading

C++ provides us the provision using which we can incorporate more than one constructor in a single program. But these constructors must have different types of arguments/ no. of arguments. This is called **Constructor Overloading**.

```C++
class demo
{
	int a;
	public:
	demo()
	{
		a = 10;
	}
	demo(int x){
		a-x;
	}
	demo(demo&z){
		a=a*z;
	}
	void putdata(){
		cout << "a= "<< a;
	}
};

int main(){
	demo aa;
	demo bb(20);
	demo cc(aa);
	aa.putdata();
	bb.putdata();
	cc.putdata();
}
```

## What is the difference between constructor and destructor 

| Constructor                        | Destructor                                               |
| ---------------------------------- | -------------------------------------------------------- |
| Value construct                    | Destroy Class Object                                     |
| Has Argumentd                      | No Arguments                                             |
| No Return Type                     | No Return Type                                           |
| It's name is similar to Class Name | The is similar to class name preceeded by tiled sign(\~) |
```C++
A()
{
	A(){
	
	}
	~A(){
	}
}
```
Like constructors, destructors are also member functions whose name is similar to the class name having `~` sign just before it's name. Destructor is used to destroy object once the object goes out of scope.
Destructor has no data type not any arguemnt

Which is a type of polymorphism. Using the concept of operator overloading we can overload any operator.i.e. we can assign a new definition to our existing operator

Some operators are there which can't be operated

1. scope resolution 