# Iterators

An Iterator is an object with a state so that it knows where it is during iteration. It generates a countable number of values and it is used to iterate over objects like [[Lists|lists]], [[Lists#^afb9a0|tuples]], sets, etc. 

- Iterators are implemented using a [[Classes|class]] since they are objects and a local variable.
- It follows lazy evaluation where the evaluation of the expression will be on hold and stored in the memory until the item is called specifically.(This helps avoid repeated evaluation)
- It requires only 1 memory location to process the value.

The implementation of each iterator object must consist of an `__iter__()` and `__next__()` method. The implementation must also have a way to track the object's internal state and raise a `StopIteration` exception once no more values can be returned. These rules are known as **iterator protocol**.

## Iterables
Iterables are objects capable of returning their members one at a time -- they can be iterate over. Popular built-in Python data structures such as [[Lists|lists]], [[Lists#^afb9a0|tuples]], and sets qualify as iterables.

Other data structures like strings and dictionaries are also considered iterables.

However, not every iterable is an iterator. An iterable produces an iterator only once it is iterated on. For lists we can do this by using the built-in `iter()` function.
```python
list_instance = [1, 2, 3, 4]
print(iter(list_instance))

"""
<list_iterator object at 0x7fd946309e90>
"""
```

### The lazy nature of iterators
It is possible to define multiple iterators based on the same iterable object. Each iterator will maintain its own state of progress.
```python
list_instance = [1,2,3,4]
iterator_a = iter(list_instance)
iterator_b = iter(list_instance)
print(f"A: {next(iterator_a)}")
print(f"A: {next(iterator_a)}")
print(f"A: {next(iterator_a)}")
print(f"A: {next(iterator_a)}")
print(f"B: {next(iterator_b)}")
"""
A: 1
A: 2
A: 3
A: 4
B: 1
"""
```

# Generators

Implementing your own iterator is a drawn-out process, and it is only sometimes necessary. A simpler alternative is to use a generator object. Generators are a special type of function that use the `yield` keyword to return an iterator that may be iterated over, one value at a time. 

To create a generator to find all of the factors for a positive integer:
```python
def factors(n):
for val in range(1,n+1):
	if n%val == 0:
		yield val
print(factors(20))
""" <generator object factors at 0x7fd938271350> """
```
Since we used the `yield` keyword instead of `return`, the function is not exited after the run. In essence, we told python to create a generator object instead of a traditional function, which enables the state of the generator object to be tracked. So, we can use the `next()` function on the lazy iterator to show the elements of the series one at a time.

Another way is to create a generator is with a generator comprehension.
```python
print((vak for val in range(1,n+1) if n%val == 0))
""" <generator object <genexpr> at 0x7fd940c31e50> """
```

## The `yield` keyword
The `yield` keyword controls the flow of a generator function. Instead of exiting the function as seen when `return` is used, the `yield` keyword returns the function but remembers the state of its local variables.

The generator returned from the `yield` call can be assigned to a variable and iterated upon with the `next()` keyword – this will execute the function up to the first `yield` keyword it encounters. Once the `yield` keyword is hit, the execution of the function is suspended. When this occurs, the function's state is saved. Thus, it is possible for us to resume the function execution at our own will.

```python
def yield_multiple_statments():
  yield "This is the first statment"
  yield "This is the second statement"  
  yield "This is the third statement"
  yield "This is the last statement. Don't call next again!"
example = yield_multiple_statments()
print(next(example))
print(next(example))
print(next(example))
print(next(example))
print(next(example))
"""
This is the first statment
This is the second statement
This is the third statement
This is the last statement. Don't call next again!
--------------------------------------------------------------------
StopIteration                  Traceback (most recent call last)
<ipython-input-25-4aaf9c871f91> in <module>()
    11 print(next(example))
    12 print(next(example))
---> 13 print(next(example))
StopIteration:
"""
```
