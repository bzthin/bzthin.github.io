---
layout: page_with_side_nav
title: Graphs
permalink: /algorithms/tree/
---

# Trees
This page contains trees algorithms. 

## Binary tree traversal
- In order (left, current, right)
- Pre order (current, left, right)
- Post order (left, right, current)

## Depth First Search
- Start at root and explore each branch completely before moving on to next branch
- Imagine going deep into one branch before exploring next.
- If data structure a graph, need to store visited nodes to not revisit them.

### Iterative deepening depth-first search
- Do DFS with iterative depth.
- E.g. DFS with 1 depth, DFS with 2 depth.
- IDDFS combines depth-first search’s space-efficiency and breadth-first search’s fast search (for nodes closer to root). 

## Breath First Search
- Start at root and explore each connecting child before going to their children
- Imagine exploring levels by levels of nodes.
- Usually involves using a queue or some sort to store next level nodes to explore. 

### Bidirectional Search
- Used to find shortest path between a source and destination.
- Runs BFS from source and destination to reduce the search space. 
- When their searches collides, we have found path.

## Iterative DFS and BFS
- TBD (DFS iterative pre, in, post methods)


## Disjoint set 
- TBD

## Interval tree
- TBD


## Backtracking
- Algorithm for finding all (or some) solutions to some computational problems which incrementally builds 
candidates to the solution and abandons a candidate ("backtracks") a
s soon as it determines that the candidate cannot lead to a valid solution.