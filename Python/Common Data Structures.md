# [[Stacks]] in  python: 

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

## Class based implementation
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

# [[Queues]] in Python

## Implementation in Class:
```python
class Queue:
	def __init__(self):
		self.queue = []
	def dequeue(self):
		if self.IsEmpty():
			return "Queue is empty"
		return self.queue.pop(0)
	def enqueue(self, element):
		self.queue.append(element)
	def IsEmpty(self):
		return len(self.queue) == 0
	def peek(self):
		if self.IsEmpty():
			return "Queue is empty"
		return self.queue[0]
```

# [[Linked lists]] in python

```python
class Node:
	def __init__(self, data):
		self.data = data
		self.next = None

class Linked_list:
	def __init__(self, head):
		self.head = Node(head)
		
	def insert_next(self, data):
	# Insert next element in the list
		last_element = self.get_last()
		last_element.next = Node(data)
	
	def get_last(self):
	# Get the last added element
		temp = self.head
		while temp.next is not None:
			temp = temp.next
		return temp
	
	def remove_first(head):
	# Remove the first elememt in the list
		if not head:
			return None
		head=head.next
		return head
	
	def traverse_print(self):
	# Traverse the list and print its values
		currentNode=self.head
		while currentNode:
			print(currentNode.data, end="-->")
			currentNode = currentNode.next
		print("None")
	
	def remove_last(self):
	# Remove the last added element
		if head is None:
			return None
		if head.next is None:
			head = None
			return None
		second_last = head
		while second_last.next.next:
			second_last = second_last.next
		second_last.next = None
		return second_last
		
	def insert_at_position(self, pos, data):
	# Insert data at given position
		value = Node(data)
		counter = 0
		preceding_node = self.head
		while counter < pos:
			preceding_node = preceding_node.next
			if preceding_node.next is None:
				return "Index out of range"
		value.next = preceding_node.next
		preceding_node.next = value
		traverse_print()
```

