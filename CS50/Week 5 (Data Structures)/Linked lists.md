# <u>Singly-Linked Lists</u> 

[[CS50/Week 3 (Algorithms)/Data Structures|Recall]], `struct` gives us "containers" for holding variables of different data types.
A linked list **node** is a special kind of `struct` with two members:
- Data of some data type (`int, char, float`...)
- A pointer to another node of the same type
In this way, a set of nodes together can be thought of as forming a chain of elements that we can follow from beginning to end.
Example:
```C
typedef struct sllist
{
	VALUE val;
	struct sllist* next;
	
}sllnode;
```
### Important operations:
1. Create a linked list when it doesn’t already exist. 
2. Search through a linked list to find an element. 
3. Insert a new node into the linked list.
4. Delete a single element from a linked list.
5. Delete an entire linked list.

Creating a linked list:
```C
sllnode* create(VALUE val);
```

### Steps Involved
1. Dynamically allocate space for a new `sllnode`.
2. Check to make sure we didn't run out of memory
3. Initialize the node's `val` field.
4. Initialize the node's `next` field
5. Return a pointer to the newly created `sllnode`
![[Pasted image 20240831153608.png]]


To search through a  linked list to find an element.
```C
bool find(sllnode* head, VALUE val);
```
- Steps involved:
	1. Create a traversal pointer to the list's head.
	2. If the current node's `val` field is what we're looking for, report success.
	3. If not, set the traversal pointer to the next pointer in the list and go back to step 2.
	4. If you've reached the end of the list, report failure.
	```C
	bool exists = find(list, 6);
	```

## Inserting a new node

- Insert a new node into the linked list
```C
sllnode* insert(sllnode* head, VALUE val);
```
- Steps Involved
	1. Dynamically allocate space for a new `sllnode`
	2. Check to make sure we didn't run out of memory
	3. Populate and insert the node at the beginning of the linked list
	4. Return a pointer to the new head of the linked list

## Delete an entire linked list

- Steps involved:
	1. Free the current node
	2. Delete the rest of the list
	3. If you've reached a null pointer, stop.

# <u>Doubly Linked List</u>

- A doubly-linked list, by contrast, allows us to move forward and backward through the list, all by simply adding one extra pointer to our `struct` definition.
```C
typedef struct dllist
{
	VALUE val;
	struct dllist* prev;
	struct dllist* next;
}
dllnode;
```

![[Pasted image 20240831161125.png]]
#### Important operations

1. Create a linked list when it doesn't already exist.
2. Search through a linked list to find an element.
3. Insert a new node into the linked list.
4. Delete a single element from a linked list.
5. Delete an entire linked list.
```C
dllnode* insert(dllnode* head, VALUE val);
```

#### Insert a new node into the linked list
- Steps involved:
	1. Dynamically allocate space for a new `dllnode`.
	2. Check to make sure we didn't run out of memory.
	3. Populate and insert the node at the beginning of the linked list.
	4. Fix the `prev` pointer of the old head of the linked list.
	5. Return a pointer to the new head of the linked list.

![[exp.gif]]

#### Deleting a node from a linked list
- Steps involved
	1. Fix the pointers of the surrounding nodes to "skip over" `target`
	2. Free `target`
![[ezgif-6-1dfaf11d7c.gif]]

- Linked lists, of both the singly- and doubly-linked varieties, support extremely efficient *insertion* and *deletion* of elements
- Downside: We have lost the ability to randomly-access list elements. It now takes $O(n)$ i.e. **linear time**.
