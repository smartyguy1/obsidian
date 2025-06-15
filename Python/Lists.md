They are like [[Arrays|arrays in C]]. However Unlike them, python lists can store multiple different data types in one list.
Creation:
```python
bicycles = ['trek', 'cannondale', 'redline', 'specialized']
```
Accessing is done just like in C arrays:
```python
print(bicycles[0])
```
```
'trek'
```
We can also use various data-type specific methods on the list items:
```python
print(bicycles[0].title())
```
```
'Trek'
```

Using -ves we can index from the back:
```python
print(bicycles[-1])
```
```
'specialized'
```

# Modifying lists
Changing value similar to in C.
## Adding Elements
```python
motorcycles = ['honda', 'yamaha', 'suzuki']
```
### Appending
```python
motorcycles.append('ducati')
print(motorcycles)
```
```
motorcycles = ['honda', 'yamaha', 'suzuki', 'ducati']
```
We can also create an empty list and then `append()` items to it.

### Inserting
```python
motorcycles = ['honda', 'yamaha', 'suzuki']

motorcycles.insert(0, 'ducati')
print(motorcycles)
```
```
['ducati', 'honda', 'yamaha', 'suzuki']
```

## Removing Items:
### del
```python
motorcycles = ['honda', 'yamaha', 'suzuki']
del motorcycles[0]
print(motorcycles)
```
```
['yamaha', 'suzuki']
```

## pop()

Sometimes we want to use the value of an item before we delete it. `pop()` method removes the last item in a list but returns it before deleting it. 
```python
motor = ['honda', 'yamaha', 'suzuki']
popped_motor = motor.pop()
print(motor)
print(popped_motor)
```
```
['honda', 'yamaha']
'suzuki'
```

We can pop items from any position in a list
```python
motorcycles = ['honda', 'yamaha', 'suzuki']
first = motorcycles.pop(0)
```

## By value using remove()

```python
motor = ['honda', 'yamaha', 'suzuki', 'ducati']
motor.remove('ducati')
print(motor)
```
```
['honda', 'yamaha', 'suzuki']
```

# Organizing

## Sorting permanently using sort() method
It sorts strings in alphabetical order
```python
cars = ['bmw', 'audi', 'toyota', 'subaru']
cars.sort()
print(cars)
```
```
['audi', 'bmw', 'subaru', 'toyota']
```

sort in reverse:
```python
cars = ['bmw', 'audi', 'toyota', 'subaru']
cars.sort(reverse=True)
print(cars)
```
```
['toyota', 'subaru', 'bmw', 'audi']
```

## Sorting temporarily using sorted() function
```python
cars = ['bmw', 'audi', 'toyota', 'subaru']
print("Here is the original list:")
print(cars)
print("\nHere is the sorted list:")
print(sorted(cars))
print("\nHere is the original list again:")
print(cars)
```
```
Here is the original list:
['bmw', 'audi', 'toyota', 'subaru']
Here is the sorted list:
['audi', 'bmw', 'subaru', 'toyota']
Here is the original list again:
['bmw', 'audi', 'toyota', 'subaru']
```

## Reversing Order
```python
cars.reverse()
```
Reverses existing order

# Finding length
```python
len(cars)
```

# Using range() function
Gives a list with the given start-value, excluding end-value and difference. The default difference is 1.
```python 
numbers = list(range(1, 6))
print(numbers)
```
```
[1, 2, 3, 4, 5]
```

```python
even_numbers = list(range(2, 11, 2))
print(even_numbers)
```
```
[2, 4, 6, 8, 10]
```

# Simple Statistics
```python
>>> digits = [1, 2, 3, 4, 5, 6, 7, 8, 9, 0]
>>> min(digits)
0
>>> max(digits)
9
>>> sum(digits)
45
```

# List comprehensions
Allows to generate lists in only one line of code
```python
squares = [value**2 for value in range(1, 11)]
print(squares)
```
```
[1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
```

# Slicing
Python stops before the 2nd index you specify.
```python 
players = ['charles', 'martina', 'michael', 'florence', 'eli']
print(players[0:3])
```
```
['charles', 'martina', 'michael']
```

```python
players = ['charles', 'martina', 'michael', 'florence', 'eli']
print(players[1:4])
```
```
['martina', 'michael', 'florence']
```

If you omit the first index in a slice, Python automatically starts your
slice at the beginning of the list:
```python
players = ['charles', 'martina', 'michael', 'florence', 'eli']
print(players[:4])
```
```
['charles', 'martina', 'michael', 'florence']
```

# Copying a list
Unlike C-arrays, `=` sign doesn't just "assign" the value on the right to the one on the left. In python, if both sides are lists then both become connected, meaning changes in one lead to changes in the other.
So to transfer values without this happening:
```python
my_foods = ['pizza', 'falafel', 'carrot cake']
friend_foods = my_foods[:]
```

# Tuples

^afb9a0

Tuples look just like [[Lists]] except you use **parentheses** to define them. Although you can't modify a tuple, you can assign a new value to a variable representing a tuple.
```python
dimensions = (200, 50)
dimensions = (400, 100)
```

