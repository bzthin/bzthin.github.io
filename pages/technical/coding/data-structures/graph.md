---
layout: page_with_side_nav
title: Graphs
permalink: /data-structures/graph/
---

# Graph
This page contains graph information.
- A graph is a non-linear data structure consisting of nodes(vertices) and edges.
- A graph can be directed or undirected.


## Introduction
- A graph is a collection of nodes with edges.
- Graphs can be directed or undirected.
- Each edge could be assigned a weight/cost.
- Graphs could have multiple isolated sub graphs.
- Graphs can also have cycles. An acyclic graph is one without cycles.


## Representation
### Adjacency List
- Most common way to represent a graph
- Every node stores a list of adjacent nodes it is connecting to.

### Adjacency matrix
- Another way to represent a graph
- It is a NxN boolean matrix where each cell(matrix[i][j]) represents if there is an edge from node i to j.


