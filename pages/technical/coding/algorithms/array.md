---
layout: page_with_side_nav
title: Array
permalink: /algorithms/array/
---

# Array
This page contains algorithms for array kind of data structure. 

## Two pointers
- Uses two pointers to point to different locations of the array.
- Could be from both ends, from middle or slow and fast pointers etc.

## Sliding window
- A window (subarray) that expands or contracts based on condition.
- Iterable through the array. 

## Circular array
- Last element next to first element of array.
- Can be used to create queues.

## Knuth-Morris-Pratt (KMP) Algorithm
- Search substring in string efficiently.
- Steps:
  - Preprocess the substring pattern to generate an array of lps (longest proper prefix/suffi)
   - i.e `abcabcabcd` -> `0001231230` 
   - When there is a mismatch, use lps index to move back to last recurring pattern index.
- Code:
```c++
int KMP(string str, string sub)
{
    if (sub.empty())
    {
        return 0;
    }
    
    vector<int> lps = CreateLPS(sub);
    
    int i = 0;
    int j = 0;
    while (i < str.size() && j < sub.size())
    {
        if (str[i] == sub[j])
        {
            ++i; 
            ++j;
        }
        else
        {
            j ? j = lps[j-1] : ++i;
        }
    }
    
    return j == sub.size() ? i-j : -1;
}

vector<int> CreateLPS(string str) 
{
    int n = str.size();
    vector<int> lps(n, 0);

    for (int i=0, j=1; j < n; ++j)
    {
        if (str[i] == str[j])
        {
            lps[j] = ++i;
        }
        else if (i != 0)
        {
            i = lps[i-1]; // Return to previous recurring character
            --j; // j doesn't need increment
        }
    }

    return lps;
}
```

## String operations
- Splitting of string with istringstream
```c++
vector<string> SplitStr(string input) {
    istringstream iss(input);
    string token;
    vector<string> res;
    while(std::getline(ss, token, ',') { // or iss >> token if using space as delimiter)
        res.push_back(token);
    }
    return res;
}
```

