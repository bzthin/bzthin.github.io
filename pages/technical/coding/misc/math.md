---
title: Math
sidebar: technical_sidebar
permalink: /misc_math
---

## Math
This page contains Math information. Here are some common math that is sometimes required in algorithms or deriving time complexity.

## Series
- Summation of 1 to n: 1 + 2 + 3 + ... + (n-1) + n = n/2 * (n+1) = n(n+1)/2.


### Permutation
- Permutation: n permute k = n! / (n-k)!

### Combination
- Combination: n choose k = n! / k!(n-k)!


## Linear Algebra
### Cross product
- Cross product two vectors to find a vector that is perpendicular to both vectors
- a X b = \|\|a\|\| \|\|b\|\| sin(θ)
  - cx = a2b3 − a3b2
  - cy = -(a1b3 - a3b1)
  - cz = a1b2 − a2b1

### Dot product
- Dot product (aka inner product) of two vectors to project one vector onto the other.
- a . b = \|\|a\|\| \|\|b\|\| cos(θ)
- c = a1b1 + a2b2 + a3b3


## Greatest common divisor
- Find greatest common divisor of two numbers.
- If both a and b are zero, returns zero. Otherwise, returns the greatest common divisor of \|a\| and \|b\|.
- C++ STL [gcd](https://en.cppreference.com/w/cpp/numeric/gcd)
