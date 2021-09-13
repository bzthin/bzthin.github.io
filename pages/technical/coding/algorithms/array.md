---
layout: page_with_side_nav
title: Array
permalink: /algorithms/array/
---

# Array
This page contains array algorithm information. 


## Techniques TBD
- Two pointers
- Sliding window
- Circular array


## Pattern search TBD
- KMP (string)
- Rolling hash


## Knuth-Morris-Pratt (KMP) Algorithm
- Search substring in string efficiently.
- Steps:
  - Preprocess the substring pattern to generate an array of lps (longest proper prefix/suffi)
   - i.e `abcabcabcd` -> `0001231230` 
   - When there is a mismatch, use lps index to move back to last recurring pattern index.
- Code:
```c++
int strstr(string str, string sub)
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
            if (j == 0)
            {
                ++i;
            }
            else
            {
                j = lps[j-1];
            }
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