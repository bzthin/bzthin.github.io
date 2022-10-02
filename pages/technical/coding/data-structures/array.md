---
title: Array
tags: 
keywords: 
last_updated: Oct 2, 2022
summary: 
sidebar: technical_sidebar
permalink: /data-structures_array/
---

# Array
This page contains array information. 
- C++ STL fixed sized array: [`array`](http://www.cplusplus.com/reference/array/array/).
- C++ STL dynamic sized array: [`vector`](http://www.cplusplus.com/reference/vector/vector/).
- C++ string: [string](https://www.cplusplus.com/reference/string/string/)

## Fixed size array
- Fixed sized normal arrays, fixed capacity.

## Dynamic sized array
- Vectors are allocated a specific capacity at the beginning.
- When the number of elements exceeds that capacity, 
a vector will dynamically allocate memory for a new array that has twice the capacity of what it has before,
and transfer all its current elements over to the new array.
- When dynamic resizing happens, the vector iterators are invalidated as all the elements are now in another memory location.
- Note the difference between `vector.reserve()` and `vector.resize()` and use them accordingly.

## String

- A string is a special kind of array which the values are made up of characters.
- In C++, think of string container as a vector<char> that is null terminated (has a null character at the end).
- All operations can be found at [c++ string](https://www.cplusplus.com/reference/string/string/)