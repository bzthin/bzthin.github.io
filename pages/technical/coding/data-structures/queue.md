---
layout: page_with_side_nav
title: Queue
permalink: /data-structures/queue/
---

# Queue
This page contains queue information. 
- C++ STL fixed sized array: [`queue`](https://www.cplusplus.com/reference/queue/).

## General
- Queue uses FIFO (first in first out) ordering.
- In C++, default container it uses is `deque` to achieve LIFO.
- Common operations: push, pop, front, back.

## Deque
- C++ double ended queue
- Containers with dynamic sizes that can be expanded or contracted on both ends
- Provide a functionality similar to vectors, but with efficient insertion and deletion of elements also at the beginning of the sequence, and not only at its end. 
- Unlike vectors, deques are not guaranteed to store all its elements in contiguous storage locations: accessing elements in a deque by offsetting a pointer to another element causes undefined behavior.
