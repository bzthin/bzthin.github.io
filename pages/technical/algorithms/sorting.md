---
layout: page_with_side_nav
title: Sorting
permalink: /algorithms/sorting/
---

# Sorting
This page contains sorting information. 


## Bubble sort
- Runtime Average: O(n^2)
- Runtime Worst: O(n^2)
- Memory: O(1)
- Algorithm: Start at the beginning of the array and swap the first two elements if the first is greater
than the second. Then, go to the next pair, and so on, continuously making sweeps of the array until it is
sorted. In doing so, the smaller items slowly "bubble" up to the beginning of the list.

## Selection sort
- Runtime Average: O(n^2)
- Runtime Worst: O(n^2)
- Memory: O(1)
- Algorithm: Find the smallest element using a linear scan and move it to the front (swapping it with the front element). 
Then, find the second smallest and move it again doing a linear scan. Continue doing this until all the elements are in place.

## Insertion sort
- Runtime Average: O(n^2)
- Runtime Worst: O(n^2)
- Memory: O(1)
- Algorithm: Separate array into sorted and non sorted parts. 
Iterate through array, taking each element and inserting them into the right position in the sorted array part.

## Merge Sort
- Runtime Average: O(nlog(n))
- Runtime Worst: O(nlog(n))
- Memory: Depends
- Algorithm: Divides the array in half until it cannot be divided, start merging halves together while sorting them.

## Quick Sort
- Runtime Average: O(nlog(n))
- Runtime Worst: O(n^2)
- Memory: O(log(n))
- Algorithm: Pick a random element and partition the array, such that all numbers that are less than the
partitioning element come before all elements that are greater than it. 
Perform the partition on the left and right subparts of the array.

## Radix Sort
- Runtime Average: O(kn)
- Runtime Worst: O(kn)
- Memory: O(1)
- Algorithm: Sorting algorithm for integers that takes advantage of the fact that integers have a finite number of bits. 
In radix sort, we iterate through each digit of the number, grouping numbers by each digit. 

## Bucket Sort
- Runtime Average: O(n)
- Runtime Worst: O(n^2)
- Memory: O(n)
- Algorithm: Bucket sort, or bin sort, is a sorting algorithm that works by distributing the elements of an array into a number of buckets. 
Each bucket is then sorted individually, either using a different sorting algorithm, or by recursively applying the bucket sorting algorithm.