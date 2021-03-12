---
layout: page_with_side_nav
title: Array
permalink: /data-structures/array/
---

# Array
This page contains array information. 
- C++ STL fixed sized array: [`array`](http://www.cplusplus.com/reference/array/array/).
- C++ STL dynamic sized array: [`vector`](http://www.cplusplus.com/reference/vector/vector/).

## Fixed size array
- Fixed sized normal arrays. Nothing much to highlight...

## Dynamic sized array
- Vectors are allocated a specific capacity at the beginning.
- When the number of elements exceeds that capacity, 
a vector will dynamically allocate memory for a new array that has twice the capacity of what it has before,
and transfer all its current elements over to the new array.
- When dynamic resizing happens, the vector iterators are invalidated as all the elements are now in another memory location.
- Note the difference between `vector.reserve()` and `vector.resize()` and use them accordingly.
