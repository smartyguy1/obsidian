Can be defined by 
```python
def greet_user():
	print("Hello!")

greet_user()
```
# Arguments and parameters:
```python
def greet_user(name):
	print(f"Hello,{name.title()}!")
greet_user('bhanu')
```
`name` here is the parameter; a piece of information that function needs to do it's job. The value `'bhanu'` is the argument; a piece of information that's passed from a function call to a function. 
*Sometimes they are used interchangeably*
# keyword arguments
```python
def describe_pet(animal_type, pet_name):
"""Display information about a pet."""
print(f"\nI have a {animal_type}.")
print(f"My {animal_type}'s name is {pet_name.title()}.")
describe_pet(animal_type='hamster', pet_name='harry')
```

## Default Values
*We can define a default value for each parameter in case no argument is passed for it*
```python
def describe_pet(pet_name, animal_type = 'dog'):
#code....

describe_pet(pet_name = 'willie')
```

# Return Values
We can also use functions to return us specific values.
using `return value`

# Optional Argument
We can declare optional arguments by giving them optional default values.
```python
def get_name(f_name, l_name, m_name = ''):
	
	if middle_name:
		full_name = f"{f_name} {m_name} {l_name}"
	else:
		full_name = f"{f_name} {l_name}"
	return full_name.title()
```

# Passing arbitrary number of arguments
We can write the parameter as `*parameter` this parameter will then take as many value as passed. `*toppings` causes python to create an empty list `toppings` and pack into it all the values that are passed. 
```python
def make_pizza(*toppings):
	print(toppings)
make_pizza('pepperoni')
make_pizza('mushrooms', 'green peppers', 'extra cheese')
```

## Mixing Positional and Arbitrary
We can mix positional and arbitrary arguments together by putting the positional parameter first in the function definition, this way the first parameter gets recognized as that one and the rest go to the positional parameter:
```python
def make_pizza(size, *toppings):
	print(f"\nMake {size}-inch pizza with the following toppings: ")
	for topping in toppings:
		print(f"-{toppings}")

make_pizza(16, 'pepperoni')
make_pizza(12, 'mushrooms', 'green peppers', 'extra cheese')
```

# Using Keyword Argument
Sometimes you'll want to accept an arbitrary number of arguments, but you won't know ahead of time what kind of information will be passed to the function. In this case, you can write functions that accept as many key-value pairs as the calling statement provides.
Example:
```python
def build_profile(f_name, l_name, **user_info):
	user_info['first_name'] = f_name
	user_info['last_name'] = l_name
	return user_info

user_profile = build_profile('albert', 'einstein', location = 'princeton', field = 'physics')
```
`**user_info` causes python to create an empty dictionary called user_info and pack whatever name-value pairs it receives into that dictionary.
This gives a dictionay:
```
{'location': 'princeton', 'field': 'physics',
'first_name': 'albert', 'last_name': 'einstein'}
```
# Modules

## Importing a module

^1aa8b1

```python
import module_name
#or
import module_name as mn
```
## Importing Specific Functions
```python
from modul_name import function_name
#or
from module_name import function_name as new_name
```

## Importing all functions in module
```python
from module_name import *
```
