---
title: Bits Manipulation
sidebar: technical_sidebar
permalink: /algorithms_bits_manipulation
---

## Bitwise operations
- NOT: ~
- AND: &
- OR: \|
- XOR: ^
- Left Shift: \<\<
- Right Shift: \>\>

## Two's Complement
- Used in computing as a method of signed number representation.
- A positive number is represented as itself 
- A negative number is represented as the two's complement of its absolute value (with a 1 in its
sign bit to indicate that a negative value)
- To get negative number from postive number, invert the bits and add 1.

## Arithmetic/Logical right shift
- Imagine a negative number like 1011 0101, which is -75, when we do an right shift by 2,
- In arithmetic right shift, we shift the bits but retain the sign bit. So it results to 1101 1010, which is -38.  
- In logical right shift, we shift the entire bits without retaining the sign bit. So it results in 0101 1010, which is 90.
- In C++, whether if its arithmetic or logical shifts is implementation dependent. 
Usually its arithmetic, but its better to think that right shift on negative numbers are undefined.


## Tips
- x & ~(x-1) gives you the lowest bit that is 1