---
layout: page_with_side_nav
title: Dynamic Programming
permalink: /algorithms/dynamic-programming/
---

# Dynamic programming 
- Identify that a problem requires dynamic programming when it has overlapping sub problems.

## Approach
- Typically brute force will utilize recurisve solution like DFS but usually time complexity would be expoential. This is called Top Down approach.
- To prevent double calculating in recursive solution, cache previous answers. This is called Top Down approach with memorization.
- We can also change into a iterative solution by doing an Bottom Up approach.

## Recursive vs Iteration solution
- Recursive solution is usually easier to understand and work with. However, they can be very space inefficient.
- Iterative solution might make the code way more complex, but would be more space efficient.  

## Identifiable Patterns 
- 0/1 Knapsack
- Unbounded Knapsack
- Shortest Path (eg: Unique Paths I/II)
- Fibonacci Sequence (eg: House Thief, Jump Game)
- Longest Common Substring/Subsequeunce