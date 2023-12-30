---
title: Algorithms
sidebar: technical_sidebar
permalink: /algorithms
---


## Algorithms
This page contains useful/commonly used C++ STL helpful functions information. 
- [C++ STL algorithms](https://www.cplusplus.com/reference/algorithm/)

## C++ STL algorithms
algorithm
- count
- count_if
- swap
- fill
- for_each
- remove
- rotate
- unique
- sort
- partial_sort
- stable_sort
- nth_element
- transform

- lower_bound
- upper_bound
- binary_search
- set_intersection (require sorted ranges)

- min_element
- max_element


functional
- plus
- minus
- multiplies
- divides
- function


## Others
- iota

## Misc Algo
- gcd (greatest common divisor)

```c++
int gcd(int a, int b)
{
    if (a == 0)
        return b;
    return gcd(b % a, a);
}
```