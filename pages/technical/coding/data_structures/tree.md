---
title: Trees
tags: 
keywords: 
last_updated: Oct 2, 2022
summary: 
sidebar: technical_sidebar
permalink: /data-structures_tree/
---

# Trees 
This page contains trees information. 
- A tree consist of nodes. Each nodes has zero or more child nodes.
- Tree can also be considered as a acyclic graph.

## Node
- Simple defintion of a node for a N-ary tree.
```c++
struct Node
{
    int val;
    vector<Node*> children;
};
```
<br>

## Binary tree
- A tree where each node has up to two children.
- Binary search tree is when every node in the tree fits a specific ordering property. 
- Can also be represented by a vector. 
  - Get left child: 2*i + 1
  - Get right child: 2*i + 2
  - Get parent: (i-1) / 2

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

<br>

## Tries (Prefix trees)
- It is a n-ary tree where characters are stored in each node. 
- In each node, the children can be stored as an array or hash table
- Its leaf nodes are often '*' which is used to indicate a completed word.
- Often used for quick prefix lookup

<br>

## Other types of trees 
### Self balancing binary search trees
- AVL Tree:  
  - Strictly balance the trees
- Red black tree:
  - Has either red or black painted on each node
- Splay tree:
  - A binary search tree with the additional property that recently accessed elements are quick to access again. 

