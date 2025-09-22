
# Heaps

- A Heap is a complete [[Binary Trees|binary tree]] that satisfies the heap property: ==for every node, the value of its children is greater than or equal to its own value.==

## Binary Heap
It can be a Min Heap or a Max Heap. In Min Heap, the key at the root is the smallest among all the keys in the heap. Similarly, a Max Heap follows the same principle, but with largest key at the root

### Array Representation

Typically, a binary heap is represented at an array as:
- The root element at `arr[0]`
- `arr`\[$\frac{(i-1)}{2}$] Returns the parent node of `arr[i]th` node
- `arr`\[$2i+1$] Returns the left child of `arr[i]`
- `arr`\[$2i+2$] Returns the right child of `arr[i]`


```python
from sys import maxsize
class heap:
    def __init__(self, cap:int):
        self.heap_size = 0
        self.capacity = cap
        self.harr = [0]*cap #[0]*n=[0,0,...ntimes 0]
    
    def getMin(self): return self.harr[0]
    
    def parent(self, i:int): return (i-1)//2

    def left(self, i:int): return (2*i+1)
    
    def right(self, i:int): return 2*i+2

    def insertkey(self, k:int):
        if (self.heap_size==self.capacity):
            print("\nOVERFLOW\n")
            return
        
        self.heap_size +=1
        i = self.heap_size - 1
        self.harr[i] = k

        while(i != 0 and self.harr[self.parent(i)] > self.harr[i]):
            self.harr[i], self.harr[self.parent(i)] = self.harr[self.parent(i)], self.harr[i]
            i = self.parent(i)
    
    def decreaseKey(self, i:int, new_value:int):
        self.harr[i] = new_value
        while(i != 0 and self.harr[self.parent(i)] > self.harr[i]):
            self.harr[i], self.harr[self.parent(i)] = self.harr[self.parent(i)], self.harr[i]
            i = self.parent(i)
    
    def extractMin(self):
        if self.heap_size <= 0:
            return
        if self.heap_size == 1:
            return self.harr[0]
        
        root =self.harr[0]
        self.harr[0] = self.harr[self.heap_size-1]
        self.heap_size-=1
        self.MinHeapify(0)

        return root
        
    def MinHeapify(self,i):
        l = self.left(i)
        r = self.right(i)
        smallest = i
        if (l < self.heap_size and self.harr[i] > self.harr[l]):
            smallest = l
        if (r < self.heap_size and self.harr[smallest] > self.harr[r]):
            smallest = r
        
        if(smallest != i):
            self.harr[i], self.harr[smallest] = self.harr[smallest], self.harr[i]
            self.MinHeapify(smallest)
    
    def deleteKey(self,i):
        if self.heap_size <= 0:
            return
        if self.heap_size < i:
            return "INDEX_OUT_OF_|RANGE"
        
        self.decreaseKey(i, -maxsize-1)
        self.extractMin()
```


```python
h = heap(11)
h.insertkey(3)
h.insertkey(2)
h.deleteKey(1)
h.insertkey(15)
h.insertkey(5)
h.insertkey(4)
h.insertkey(45)

print(h.extractMin(), end=" ")
print(h.getMin(), end=" ")
h.decreaseKey(2,1)
print(h.getMin())

```

    2 4 1
    