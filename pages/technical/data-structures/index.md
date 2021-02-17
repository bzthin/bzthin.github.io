---
layout: page_with_side_nav
title: Data Structures
permalink: /data-structures
---

# Data Structures
This page contains data structures information. 

## Big O Cheat Sheet

| DS | AVG TC | AVG TC | AVG TC | AVG TC | W TC | W TC | W TC | W TC | SC |
|    | Access | Search | Insertion | Deletion | Access | Search | Insertion | Deletion | |
|:-|:-|:-|:-|:-|:-|:-|:-|:-|:-|
| Hash Table | NA | O(1) | O(1) | O(1) | NA | O(n) | O(n) | O(n) | O(n) |

Legend:
- DS: Data structure
- AVG TC: Average time complexity
- W TC: Worst time complexity
- SC: Space complexity

## C++ STL data structures
- `array`: Fixed size array
- `deque`: Double ended queue.
- `forward_list`: Singly linked list
- `list`: Doubly linked list
- `map`: Key value pairs. Implemented as binary search tree
- `multimap`: Similar to map, but allows multiple values to tie to 1 key. 
- `queue`: FIFO data structure. Implemented with deque by default.
- `priority_queue`: Max heap. Implemented with vector by default
- `set`: Stores unique elements where the value of an element is also its key. Implemented as binary search tree.
- `multiset`: Similar to set but allows multiple values to be stored
- `stack`: LIFO data structure. Implemented using deque by default.
- `unordered_map`: Key value pairs. STL implementation of hash table
- `unordered_multimap`: Similar to unordered_map but allows multiple values to tie to 1 key.
- `unordered_set`: Stores unique elements in no particular order and runtime similar to a hash table.
- `unordered_multiset`: Similar to unordered_set, but allows multiple values
- `vector`: Dynamic size arrays