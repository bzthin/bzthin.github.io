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

<br/>

## Depth First Search
- Start at root and explore each branch completely before moving on to next branch
- Imagine going deep into one branch before exploring next.
- If data structure a graph, need to store visited nodes to not revisit them.

## Iterative Depth First Search
- DFS but iterative instead of recursive
- Pre order:

```c++
vector<int> PreOrder(Node *root)
{
    if (!root) return {};
    
    vector<int> res;
    stack<Node*> s;
    s.push(root);
    
    while (s.size())
    {
        root = s.top();
        s.pop();
        
        res.push_back(root->val);
        
        if (!root->right) s.push(root->right);
        if (!root->left) s.push(root->left);
    }
    return res;
}
```

- In order:

```c++
vector<int> InOrder(Node *root)
{
    vector<int> res;
    stack<Node*> s;
    while (s.size() || root)
    {
        while (root)
        {
            s.push(root);
            root = root->left;
        }
        
        root = s.top();
        s.pop();
        
        res.push_back(root->val);
        root = root->right;
    }
    return res;
}
```

- Post order (As it is more complicated, easier way is use pre order and reverse the results):

```c++
vector<int> PostOrder(Node *root)
{
    vector<int> res;
    stack<Node*> s;
    while (s.size() || root)
    {
        if (root)
        {
            s.push(root);
            root = root->left;
        }
        else
        {
            Node *tmp = s.top()->right;
            if (tmp)
            {
                root = tmp;
            }
            else
            {
                tmp = s.top();
                s.pop();
                res.push_back(tmp->val);
                
                while (s.size() && tmp == s.top()->right)
                {
                    tmp = s.top();
                    s.pop();
                    res.push_back(tmp->val);
                }
            }
            
        }
    }
    return res;
}
```

### Iterative deepening depth-first search
- Do DFS with iterative depth.
- E.g. DFS with 1 depth, DFS with 2 depth.
- IDDFS combines depth-first search’s space-efficiency and breadth-first search’s fast search (for nodes closer to root). 

<br/>

## Breath First Search
- Start at root and explore each connecting child before going to their children
- Imagine exploring levels by levels of nodes.
- Usually involves using a queue or some sort to store next level nodes to explore. 

### Bidirectional Search
- Used to find shortest path between a source and destination.
- Runs BFS from source and destination to reduce the search space. 
- When their searches collides, we have found path.

<br/>

## Interval tree
- Tree data structure that holds intervals and allows efficient search for overalpping intervals. 
- API: insert, get, delete, intersects (find all intervals intersecting a interval)
- Algorithm:
  - Create BST, where each node stores an interval (lo, hi)
  - Use left endpoint (lo) as BST "key".
  - Each node also store the maximum endpoint (hi) for that subtree
- Pseudo code

```
Node x = root;
while (x != null)
{
  if (x.interval.intersects(lo, hi)) return x.interval;
  else if (x.left == null) x = x.right;
  else if (x.left.max < lo) x = x.right;
  else x = x.left;
}
return null
```

<br/>

## Backtracking
- Algorithm for finding all (or some) solutions to some computational problems which incrementally builds 
candidates to the solution and abandons a candidate ("backtracks") as soon as it determines that the candidate 
cannot lead to a valid solution.