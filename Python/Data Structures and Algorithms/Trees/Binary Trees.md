A binary tree is an [[Trees|ordered tree]] with the following properties:
1. Every node has at most 2 children
2. Each child node is labeled as being either a **left child** or a **right child**.
3. A left child precedes a right child in the order of children of a node.

A binary tree is **proper** if each node has either zero or two children. They are also referred to as **full** binary trees. A binary tree that is not proper is **improper**.

![[Pasted image 20250616212410.png]]
^[Example of a binary tree]

## A Recursive Binary Tree Definition
Incidentally, we can also define a binary tree in a recursive way such that a binary tree is either empty or consists of:
- A node $r$, called the root of $T$, that stores an element
- A binary tree(possibly empty), called the left subtree 
- A binary tree(possibly empty), called the right subtree

## Array representation
