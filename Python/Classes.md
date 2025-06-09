- With classes you represents real-world things and situations, and you create *objects* bases on these classes.
- Making an object is called *instantiation* and you work with *instances* of a class. We can specify what type of information that can be stored in instances, and functions that can be used.
# Creating and Using Class

## Creating
Eg:
```python

class dog:
	
	def __init__(self, name, age):
		self.name = name
		self.age = age
	
	def set(self):
		print(f"{self.name} is now sitting.")
	
	def roll_over(self):
		print(f"{self.name} rolled over!")
```

### The \_\_init\_\_() Method
A function that is part of a class is a *method*. 
The `__init__()` method is a special method that  Python runs automatically whenever we create a new instance based on the `dog` class.The underscores help python differentiate it from our method names.(make sure to use two underscores on each side of `__init__()`
Python calls the `__init__()` method to create an instance. In our function it has three parameters: `self`, `name` and `age`. The `self` parameter is required in the method definition and it must come first before the other parameters. It must be included in the definition because when python calls this method later (to create an instance) the method call will automatically pass the self argument. We can think of the `__init__()` method as the definition of the instance and `self` as a keyword used to refer to the class-object in itself.

The lines `self.name = name` and `self.age = age` are used to give *attributes* to the class instance. Anything defined with prefix `self.` becomes an attribute.

## Making an instance from a class
```python
class dog:
	#code same as before
my_dog = dog('Willie', 6)

print(f"My dog's name is {my_dog.name}.")
print(f"My dog is {my_dog.age} years old.")
```

# Accessing attributes
```python
my_dog.name
```

# Calling methods
```python
my_dog.sit()
my_dog.roll_over()
```

# Setting default value for an attribute
```python
self.colour = 'black'
```

# Modifying Attributes
```python
my_dog.colour = 'brown' 
```
# Inheritance
If the class we are writing is a specialized version of another class you wrote, you can use *[[C++ OOPs#^6a3e81|inheritance]]*. When one class inherits from another, it takes on the attributes and methods of the first class.
The original class is called the *parent class* and the new class is the *child class*. The child can inherit any and all the attributes and methods of its parent class, but it's also free to define new attributes and methods of its own.

```python
class Car:
"""A simple attempt to represent a car."""
	def __init__(self, make, model, year):
		self.make = make
		self.model = model
		self.year = year
		self.odometer_reading = 0
	def get_descriptive_name(self):
		long_name = f"{self.year} {self.manufacturer} {self.model}"
		return long_name.title()
	
	def read_odometer(self):
		print(f"This car has {self.odometer_reading} miles on it.")
	
	def update_odometer(self, mileage):
		
		if mileage >= self.odometer_reading:
			self.odometer_reading = mileage
		
		else:
			print("You can't roll back an odometer!")
	
	def increment_odometer(self, miles):
		self.odometer_reading += miles

class ElectricCar(Car):
	"""Represent aspects of a car, specific to electric vehicles."""
	
	
	def __init__(self, make, model, year):
		"""Initialize attributes of the parent class."""
		super().__init__(make, model, year)


y my_tesla = ElectricCar('tesla', 'model s', 2019)
print(my_tesla.get_descriptive_name())
```

## The \_\_init\_\_ Method for a Child Class

When writing a child class we would call the `__init__()` method from the parent class. This will initialize any attributes that were defined in the parent `__int__()` method and make them available in the child class. This is similar to a [[C++ OOPs|constructor]] function. However, it is more accurate to call it the **Initializer method**.

Eg:
```python
class wild_dog(dog)
	def __init__(self, name, age, species):
		super().__init__(name, age)
```
The `super()` function is a special function that allows you to call a method from the parent class. This line tells python to call the `__init__()` method from `dog`  and which gives an `wild_dog` instance all the attributes defined in that method. 
The name *super* comes from a convention of calling the parent class a *superclass* and the child class a *subclass*.

# Overriding Methods from the parent class
We can override any method from the parent class that doesn't fit what you're trying to model. This can be done by defining a method in the child class with the same name as the method we are overriding that is in the parent class. 
For example, for the child-class `ElectricCar(Car)` the method `fill_gas_tank()` is illogical since electric cars don't have gas tanks.
We can override this by:
```python
class ElectricCar(Car):
	#code
	def fill_gas_tank(self):
		"""Electric cars don't have gas tanks."""
		print("This car doesn't need a gas tank!")
```

# Instances as Attributes
We can also combine a class with other classes.
For example:
```python
class Car:
	#code

class Battery:
	"""A simple attempt to model a battery for an electric car."""
	def __init__(self, battery_size=75):
		"""Initialize battery's attributes"""
		self.battery_size = battery_size
	def describe_battery(self):
		"""Print a statement describing a battery"""
		print(f"This car has a {self.battery_size}-kWh battery.")

class ElectricCar(Car):
	"""Represent aspects of a car, specific to electric vehicles."""
	def __init__(self,make,model,year):
		#code
		self.battery = Battery()
```

# Importing classes
Same way as [[Functions in python#^1aa8b1|functions]].

# Private vs Public vs Protected Attribute:
[[C++ OOPs|Encapsulation]] is a key principle of object oriented programming , allowing you to restrict access to certain attributes or methods within a class.
Private attributes are one way to implement encapsulation by making variables accessible only within the class itself.

``` python
class Student:
    __id = 1234
    def Print_id(self):
        print(f” student id is {self.__id}”)
```

## Public attribute:
These attributes can be accessed anywhere (inside/outside) the class, in subclasses, etc. 
```python
class Public:
	def __init__(self):
		self.name='AMAN'
	def display_name(self):
		print(self.name)
obj=Public()

obj1.display_name()
print(obj1.name())
```

## Private attribute
**Syntax:** `__variable`
Python performs name mangling to make it harder to accidentally override the member in subclasses. The name is rewritten as `_ClassName__variable`.

These attributes are still accessible, but require using the mangles name.
```python
class private:
	def __init__(self):
		self.__salary=40000 #Private variable 
	def display_name(self):
		print(self._salary) #Public method	

obj2 = private()
print(obj2.__salary) # Gives an error
obj2.display() # Does not return an error
```

**No True Privacy**: Python trusts developers to respect conventions. "Private" members are still accessible with effort.

**Best Practice:** Use public members unless you have a reason to restrict access. Avoid accessing "Private" members externally unless necessary.
## Protected attributes

**Syntax:** `_variable`

Signals that the member is meant for internal use within the class or its subclasses. However, Python **does not enforce** this-- it's a convention.
```Python
# Protected attribute

class Protected:
	def __init__(self):
		self._age=22 # Protected attribute

class subclass(Protected):
	def display_age(self):
		print(self._age) # Accessibility in subclass
```