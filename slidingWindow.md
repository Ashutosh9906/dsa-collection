# Sliding Windoe & Two Pointer Combined Problem

## Table of content
- [Sliding Windoe \& Two Pointer Combined Problem](#sliding-windoe--two-pointer-combined-problem)
  - [Table of content](#table-of-content)
  - [1. Longest Substring Without Repeating Characters 4⭐](#1-longest-substring-without-repeating-characters-4)
    - [Approach](#approach)
  - [2. Max Consecutive Ones III 3⭐](#2-max-consecutive-ones-iii-3)
    - [Approach](#approach-1)
  - [3. Fruit into Basket 4⭐](#3-fruit-into-basket-4)
    - [Approach](#approach-2)
  - [5. Binary Subarrays With Sum 3⭐](#5-binary-subarrays-with-sum-3)
    - [Approach](#approach-3)

## 1. Longest Substring Without Repeating Characters 4⭐
- **Link** -> https://leetcode.com/problems/longest-substring-without-repeating-characters/description/
- **Difficulty** -> MEDIUM
### Approach
1. We use two pointer method to find max len of the string wiht no duplicates, we initialize start and end to 0, and maxLen to 1, and hash of size 256 initialized to -1
2. We iterate through an while loop until end reaches n
3. At the start we check whether the char already present into the string by checking in hash table if present and it's location is further to start then update start = hash[s[start]] + 1
4. If not present calculate the len = left - right + 1 and update maxLen and increment the pointer
5. Complexity:
    - `Time` -> *o(n)*: to iterate through each element
    - `Space` -> *O(256)*: size of hash table
6. [To Table Of Content](#table-of-content)

## 2. Max Consecutive Ones III 3⭐
- **Link** -> https://leetcode.com/problems/max-consecutive-ones-iii/description/
- **Difficulty** -> MEDIUM
### Approach
1. We will use sliding window with the help variables like start, end as pointers maxSize to store the ans, zeros to count number of 0s
2. If the arr[end] is 0 increase the pointer of the zeros
3. If at any moment count of zeros cross the limit k then if the element where currenly start is 0 then decrement the zeros count and increment the start pointer
4. If the count of 0s zeros is leff then or equal to the limit k then only update the answer maxSize, at the end of all iteration return maxSize
5. Complexity:
    - `Time` -> *O(n)*: to iterate through arr
    - `Space` -> *O(1)*
6. [To Table Of Content](#table-of-content)

## 3. Fruit into Basket 4⭐
- **Link** -> https://leetcode.com/problems/fruit-into-baskets/description/
- **Difficulty** -> MEDIUM
### Approach
1. Same approach as above, we will use unordered_map to track fruits and two pointers, iterate the end pointer util less than arr.size()
2. Increment the value at fruit by 1 mp[arr[end]]++
3. If the size of map exceeds 2 will decrement the freq of the start mp[arr[start]]--
4. If at any moment the freq of the start became 0 remove it fromt the map mp.erase(arr[start])
5. While altering the answer for maxFruit always check whether map have less than or equal to 2 elements then only update the answer
6. Complexity:
    `Time` -> *O(n)*: for the main outer loop
    `Space` -> *O(3)*: constant map size at max 3 elemets
7. [To Table Of Content](#table-of-content)

## 5. Binary Subarrays With Sum 3⭐
- **Link** -> https://leetcode.com/problems/binary-subarrays-with-sum/description/
- **Difficulty** -> HARD
### Approach
> The optimal solution for above question is same as prefix sum question, but as externally mentioned the array will only contanin 1s and 0s then there is an scope of improvement for space complexity 
1. We will sove using a bit different compared to above solution, we use variables like start, end, sum, count = 0 fo sliding window
2. At the very start we add the element to the sum, if the sum is greater the goal then remove the arr[start] from the sum and move the start pointer
3. If the sum <= to the goal then add the len (end - start + 1) to the count variable
4. If we do this for goal and goal-1 there difference wll give the required answer, just an edge case if the goal < 0 return 0
5. Complexity:
  - `Time` -> *O(4n)*: 2n required of one function, n for external while loop and n for interanl while to move start pointer
  - `Space` -> *O(1)*
6. [To Table Of Content](#table-of-content)