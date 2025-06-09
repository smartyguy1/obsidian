- It is implemented in one of two ways: as an **array** or as a **linked list**.
- In either case, the crucial rule is LIFO(Last In, First Out).
- There are only two operations that can be legally performed on a stack
	- **Push**: Add a new element to the top of the stack
	- **Pop**: Remove the most recently-added element from the top of the stack
# Array-based implementation
```C
typedef struct _stack
{
	VALUE array[CAPACITY];
	int top;
}
stack;
```

## Push
- Add a new element to the top of the stack

In the general case, `push()` needs to:
- Accept a pointer to the stack.
- Accept data of type `VALUE` to be added to the stack.
- Add that data to the stack at the top of the stack
- Change the location of the top of the stack

![[ezgif-5-09f1b573e7.gif]]
## Pop
- Remove the most recent element from the top of the stack

In general. `pop()` needs to:
- Accept a pointer to the stack
- Change the location of the top of the stack
- Return the value that was removed from the stack

![[ezgif-5-1e0333d64d.gif]]

# Linked list-based implementation
```C
typedef struct _stack
{
	VALUE val;
	struct _stack *next;
}
stack;
```
- Make sure to always maintain a pointer to the head of the linked list.
- To **push**, dynamically allocate a new node, set its next pointer to point to the current head of the list, then move the head pointer to the newly-created node.
![[ezgif-4-26ef5e668c.gif]]

- To **pop**, traverse the linked list to its second element(if it exists), free the head of the list, then move the head pointer to the (former) second element.
	![[ezgif-4-d5f5ad76e4.gif]]
