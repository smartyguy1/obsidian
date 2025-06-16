Like the [[CS50/Week 5 (Data Structures)/Queues|Queue]] [[CS50/Week 5 (Data Structures)/Data Structures|Data Structure in CS50]]: ![[CS50/Week 5 (Data Structures)/Queues|Queues]]
# Implementation in python

### Using [[Classes|Class]] 
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
