---
layout: page_with_side_nav
title: Queue
permalink: /data-structures/queue/
---

# Queue
This page contains queue information. 
- C++ STL queue: [`queue`](https://www.cplusplus.com/reference/queue/).
- C++ STL heap: [`priority_queue`](https://www.cplusplus.com/reference/queue/priority_queue/)
- C++ STL double ended queue: [`deque`](http://www.cplusplus.com/reference/deque/deque/)

## Queue
- Queue uses FIFO (first in first out) ordering.
- In C++, default container it uses is `deque` to achieve LIFO.
- Common operations: push, pop, front, back.


## Priority_queue
- C++ priority queue represents a heap data structure created with vector<T> by default.
- Default is max heap. Change to min heap by using std::greater<T> comparator.
- Use strict weak ordering criterion to compare.
- The container used should have random access iterators and support the following operations: empty() size() front() push_back() pop_back(). 
- Common operations: push, pop, top.


## Deque
- C++ double ended queue
- Containers with dynamic sizes that can be expanded or contracted on both ends
- Provide a functionality similar to vectors, but with efficient insertion and deletion of elements also at the beginning of the sequence, and not only at its end. 
- Unlike vectors, deques are not guaranteed to store all its elements in contiguous storage locations: accessing elements in a deque by offsetting a pointer to another element causes undefined behavior.