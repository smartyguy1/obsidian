Discussed in CS50 using C: ![[CS50/Week 5 (Data Structures)/Linked lists|Linked lists]]
# Python Implementation of singly linked list:
```python
# This program is a python implementation of a singly linked list

class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

class linked_list:
    def __init__(self, start=None):
        self.start = Node(start) 
    
    def insert_start(self, new):
        new = Node(new)
        new.next = self.start
        self.start = new
    
    def insert_end(self, new):
        new = Node(new)
        if self.start is None:
            self.start = new
            return
        
        temp = self.start
        while(temp.next is not None):
            temp = temp.next
        temp.next = new
    
    def remove_start(self):
        temp = self.start
        self.start = self.start.next
        temp = None

    def remove_end(self):
        temp = self.start
        while(temp.next.next is not None):
            temp = temp.next
        temp.next = None

    def traverse_print(self):
        temp = self.start
        while(temp is not None):
            print(temp.data, end='--->')
            temp = temp.next
        print("None")
    
    def get_from_pos(self, pos:int):
        temp = self.start
        temp_pos = 0
        while(temp is not None):
            if temp_pos == pos:
                return temp
            temp = temp.next
            temp_pos += 1
            
        raise IndexError("Index is out of range")
    def delete_from_pos(self, pos:int):
        temp = self.get_from_pos(pos-1)
        temp.next = None

lls1 = linked_list(1)
lls1.insert_end(2)
lls1.traverse_print()
lls1.insert_end(3)
lls1.insert_end(4)
lls1.traverse_print()
lls1.remove_end()
lls1.traverse_print()
lls1.remove_start()
lls1.traverse_print()
lls1.insert_start(0)
lls1.traverse_print()
print(lls1.get_from_pos(1).data)
print(lls1.get_from_pos(2).data)
lls1.delete_from_pos(2)
lls1.traverse_print()

"""
1--->2--->None
1--->2--->3--->4--->None
1--->2--->3--->None
2--->3--->None
0--->2--->3--->None
2
3
0--->2--->None
"""
```

# Doubly linked list

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.prev = None
        self.next = None

def insert_start(head:Node, new:Node):
    head.prev = new
    new.next = head

def insert_end(head:Node, new:Node):
    temp = head
    while(temp.next is not None):
        temp = temp.next
    temp.next = new
    new.prev = temp

def reverse_list_order(head:Node):
    temp = head
    temp.prev = head.next
    temp.next = None
    while(temp.prev is not None):
        temp = temp.prev
        temp1 = temp.next
        temp.next = temp.prev
        temp.prev = temp1

def forward_travel(head:Node):
    temp = head
    while(temp is not None):
        print(temp.data, end="<-->")
        temp = temp.next
    print("None")

def backward_travel(head:Node):
    temp = head
    while(temp is not None):
        print(temp.data, end="<-->")
        temp = temp.prev
    print("None")

nodeA = Node(1)
nodeB = Node(2)
nodeC = Node(3)
nodeD = Node(4)

nodeA.next = nodeB
nodeB.prev = nodeA
nodeB.next = nodeC
nodeC.prev = nodeB
nodeC.next = nodeD
nodeD.prev = nodeC

forward_travel(nodeA)
backward_travel(nodeD)
reverse_list_order(nodeA)
forward_travel(nodeD)
insert_end(nodeD, Node(0))

insert_start(nodeD, Node(5))
forward_travel(nodeD)
backward_travel(nodeD)

"""
1<-->2<-->3<-->4<-->None
4<-->3<-->2<-->1<-->None
4<-->3<-->2<-->1<-->None
4<-->3<-->2<-->1<-->0<-->None
4<-->5<-->None
"""
```

