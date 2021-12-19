---
layout: page_with_side_nav
title: Array
permalink: /algorithms/array/
---

# Array
This page contains algorithms for array kind of data structure. 

## Binary Search
- Runtime Average: O(log(n))
- Runtime Worst: O(log(n))
- Memory: O(1)
- Algorithm: 
  - Binary search works on sorted arrays. 
  - Binary search begins by comparing an element in the middle of the array with the target value. 
  - If the target value matches the element, its position in the array is returned. 
  - If the target value is less than the element, the search continues in the lower half of the array. 
  - If the target value is greater than the element, the search continues in the upper half of the array. 
  - By doing this, the algorithm eliminates the half in which the target value cannot lie in each iteration.
- Terminating condition can be `lo<=high` or `lo<high` where the latter is for using the value `lo` after while loop instead of returning in the while loop.

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
  - Preprocess the substring pattern to generate an array of lps (longest proper prefix which is also suffix)
   - i.e `abcabcabcd` -> `0001231230` 
   - When there is a mismatch, use lps index to move back to last recurring pattern index.
- Code:

```c++
int KMP(string str, string sub)
{
    vector<int> lps = CreateLPS(sub);
    for (int i=0, j=0; i < str.size() && j < sub.size())
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
vector<string> SplitStr(string input) 
{
    istringstream iss(input);
    string token;
    vector<string> res;
    while(std::getline(ss, token, ',') // or iss >> token if using space as delimiter)
    { 
        res.push_back(token);
    }
    return res;
}
```

