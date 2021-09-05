---
layout: page_with_side_nav
title: Hash Table
permalink: /data-structures/hash-table/
---

# Hash Table
C++ STL containers for hash tables
- [`unordered_map`](http://www.cplusplus.com/reference/unordered_map/unordered_map/): Key value pairs
- [`unordered_multimap`](https://www.cplusplus.com/reference/unordered_map/unordered_multimap/): Similar to unordered_map but allows multiple values to tie to 1 key.

- [`unordered_set`](https://www.cplusplus.com/reference/unordered_set/unordered_set/): Stores unique elements in no particular order and runtime similar to a hash table.
- [`unordered_multiset`](https://www.cplusplus.com/reference/unordered_set/unordered_multiset/): Similar to unordered_set, but allows multiple values

## General
- We have an array as our storage. 
- A hash function is applied on to a key to get a hash code. 
- This hash code is used to map to an index in an array.
- We store the value in that index for look up in future.

## Collision handling
Its possible our hash code maps different keys to the same index in the array. Some collision handling techniques are,

### Chaining
- Make each element in the array a linkedlist instead. 
- Stores key and value in each element in linked list for look up.

### Open Addressing
- All elements stored on hash table. 
- Each entry contains value or empty or deleted. 
- After mapping to an index, we search next elements until desired element is found or its clear that it is not in the table.
- Way of searching can be any method. For example linear probing, quadratic probing or double hashing to find next index.
