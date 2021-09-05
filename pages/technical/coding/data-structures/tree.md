---
layout: page_with_side_nav
title: Trees 
permalink: /data-structures/tree/
---

# Trees 
This page contains trees information. 
- A tree consist of nodes. Each nodes has zero or more child nodes

## Node
- Simple defintion of a node 
```c++
struct Node
{
    int val;
    vector<Node*> children;
};
```

## Binary tree
- A tree where each node has up to two children.
- Binary search tree is when every node in the tree fits a specific ordering property. 

### Balanced tree
- Balanced tree means left and right subtree are more or less the same. (I.e Depth difference is <= 1)
- Common self balancing tree are red-black trees and AVL trees.

### Complete binary tree
- Every level of the tree is fully filled except the last level.

### Full binary tree
- Every node has zero or two children, no one child nodes.

### Perfect binary tree
- Tree that is both full and complete.

### Binary Heap
- Min or max heaps. They are complete binary trees.
- Can be represented by tree or vector(i.e priority_queue).
- Insert: Insert new element at the tree rightmost bottom. Then bubble up to find its placing.
- Extract Min/Max: Extract the top, swap with last element in the tree and bubble down to find its placing. Choose left or right nodes yourself.

## Tries (Prefix trees)
- It is a n-ary tree where characters are stored in each node.
- Its leaf nodes are often '*' which is used to indicate a completed word.
- Often used for quick prefix lookup

## Disjoint-set data structure 
- Also called union-find data structure
- Data structure to collect a collection of disjoint(non-overlapping) sets.
- Operations:
  - MakeSet: Adds a new element which is placed into a new set containing only that element.
  - Find: Follows the chain of parent points to find the root of the set.
  - Merge: Merge two disjoint sets into one.
- Complexity for find and merge can be near constant amortized time by doing these optimizations
  - Find: Flatten the tree by redirectly child nodes to point directly to the parent each time.
  - Merge: Merge by size or rank, where the "smaller" set will merge to the "larger" set.
  
## Other types of trees 
### Self balancing binary search trees
- AVL Tree:  
  - Strictly balance the trees
- Red black tree:
  - Has either red or black painted on each node
- Splay tree:
  - A binary search tree with the additional property that recently accessed elements are quick to access again. 

