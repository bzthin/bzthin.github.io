---
title: Graph
sidebar: technical_sidebar
permalink: /algorithms_graph
---

## Overall
- There are many graph algorithms. Important ones are usually BFS/DFS and topological sort(in sorting section). But would be good to know Dijkstra and Prim/Kruskal.

## Minimum spanning tree
-  A minimum spanning tree is a spanning tree with the minimum possible total edge weight in a “weighted undirected graph”.

### Cut property
- A cut is a partition of vertices in a graph into two disjoint subsets. 
- A cut-set refers to the edges that is in the cut that connects from one disjoint set to the other.
- For any cut of the graph, if the weight of an edge in the cut-set is strictly smaller than the weights of all other edges of the cut-set, then this edge belongs to all MSTs of the graph.

### Kruskal’s Algorithm
- Greedy algorithm to construct minimum spanning tree of a weighted undirected graph using edges
- Steps
  - Sort all edges in ascending weight order 
  - Add edges in that order into MST. Skip edges that would produce cycles. (Use Disjoint set data structure to check if there are cycles)
  - Repeat until N-1 edges are added

### Prim's Algorithm
- Greedy algorithm to construct minimum spanning tree of a weighted undirected graph using vertices
- Steps
  - Constructs a visited and non visited set. 
  - Take a vertex from the non visited set, add it into the visited set while adding all its connected edges to our list of edges
  - Choose the edge with the minimum weight and visit the next vertex. If that vertex is already visited, simply continue to next minimum weight edge. 
  - If there are no more edges to choose from, we will look into the non visited set
  - Repeat until all vertices are visited.
- The difference between Prim and Kruskal is, Kruskal uses edges but Prim uses vertices, thus they have difference in time complexities.

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
- Will not work if there is a negative weight cycle.
- Pesudocode:
```
function BellmanFord(list vertices, list edges, vertex source) is

    // This implementation takes in a graph, represented as
    // lists of vertices (represented as integers [0..n-1]) and edges,
    // and fills two arrays (distance and predecessor) holding
    // the shortest path from the source to each vertex

    distance := list of size n
    predecessor := list of size n

    // Step 1: initialize graph
    for each vertex v in vertices do

        distance[v] := inf             // Initialize the distance to all vertices to infinity
        predecessor[v] := null         // And having a null predecessor
    
    distance[source] := 0              // The distance from the source to itself is, of course, zero

    // Step 2: relax edges repeatedly
    
    repeat |V|−1 times:
         for each edge (u, v) with weight w in edges do
             if distance[u] + w < distance[v] then
                 distance[v] := distance[u] + w
                 predecessor[v] := u

    // Step 3: check for negative-weight cycles
    for each edge (u, v) with weight w in edges do
        if distance[u] + w < distance[v] then
            error "Graph contains a negative-weight cycle"

    return distance, predecessor
```
- Time Complexity: O(\|V\| * \|E\|)
- Space Complexity: O(V) for storing distances  


### Floyd-Warshall Algorithm (Multi)
- An algorithm to find shortest paths with all pairs of vertices in a directed weighted graph with positive or negative edge weights (but with no negative cycles) 
- TBD


### AStar algorithm
- A* is an informed search algorithm, or a best-first search, meaning that it is formulated in terms of weighted graphs: starting from a specific starting node of a graph, it aims to find a path to the given goal node having the smallest cost (least distance travelled, shortest time, etc.). It does this by maintaining a tree of paths originating at the start node and extending those paths one edge at a time until its termination criterion is satisfied.
- TBD

<br> 

## Strongly Connected Components: 
- In the mathematical theory of directed graphs, a graph is said to be strongly connected if every vertex is reachable from every other vertex. 
### Tarjan's Algorithm
- A algorithm in graph theory for finding the strongly connected components (SCCs) of a directed graph.




