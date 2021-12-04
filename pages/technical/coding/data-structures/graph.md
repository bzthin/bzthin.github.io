---
layout: page_with_side_nav
title: Graphs
permalink: /data-structures/graph/
---

# Graph
This page contains graph information.
- A graph is a non-linear data structure consisting of nodes(vertices) and edges.


## Introduction
- A graph contains vertices and edges.
- Graphs can be directed or undirected.
- Each edge could be assigned a weight/cost.
- Graphs could have multiple isolated sub graphs.
- Graphs can also have cycles. An acyclic graph is one without cycles.
- Degree of vertex means number of edges connecting the vertex.
  - In degree(incoming edges),  out degree(outgoing edges) 


## Data Structure Representation
### Adjacency List
- Every node stores a list of adjacent nodes it is connecting to.

### Adjacency matrix
- It is a NxN boolean matrix where each cell(matrix[i][j]) represents if there is an edge from node i to j.


## Disjoint set 
- Also known as the union-find data structure. Used to check if two vertices are connected. 
- Mainly has two functions, union and find. 
- Has two ways to implement
  - Quick Find: Time complexity of the find function will be O(1). However, union function be O(N).
  - Quick Union: As compared to quick find, time complexity of union function is better. Meanwhile, the find function will take more time.
- Generally quick union is more efficient than quick find.
- Optimizations
  - Union by rank: We can optimize the two methods by selecting our parent node during union by rank. (Height of each vertex). The idea is merge the shorter tree under the taller tree to reduce height.
  - Path compression: We can also optimize by compressing each node path to parent node. After a find operation, update the parent node of all traversed elements to directly the parent node to eliminate traversal in future.
- Code:


```c++
class UnionFind {
public:
    UnionFind(int sz) : root(sz), rank(sz) {
        for (int i = 0; i < sz; i++) {
            root[i] = i;
            rank[i] = 1;
        }
    }

    int Find(int x) {
        if (x == root[x]) {
            return x;
        }
        return root[x] = Find(root[x]);
    }

    void UnionSet(int x, int y) {
        int rootX = Find(x);
        int rootY = Find(y);
        if (rootX != rootY) {
            if (rank[rootX] > rank[rootY]) {
                root[rootY] = rootX;
            } else if (rank[rootX] < rank[rootY]) {
                root[rootX] = rootY;
            } else {
                root[rootY] = rootX;
                rank[rootX] += 1;
            }
        }
    }

    bool connected(int x, int y) {
        return Find(x) == Find(y);
    }

private:
    vector<int> root;
    vector<int> rank;
};
```
