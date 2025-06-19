Trees are very important Non-Linear [[CS50/Week 5 (Data Structures)/Data Structures|Data Structures]]. The relationships in a tree are hierarchical, with some objects being "above" and some "below" Others. The main terminology are "parent" and "child".

### Properties
With the exception of the top-element(called the ***root***), each element in a tree has a *parent* and 0 or more *children*. Visually it looks like this:

![[Trees-1.excalidraw]]
- If  a tree $T$ is non-empty, it has a special node, called the **root** of $T$ that has no parent
- Each node $\nu$ of $T$ different from the root has a unique *parent* node $w$; every node with parent $w$ is a *child* of $w$
### Formal Definition
Formally, we define a *tree* $T$ as a set of **nodes** storing elements such that the nodes have a *parent-child* relationship that satisfies the given properties.
Note that according to this definition, a tree can be empty, meaning that it does not have any nodes. This convention allows us to define a tree recursively such that a tree $T$ is either empty or consists of a node $r$, called the root of $T$ and a (possibly empty) set of subtrees whose roots are the children of $r$.


### Edges and Paths
An ***edge*** of tree $T$ is a pair of nodes $(u,v)$ such that $u$ is the parent of $v$ or vice versa. A ***path*** of $T$ is a sequence of nodes such that any two consecutive nodes in the sequence form an edge.

![[Trees-2.excalidraw]]

### Ordered Trees
A tree is ordered if there is a meaningful linear order among the children of each node.
We purposefully identify the children of a node as being the 1st, 2nd, 3rd and so on. Such an order is usually visualized by arranging siblings left to right.

## The Tree Abstract Data Type

We use the concept of **position** as an abstraction for a node of a tree. An element is stored at each position, and positions satisfy parent-child relationships that define the tree structure. A position object for a tree supports the method:
`p.element()` : Return the element stored at position p.

The Tree ADT then supports the following ***accessor methods***, allowing a user to navigate the various positions of a tree:
- `T.root()` : Return the position of the root of Tree or None if T is empty
- `T.is_root(p)` : Return True if position p is the root of Tree T.
- `T.parent(p)` : Return the position of the parent of position p, or `None` if p is the root of T
- `T.num_children(p)` : Return the number of children of position p
- `T.chilren(p)` Generate an iteration of the children of position p.
- `T.is_leaf(p)` : Return True if position p does not have any children.
- `len(T)`: Return the number of positions (and hence elements) that are contained in tree T
- `T.is_empty()` : Return True if T is empty
- `T.poistions()`: Generate an iteration of all positions of tree T.
- `iter()` : Generate an iteration of all elements stored within tree T.`

### Computing Depth and Height
**Depth**(p): The number of ancestors of $p$, excluding $p$ itself. The depth of $p$ can also be defined recursively as:
- If $p$ is the root, then depth of $p$ is 0.
- Otherwise, the depth of $p$ is one plus the depth of the parent of p.
Based on this definition. we present a simple, recursive algorithm:
```python
def depth(self, p):
if self.is_root(p):
	return 0
else
	return 1 + self.depth(self.parent(p))
```
The running time of $T.depth(p)$ for position $p$ is $O(d_p + 1)$.
$d_p$ is the depth of $p$ in the tree $T$, because the algorithm performs a constant-time recursive step for each ancestor of $p$. Thus algorithm of $T.depth(p)$ runs in $O(n)$ worst-case time, where $n$ is the total number of positions in $p$.

**Height** of $p$ is also defined recursively as:
- If $p$ is a leaf, then the height of $p$ is 0
- Otherwise, the height of $p$ is 1 + maximum of the heights of $p$'s children.
Another algorithm can be implemented in code as:
```python
def _height1(self):
	"""Return the height of the tree."""
	return max(self.depth(p) for p in self.positions( ) if self.is_leaf(p))
```
 Unfortunately this algorithm is not very efficient. We will see that the `.positions()` methods will be implemented to run in $O(n)$ time. Because this algorithm also calls `depth(p)` on each leaf of $T$, its running time is $O(n+\sum_{p\in{L}}(d_{p} + 1))$ where $L$ is the set of leaf positions of $T$. In the worst case $\sum_{p\in{L}}(d_{p} + 1)$ is proportional to $n^2$ . So the algorithm `height1` run in $O(n^2)$ worst-case time.

Using the original recursive algorithm:
```python
def _height2(self,p):
	"""Return the height of the subtree rooted at position p"""
	if self.is_leaf(p):
		return 0
	else:
		return 1 + max(self._height2(c) for c in self.children(p))
```
To analyze this algorithm:
We assume that that `chilren(p)` method will be implemented at $O(c_p +1)$ time, where $c_p$ is the no. of children of $p$. This algorithm spends $O(c_p+1)$ time at each position $p$ to compute the maximum. It's overall running time is $O(\sum_{p}(c_p+1)) = O(n+\sum_p c_p)$.
In order to complete the analysis, we make use of the following property

> Let $T$ be a tree with $n$ positions, and let $c_p$ denote the number of children of a position $p$ of T. Then, summing over the positions of $T$, $\sum_p c_p = n-1$.

So, the running time of the given algorithm is $O(n)$.


  

