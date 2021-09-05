---
layout: page_with_side_nav
title: Primitive Types
permalink: /data-structures/primitive/
---

# TBD
Primitive types - know how int, char, double, etc are represented in memory and the primitive operations on them.
Operations on them (bitwise operators, comparison, etc)

# Primitive
This page contains primitive information

## Types
Here are the basic types and their typical size. (Compiler dependent)

| Type               | Bytes  |
|:-------------------|:-------|
| char               | 1      |
| short              | 2      |
| int                | 4      |
| long long          | 8      |
| unsigned char      | 1      |
| unsigned short     | 2      |
| unsigned int       | 4      |
| unsigned long long | 8      |
| float              | 4      |
| double             | 8      |
| bool               | 1 or 4 |


## Operator precedence
- All operations in C++ have a precedence to follow. 
- [C++ operation precedence](https://en.cppreference.com/w/cpp/language/operator_precedence)

## Bit operations
- `&` (bitwise AND)
- `|` (bitwise OR)
- `^` (bitwise XOR)
- `<<` (bitwise left shift)
- `>>` (bitwise right shift) (Undefined for negative number)
- `~` (bitwise NOT)