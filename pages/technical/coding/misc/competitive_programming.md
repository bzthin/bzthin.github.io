---
title: Competitive Programming 
sidebar: technical_sidebar
permalink: /misc_competitive_programming
---

## Competitive Programming
- This page contains competitive programming tips

## Template
```c++
#include <bits/stdc++.h>
using namespace std;
int main() {
  // code
}
```

## Input and output
- Use `cin, cout, printf, scanf, getline` for input and output related
- To make input output more efficient, do this
```c++
ios::sync_with_stdio(0);
cin.tie(0);
```

### Shorten code
- Typedef long types like long long to `typedef ll long long`
- Macros for common things. i.e
```c++
#define F first
#define S second
#define PB push_back
#define MP make_pair
#define REP(i,a,b) for (int i = a; i <= b; i++)
#define SQ(a) a*a
```
