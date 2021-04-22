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

### Topological sort
- Kahn's algorithm, linear method. 
  - Time complexity: O(|V| + |E|)
  - Space complexity: O(|V| + |E|)

```
L = Empty list that will contain the sorted elements
S = Set of all nodes with no incoming edge

while S is non-empty do
    remove a node n from S
    add n to tail of L
    for each node m with an edge e from n to m do
        remove edge e from the graph
        if m has no other incoming edges then
            insert m into S

if graph has edges then
    return error   (graph has at least one cycle)
else 
    return L   (a topologically sorted order)
```



- Alternative method using DFS
  - Time complexity: O(|V| + |E|)
  - Space complexity: O(|V| + |E|)

```
L ← Empty list that will contain the sorted nodes
while exists nodes without a permanent mark do
    select an unmarked node n
    visit(n)

function visit(node n)
    if n has a permanent mark then
        return
    if n has a temporary mark then
        stop   (not a DAG)

    mark n with a temporary mark

    for each node m with an edge from n to m do
        visit(m)

    remove temporary mark from n
    mark n with a permanent mark
    add n to head of L
```