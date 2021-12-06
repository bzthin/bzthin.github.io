---
layout: page_with_side_nav
title:  Graph
permalink: /algorithms/graph/
---

# Graphs
This page contains trees and graphs algorithms. 

## Graph algorithms (TBD) 
- TBD (Distance, search, connectivity, cycle-detection etc)
- 3 basic ways to represent graph in memory (object and pointers, matrix, and adjacency list) and their pros and cons
- Basic graph traversal algorithms, BFS, DFS.

## Articulation point
- TBD
 - https://cp-algorithms.com/graph/cutpoints.html

 
 ## Minimum spanning tree
-  A minimum spanning tree is a spanning tree with the minimum possible total edge weight in a “weighted undirected graph”.

### Cut property
- For any cut C of the graph, if the weight of an edge E in the cut-set of C is strictly smaller than the weights of all other edges of the cut-set of C, then this edge belongs to all MSTs of the graph.

### Kruskal’s Algorithm
- Algorithm to construct minimum spanning tree of a weighted undirected graph
- Steps
  - Sort all edges in ascending weight order 
  - Add edges in that order into MST. Skip edges that would produce cycles
  - Repeat until N-1 edges are added

### Prim's Algorithm
- Algorithm to construct minimum spanning tree of a weighted undirected graph
- Contains visited and non visited set. Each step take a vertex from the non visited set, add it into the visited set, get all its edges and incrementally add by the minimum weight edge. 
If there are no more edges, continue with non visited set.


## Single Source Shortest Path
### Dijkstra’s algorithm
- “Dijkstra’s algorithm” solves the “single-source shortest path” problem in a weighted directed graph with non-negative weights.
- We take the starting point u as the center and gradually expand outward while updating the “shortest path” to reach other vertices.
- “Dijkstra's Algorithm” uses a “greedy approach”. Each step selects the “minimum weight” from the currently reached vertices to find the “shortest path” to other vertices.

### AStar algorithm
- TBD

### Bellman-Ford algorithm
- Solve the “single source shortest path” problem in graphs with negative weights.
- 


## Floyd-Warshall Algorithm
- TBD
