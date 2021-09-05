---
layout: page_with_side_nav
title: List
permalink: /data-structures/list/
---

# Linked List
This page contains linked list information. 
- C++ STL singly linked list: [`forward_list`](http://www.cplusplus.com/reference/forward_list/forward_list/)
- C++ STL doubly linked list: [`list`](http://www.cplusplus.com/reference/list/list/)

# General
- Data structure that represents a sequence of nodes.
- Each node has its own memory. Thus accessing all elements in linked list will be slower than vector as it jumps around in memory.  

## Singly linked list
- Each node has a pointer to the next node.
- Typical node structure with `int` data.
```c++
struct Node
{
    int data;
    Node *next;
};
```

## Doubly linked list
- Each node has a pointer to the previous node and next node.
- Typical node structure with `int` data.
```c++
struct Node
{
    int data;
    Node *prev;
    Node *next;
};
```

