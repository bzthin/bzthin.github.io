---
layout: page_with_side_nav
title: Trees and Graphs
permalink: /data-structures/tree-graph/
---

# Trees and Graphs
This page contains trees and graphs information. 
- C++ STL max heap: [`priority_queue`](https://www.cplusplus.com/reference/queue/priority_queue/)

## Node
- Simple defintion of a node 
```c++
struct Node
{
    int val;
    vector<Node*> children;
};
```

# Tree
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

### Binary Heap
- Min or max heaps. They are complete binary trees.
- Can be represented by tree or vector. 
- Insert: Insert new element at the tree rightmost bottom. Then bubble up to find its placing.
- Extract Min/Max: Extract the top, swap with last element in the tree and bubble down to find its placing. Choose left or right nodes yourself.

## Tries (Prefix trees)
- It is a n-ary tree where characters are stored in each node.
- Its leaf nodes are often '*' which is used to indicate a completed word.
- Often used for quick prefix lookup


# Graph
- A graph is a collection of nodes with edges.
- Graphs can be directed or undirected.
- Graphs could have multiple isolated sub graphs.
- Graphs can also have cycles. An acyclic graph is one without cycles.

## Adjacency List
- Most common way to represent a graph
- Every node stores a list of adjacent nodes it is connecting to.
- Sample code
```c++
// Defining with STL
vector<List<int>> graph;

// Defining ourselves
struct Graph
{
    vector<Node> nodes;
}

struct Node 
{
    int val;
    vector<Node*> children;
}
```

## Adjacency Matrices
- Another way to represent a graph
- It is a NxN boolean matrix where each cell(matrix[i][j]) represents if there is an edge from node i to j.

## Graph search

