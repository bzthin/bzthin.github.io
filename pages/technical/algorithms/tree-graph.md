---
layout: page_with_side_nav
title: Trees and Graphs
permalink: /algorithms/tree-graph/
---

# Trees and Graphs
This page contains trees and graphs algorithms. 

## Binary tree traversal
- In order (left, current, right)
- Pre order (current, left, right)
- Post order (left, right, current)

## Depth First Search
- Start at root and explore each branch completely before moving on to next branch
- Imagine going deep into one branch before exploring next.
- If data structure a graph, need to store visited nodes to not revisit them.

## Breath First Search
- Start at root and explore each connecting child before going to their children
- Imagine exploring levels by levels of nodes.
- Usually involves using a queue or some sort to store next level nodes to explore. 

### Bidirectional Search
- Used to find shortest path between a source and destination.
- Runs BFS from source and destination to reduce the search space. 
- When their searches collides, we have found path.

