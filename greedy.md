# GREEDY ALGORITHM

## Table of content
- [GREEDY ALGORITHM](#greedy-algorithm)
  - [Table of content](#table-of-content)
  - [1. Assign Cookies 4⭐](#1-assign-cookies-4)
    - [Approach](#approach)
  - [2. Fractional Knapsack 3⭐](#2-fractional-knapsack-3)
    - [Approach](#approach-1)

## 1. Assign Cookies 4⭐
- **Link** -> https://leetcode.com/problems/assign-cookies/description/
- **Difficulty** -> EASY
### Approach
1. We want to fulfill the greed of mostly every child so we have distribute the cokkies in greedly 
2. For an children with greed x we will find out any cookie y >= x and fulfill his greed insted of just giving one by one
3. We will sort both the array of children and cookie, assign pointer in both array to iterate until we reach such an point there does not exit such a cookie that will fullfill the greed of child x
4. Complexity:
    - `Time` -> *O(nlogn)*: to sort the children and cookies array + *O(n)*: to fullfill the greed
    - `Space` -> *O(1)*  
5. [Table of Content](#table-of-content)

## 2. Fractional Knapsack 3⭐
- **Link** -> https://www.geeksforgeeks.org/problems/fractional-knapsack-1587115620/1
- **Difficulty** -> MEDIUM
### Approach
1. We want to maximize the value and we can take fractional part of the weights relative to the value, confusion arises take not take and even further take in whole or the fractional part
2. The key is the unitValue of value to weight like weight(20), value(100) then unit value will be value/weight = 5
3. Based on the unitValue we will take the weights, we will take from heights unitValue to the lowest until the capacity is fullfilled
4. For largest unitValue if we can accomodate in whole we will take else we take the fraction part at exit the loop
5. For getting the largest unitValue we will heap with defination as `priority_queue<pair<double, pair<int, int>>> maxHeap` { unitValue, { val[i], wt[i] } }
6. Complexity:
    - `Time` -> *O(nlogn)*: to push all the elements into the heap + *O(nlogn)*: to pop and fullfill the capacity
    - `Space` -> *O(n)*: heap space
7. [Table of Content](#table-of-content)