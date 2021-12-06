---
layout: page_with_side_nav
title: Linked List
permalink: /algorithms/linked-list/
---

# Linked List
This page contains algorithms relating to linked list.

## Slow Fast Runner 
- The runner technique means iterating through the linked list with two pointers simultaneously, with one ahead of the other.
- For example, 
  - The "slow" pointer could iterate through the list, element by element.
  - The "fast" pointer could be ahead of the slow pointer by a fixed amount while iterating, or hopping multiple nodes for each iteration in the "slow" node.

## Floyd cycle detection
- Using slow fast runner technique, traverse through list and if they meet at some point, means there is a cycle
- Able to find start of cycle too. After pointers meet, reset one pointer to the start and move both pointers by single steps. 
- Proof
  - ![Floyd Cycle](/assets/images/floyd_cycle_finding.png)
  - Distance travelled by slowPointer before meeting: x + y
  - Distance travelled by fastPointer before meeting: (x + y + z) + y = x + 2y + z
  - Since fastPointer travels with double the speed of slowPointer. So by using simple speed, time and distance relation we have,
    - 2 * dist(slowPointer) = dist(fastPointer)
    - 2(x + y) = x + 2y + z
    - 2x + 2y = x + 2y + z
    - x = z