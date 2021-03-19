---
layout: page_with_side_nav
title: Tree and Graphs
permalink: /data-structures/tree-graph/
---

# Tree and Graphs
This page contains tree and graph information. 

## Node
- Simple defintion of a node
```c++
struct Node
{
    int val;
    vector<Node*> children;
};
```

## Tree
- Consist of nodes. Each nodes has zero or more child nodes

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

### Binary tree traversal
- In order (left, current, right)
- Pre order (current, left, right)
- Post order (left, right, current)

### Binary Heap
- Min or max heaps. They are complete binary trees.
- Can be represented by tree or vector. 
- Insert: Insert new element at the tree rightmost bottom. Then bubble up to find its placing.
- Extract Min/Max: Extract the top, swap with last element in the tree and bubble down to find its placing. Choose left or right nodes yourself.

## Tries (Prefix trees)



