---
layout: page_with_side_nav
title: Dynamic Programming
permalink: /algorithms/dynamic-programming/
---

# Dynamic programming 
- Identify that a problem requires dynamic programming when it has overlapping sub problems.
- Approaches can be top down or bottom up.

## Framework for Dynamic Programming problems
1. Define state. A state is a set of variables that can sufficiently describe a scenario. These variables
are called state variables.
2. A function or data structure that will compute/contain the answer to the problem for every given state.
3. A recurrence relation to transition between states.
4. Base cases, so that our recurrence relation doesn't go on infinitely.

### Steps to convert top-down into bottom-up
1. Start with a completed top-down implementation.
2. Initialize an array dp that is sized according to your state variables.
3. Set your base cases, same as the ones you are using in your top-down function. 
4. Write a for-loop(s) that iterate over your state variables. 
5. Each iteration of the inner-most loop represents a given state, and is equivalent to a function 
call to the same state in top-down. Copy the logic from your function into the for-loop and change 
the function calls to accessing your array. 

## Recursive vs Iteration solution
- Recursive solution is usually easier to understand and work with. However, they can be very space inefficient.
- Iterative solution might make the code way more complex, but would be more space efficient.  

## Identifiable Patterns 
- 0/1 Knapsack
- Unbounded Knapsack
- Shortest Path (eg: Unique Paths I/II)
- Fibonacci Sequence (eg: House Thief, Jump Game)
- Longest Common Substring/Subsequeunce
