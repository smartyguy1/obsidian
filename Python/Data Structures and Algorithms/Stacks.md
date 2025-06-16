Just like the [[CS50/Week 5 (Data Structures)/Stacks|Stacks]] in [[CS50/Week 5 (Data Structures)/Data Structures|CS50]]
![[CS50/Week 5 (Data Structures)/Stacks|Stacks]]
## List based implementation
```python
stack_fruits = []
#Puch
stack_fruits.append("Apple")
stack_fruits.append("Bananna")
stack_fruits.append("Orange")

#pop
element = stack_fruits.pop()
print("Pop", element)
print("Fruits Stack:", stack_fruits)

#Peak
topelement = stack_fruits[-1]
print(topelement)

#Is Empty
isempty = (len(stack_fruits)) == 0
if isempty:
	print("The list is empty")
else:
	print("The list is not empty")
```

## [[Classes|Class]] based implementation
```python
class Stack:
	def __init__(self):
		self.stack_fruits = []
	def push(self, element):
		self.stack_fruits.append(element)
	def pop(self):
		if self.IsEmpty():
			return "Stack is empty"
		return self.stack_fruits.pop()
	def peek(self):
		if self.IsEmpty():
			return "Stack is empty"
		return self.stack_fruits[-1]
	def IsEmpty(self):
		return len(self.stack_fruits) == 0
```
