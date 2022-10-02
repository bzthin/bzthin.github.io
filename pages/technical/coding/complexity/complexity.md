---
title: Big O Complexity
tags: 
keywords: 
last_updated: Oct 2, 2022
summary: 
sidebar: technical_sidebar
permalink: /complexity/
---

# Big O Complexity
This page contains Big O complexity information.

## Time Complexity
- Computational complexity that describes the amount of computer time it takes to run an algorithm.
- Big O: Used to describe the upper bound on the run time. 
- There are three kinds of cases for all algorithms,
  - Best case: Shortest possible runtim scenario.
  - Worst case: Longest possible runtime scenario.
  - Expected case: General cases scenario.
- During interviews, we usually discuss worst case and expected case.

## Deriving Time Complexity
- Time complexities are straight forward in most cases but can be confusing when deriving logarithmic time and recursive time.
- Best way to understand time complexity is to work with some examples. You can find many examples in CTCI and their explaination.

## Space Complexity
- Measure of the amount of working storage an algorithm needs.
- Similar concept to time complexity. However, instead of time, we are measuring memory used.

## Deriving Space Complexity
- Simiarly to time complexity, space complexities are straight forward in most cases, best way to understand them is to work with some examples. 
- Note that during recursive calls, we need to count space allocated on the stack as well.

## Big O complexity simplification
- We will drop constants and non dominant terms for big O notations to make it less complicated to express its complexity.
- For example, O(2N^2 + N) = O(N^2), where 2 is a constant and N^2 is more dominant than N.

## Complexity notions
- Common notions
  - O(1): Constant time
  - O(log N): Logarithmic
  - O(n): Linear time
  - O(n^2): Quadratic time
  - O(2^n): Exponential time
- Amortized Time: Amortized time is the way to express the general time complexity when an algorithm has a very bad time complexity only once in a while.
