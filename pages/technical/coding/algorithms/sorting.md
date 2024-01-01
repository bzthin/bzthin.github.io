---
title: Sorting
sidebar: technical_sidebar
permalink: /algorithms_sorting
---

## Overall
- For interviews, the important ones would be merge sort, quick sort, topological sort. The rest would be good to know but usually not asked to implement.


## Merge Sort
- Runtime Average: O(nlog(n))
- Runtime Worst: O(nlog(n))
- Memory Worst: O(n)
- Algorithm: Divides the array in half until it cannot be divided, start merging halves together while sorting them.

```c++
void MergeSort(vector<int> &v, int l, int r)
{
    if (l < r)
    {
        int m = l+(r-l)/2;
        MergeSort(v, l, m);
        MergeSort(v, m+1, r);
        Merge(v, l, m, r);
    }
}

void Merge(vector<int> &v, int l, int m, int r)
{
    int lhs = l;
    int lhsEnd = m;
    int rhs = m+1;
    int rhsEnd = r;
    
    vector<int> res;
    while (lhs <= lhsEnd || rhs <= rhsEnd)
    {
        int lhsVal = lhs <= lhsEnd ? v[lhs] : INT_MAX;
        int rhsVal = rhs <= rhsEnd ? v[rhs] : INT_MAX;
        
        int val;
        if (lhsVal <= rhsVal)
        {
            val = lhsVal;
            ++lhs;
        }
        else
        {
            val = rhsVal;
            ++rhs;
        }
        
        res.push_back(val);
    }
    
    copy(res.begin(), res.end(), v.begin()+l);
}
```


## Quick Sort
- Runtime Average: O(nlog(n))
- Runtime Worst: O(n^2)
- Memory Worst: O(log(n))
- Algorithm: Pick a random element and partition the array, such that all numbers that are less than the
partitioning element come before all elements that are greater than it. 
Perform the partition on the left and right subparts of the array.

```c++
void QuickSort(vector<int> &v, int l, int r)
{
    if (l < r)
    {
        int pivot = Partition(v, l, r);
        QuickSort(v, l, pivot-1);
        QuickSort(v, pivot+1, r);
    }
}

int Partition(vector<int> &v, int l, int r)
{
    int pivot = v[r];
    int i = l;
    for (int j = l; j < r; ++j)
    {
        if (v[j] <= pivot)
        {
            swap(v[i++], v[j]);
        }
    }
    swap(v[i], v[r]);
    return i;
}
```


## Topological sort
- Kahn's algorithm, linear method. 
  - Time complexity: O(V + E) where V is number of vertices and E is number of edges
  - Space complexity: O(V + E)

```
L = Empty list that will contain the sorted elements
S = Set of all nodes with no incoming edge

while S is non-empty do
    remove a node n from S
    add n to tail of L
    for each node m with an edge e from n to m do
        remove edge e from the graph
        if m has no other incoming edges then
            insert m into S

if graph has edges then
    return error   (graph has at least one cycle)
else 
    return L   (a topologically sorted order)
```
```c++
vector<int> TopologicalSort(int n, vector<vector<int>> &dependency) 
    {
        vector<int> indegrees(n, 0);
        for (auto &d : dependency)
        {
            ++indegrees[d[0]];
        }
                
        queue<int> zeroDeg;
        for (int i = 0; i < n; ++i)
        {
            if (indegrees[i] == 0)
            {
                zeroDeg.push(i);
            }
        }
        
        vector<int> res;
        while (zeroDeg.size())
        {
            int v = zeroDeg.front();
            zeroDeg.pop();
            res.push_back(v);
            
            for (auto &d : dependency)
            {
                if (d[1] == v && --indegrees[d[0]] == 0)
                {
                    zeroDeg.push(d[0]);
                }
            }
        }
        
        for (int i = 0; i < n; ++i)
        {
            if (indegrees[i] != 0)
            {
                return {};
            }
        }
        
        return res;
    }
```

- Alternative method using DFS
  - Time complexity: O(V + E) where V is number of vertices and E is number of edges
  - Space complexity: O(V + E)

```
L = Empty list that will contain the sorted nodes
while exists nodes without a permanent mark do
    select an unmarked node n
    visit(n)

function visit(node n)
    if n has a permanent mark then
        return
    if n has a temporary mark then
        stop   (not a directed acyclic graph)

    mark n with a temporary mark

    for each node m with an edge from n to m do
        visit(m)

    remove temporary mark from n
    mark n with a permanent mark
    add n to head of L
```

## Bubble sort
- Runtime Average: O(n^2)
- Runtime Worst: O(n^2)
- Memory Worst: O(1)
- Algorithm: Start at the beginning of the array and swap the first two elements if the first is greater
than the second. Then, go to the next pair, and so on, continuously making sweeps of the array until it is
sorted. In doing so, the smaller items slowly "bubble" up to the beginning of the list.

```c++
void BubbleSort(vector<int> &v)
{
    int n = v.size();
    for (int i = 0; i < n; ++i)
    {
        bool hasSwaps = false;
        for (int j = 1; j < n-i; ++j)
        {
            if (v[j-1] > v[j])
            {
                swap(v[j-1], v[j]);
                hasSwaps = true;
            }
        }
        
        if (!hasSwaps) 
        {
            break;
        }
    }
}
```


## Selection sort
- Runtime Average: O(n^2)
- Runtime Worst: O(n^2)
- Memory Worst: O(1)
- Algorithm: Find the smallest element using a linear scan and move it to the front (swapping it with the front element). 
Then, find the second smallest and move it again doing a linear scan. Continue doing this until all the elements are in place.

```c++
void SelectionSort(vector<int> &v)
{
    int n = v.size();
    for (int i = 0; i < n-1; ++i)
    {
        auto minIter = min_element(v.begin()+i, v.end());
        swap(v[i], *minIter);
    }
}
```


## Insertion sort
- Runtime Average: O(n^2)
- Runtime Worst: O(n^2)
- Memory Worst: O(1)
- Algorithm: Separate array into sorted and non sorted parts. 
Iterate through array, taking each element and inserting them into the right position in the sorted array part.

```c++
void InsertionSort(vector<int> &v)
{
    int n = v.size();
    for (int i = 1; i < n; ++i)
    {
        int j = i;
        int num = v[j];
        while (j > 0 && v[j-1] > num)
        {
            v[j] = v[j-1];
            --j;
        }
        v[j] = num;
    }
}
```


## Counting Sort
- Runtime Average: O(n+k)
- Runtime Worst: O(n+k)
- Memory Worst: O(k)
- Input is from a small range of integer, i.e 0 to k-1
- Algorithm: Use an array (A) to count number of counts for each key. 
Sum each element in A with the previous element to get where the key ends in index.
Loop through original array from the back, for each element, get from A its index and decrement the index in A for future occurrence.
  - Has traverse original array in reverse order for the sort to be stable.


## Bucket Sort
- Runtime Average: O(n)
- Runtime Worst: O(n^2)
- Memory Worst: O(n)
- Input data should be from a uniform distribution (i.e 0 to 100).
- Algorithm: Bucket sort, or bin sort, is a sorting algorithm that works by distributing the elements of an array into a number of buckets. 
Each bucket is then sorted individually, either using a different sorting algorithm, or by recursively applying the bucket sorting algorithm.
  - Note that the individual sort here is usually constant because if the data is uniformly distributed, each bucket would have <= <constant> items.


## Radix Sort
- Runtime Average: O(kn)
- Runtime Worst: O(kn)
- Memory Worst: O(1)
- Algorithm: Sorting algorithm for integers that takes advantage of the fact that integers have a finite number of bits. 
In radix sort, we iterate through each digit of the number, grouping numbers by each digit. 
Think of it as counting sort on each digit of the input separately.


## Heap Sort
- Runtime Average: O(nlogn)
- Runtime Worst: O(nlogn)
- Memory Worst: O(1)
- Algorithm: Build max heap, remove max, heapify, repeat until heap is empty.

