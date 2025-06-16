Trees are very important Non-Linear Data Structures. The relationships in a tree are hierarchical, with some objects being "above" and some "below" Others. The main terminology are "parent" and "child".

### Properties
With the exception of the top-element(called the ***root***), each element in a tree has a *parent* and 0 or more *children*. Visually it looks like this:

![[Trees-1.excalidraw]]
- If  a tree $T$ is non-empty, it has a special node, called the **root** of $T$ that has no parent
- Each node $\nu$ of $T$ different from the root has a unique *parent* node $w$; every node with parent $w$ is a *child* of $w$
### Formal Definition
Formally, we define a *tree* $T$ as a set of **nodes** storing elements such that the nodes have a *parent-child* relationship that satisfies the given properties.
Note that according to this definition, a tree can be empty, meaning that it does not have any nodes. This convention allows us to define a tree recursively such that a tree $T$ is either empty or consists of a node $r$, called the root of $T$ and a (possibly empty) set of subtrees whose roots are the children of $r$.




