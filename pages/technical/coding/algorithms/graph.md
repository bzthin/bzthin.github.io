---
layout: page_with_side_nav
title:  Graph
permalink: /algorithms/graph/
---

# Graphs
This page contains graphs algorithms. 
 
## Minimum spanning tree
-  A minimum spanning tree is a spanning tree with the minimum possible total edge weight in a “weighted undirected graph”.

### Cut property
- A cut is a partition of vertices in a graph into two disjoint subsets. 
- A cut-set refers to the edges that is in the cut that connects from one disjoint set to the other.
- For any cut of the graph, if the weight of an edge in the cut-set is strictly smaller than the weights of all other edges of the cut-set, then this edge belongs to all MSTs of the graph.

### Kruskal’s Algorithm
- Algorithm to construct minimum spanning tree of a weighted undirected graph
- Steps
  - Sort all edges in ascending weight order 
  - Add edges in that order into MST. Skip edges that would produce cycles. (Use Disjoint set data structure to check cycles)
  - Repeat until N-1 edges are added

### Prim's Algorithm
- Algorithm to construct minimum spanning tree of a weighted undirected graph
- Steps
  - Constructs a visited and non visited set. 
  - Take a vertex from the non visited set, add it into the visited set while adding all its connected edges to our list of edges
  - Choose the edge with the minimum weight and visit the next vertex.
  - If there are no more edges to choose from, we will look into the non visited set
  - Repeat until all vertices are visited.
- Difference with Kruskal, is Kruskal uses edges but Prim uses vertices, thus difference in time complexities.

<br>

## Single/Multi Source Shortest Path
### Dijkstra’s algorithm (Single)
- “Dijkstra’s algorithm” solves the “single-source shortest path” problem in a weighted directed graph with non-negative weights.
- We take the starting point u as the center and gradually expand outward while updating the “shortest path” to reach other vertices.
- “Dijkstra's Algorithm” uses a “greedy approach”. Each step selects the “minimum weight” from the currently reached vertices to find the “shortest path” to other vertices.
- Pseudocode:
```
function Dijkstra(Graph, source):
    create vertex set Q

    for each vertex v in Graph:            
        dist[v] ← INFINITY                 
        prev[v] ← UNDEFINED                
        add v to Q                     
    dist[source] ← 0                       
   
    while Q is not empty:
        u = vertex in Q with min dist[u]    
        remove u from Q
       
        for each neighbor v of u still in Q:
            altDist = dist[u] + length(u, v)
            if altDist < dist[v]:              
                dist[v] = altDist
                prev[v] = u

    return dist[], prev[]
```
- Time complexity (with binary heap): O(V + ElogV)
- Space complexity O(V)

### Bellman-Ford algorithm (Single)
- Solve the “single source shortest path” problem in graphs with negative weights.
- TBD

### Floyd-Warshall Algorithm
- TBD

### AStar algorithm
- TBD

<br> 

## Strongly Connected Components: 
### Tarjan's Algorithm
- TBD




