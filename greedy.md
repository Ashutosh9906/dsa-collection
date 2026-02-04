# GREEDY ALGORITHM

## Table of content
- [GREEDY ALGORITHM](#greedy-algorithm)
  - [Table of content](#table-of-content)
  - [1. Assign Cookies 4⭐](#1-assign-cookies-4)
    - [Approach](#approach)
  - [2. Fractional Knapsack 3⭐](#2-fractional-knapsack-3)
    - [Approach](#approach-1)
  - [3. Minimum number of coins 4⭐](#3-minimum-number-of-coins-4)
    - [Approach](#approach-2)
  - [4. Lemonade change 4⭐](#4-lemonade-change-4)
    - [Approach](#approach-3)

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

## 3. Minimum number of coins 4⭐
- **Link** -> https://www.geeksforgeeks.org/problems/-minimum-number-of-coins4426/1
- **Difficulty** -> HARD
### Approach
1. We want the minium number of change to be used to generate to get the sum of given number
2. We have notes from {10, 5, 2, 1}, we will divide the n by 10 store it quotient into the answer and n = n%10 we will perfrom this operation with all the changes we have
3. Complexity:
    - `Time` -> *O(1)*
    - `Space` -> *O(1)*
4. [Table of Content](#table-of-content)

## 4. Lemonade change 4⭐
- **Link** -> https://leetcode.com/problems/lemonade-change/description/
- **Difficulty** -> EASY
### Approach
1. We are running an lemonade shop and we have to mange all the bills and return true if we are able to attain the customer by returning proper change else false
2. We will keep track on number of bills of 5$ and 10$, if the given bill is 5$ just increment the 5$ counter, if it is an 10$ counter increment the 10$ counter and decrement the 5$ counter by 1, if the it is 20$ we have two options give 3 * 5$ or give 10$ + 5$ based on which we will do the inncrement and decrement
3. If for any of the above exchange we don't have enough bills straight away return false
4. Complexity:
    - `Time` -> *O(n)*: to exchange bills
    - `Space` -> *O(1)*
5. [Table of Content](#table-of-content)