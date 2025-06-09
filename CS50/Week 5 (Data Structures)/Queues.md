- It is used to maintain data in an organized way
- This data structure is commonly implemented in one of two ways: as an **array** or as a **linked list**.
- The important rule that queues follow is FIFO(First In, First Out).

There are only two operations that may legally be performed on a queue.
- **Enqueue**: Add a new element to the end of the queue.
- **Dequeue**: Remove the oldest element from the front of the queue.

# Array-based implementation
```C
typedef struct _queue
{
	VALUE array[CAPACITY];
	int front;
	int size;
}
queue;
```

## Enqueue
- Add a new element to the end of the queue.
In general case, `enqueue()` needs to:
- Accept a pointer to the queue
- Accept data of type `VALUE` to be added to the queue.
- Add that data to the queue at the end of the queue.
- Change the size of the queue.

![[ezgif-6-c0f08d7ab9.gif]]

## Dequeue:
- Remove the most recent element from the front of the queue.

In the general case `dequeue()` needs to:
- Accepts a pointer to the queue
- Change the location of the front of the queue
- Decrease the size of the queue
- Return the value that was removed from the queue

![[ezgif-5-ac6258b2ab.gif]]

# Linked list-based implementation]
```C
typedef struct _queue
{
	VALUE val;
	struct _queue *prev;
	struct _queue *next;
}
queue;
```
- It is important to always maintain pointers to the head and the tail of the linked list! 
## Enqueue:
- Dynamically allocate a new node
- Set its next pointer to `NULL`, set its prev pointer to the tail
- Set the tail's next pointer to the new node
- Move the tail pointer to the newly-created node
![[ezgif-5-a8fcc769f0.gif]]

## Dequeue:
- Traverse the linked list to its second element(if it exists)
- Free the head of the list
- Move the head pointer to the (former) second element
- Make that node's `prev` pointer point to `NULL`

![[ezgif-5-a86c0d0629.gif]]
