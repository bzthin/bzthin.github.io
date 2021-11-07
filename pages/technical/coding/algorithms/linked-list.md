---
layout: page_with_side_nav
title: Linked List
permalink: /algorithms/linked-list/
---

# Linked List
This page contains algorithms relating to linked list.

## Runner Technique
- The runner technique means iterating through the linked list with two pointers simultaneously, with one ahead of the other.
- For example, 
  - The "slow" pointer could iterate through the list, element by element.
  - The "fast" pointer could be ahead of the slow pointer by a fixed amount while iterating, or hopping multiple nodes for each iteration in the "slow" node.

### Floyd cycle detection
- Using slow and fast pointer method, traverse through list
- If they meet at some point, means there is a cycle
- Able to find start of cycle too. After pointers meet, reset one pointer to the start and move both pointers by single steps. 
- Proof
  - Distance travelled by slowPointer before meeting =x+y
  - Distance travelled by fastPointer before meeting =(x+y+z)+y=x+2y+z
  - Since fastPointer travels with double the speed of slowPointer, and time is constant for both when both pointers reach the meeting point. So by using simple speed, time and distance relation (slowPointer traveled half the distance):
  - 2∗dist(slowPointer)2(x+y)2x+2yx=dist(fastPointer)=x+2y+z=x+2y+z=z