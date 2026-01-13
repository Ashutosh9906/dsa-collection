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
  - [4. longest repeating character replacement 2⭐](#4-longest-repeating-character-replacement-2)
    - [Approach](#approach-3)
  - [5. Binary Subarrays With Sum 2⭐](#5-binary-subarrays-with-sum-2)
    - [Approach](#approach-4)
  - [6. Count number of Nice Subarrays 4⭐](#6-count-number-of-nice-subarrays-4)
    - [Approach](#approach-5)
  - [7. Number of Substrings Containing All Three Characters 3⭐](#7-number-of-substrings-containing-all-three-characters-3)
    - [Approach](#approach-6)
  - [8. Maximum Points You Can Obtain from Cards 3⭐](#8-maximum-points-you-can-obtain-from-cards-3)
    - [Approach](#approach-7)

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

## 4. longest repeating character replacement 2⭐
- **Link** -> https://leetcode.com/problems/longest-repeating-character-replacement/description/
- **Difficulty** -> HARD
### Approach
1. We will use sliding we window to compute the max len, we will maintain an hash array of size 26 to sotre the freq of each char, maxFreq to store the freq of an char and maxLen to store the ans
2. We will use left and right pointers for computation and loop until right reaches arr.size()
3. At the very star we will incrment the counter hash[arr[right] - 'A']++ and update the maxFreq as max(maxFreq, hash[arr[right] - 'A'])
4. The number of char that can be changed will be the Len(right - left + 1) - maxFreq 
  - `if(change > k)` -> then we can remove the char from the start moving left poiner in an while loop and also decrement in the hash array, we also have to compute the maxFreq which will need an for loop from 0 -> 26
  - `if(change < k)` -> we will update the maxLen variable with max(maxLen, (left-right+1))
5. There are some scope of optimization in the above approach as it takes *O(26 X (n + n))* time complexity
  - Insted of an while loop to increment left pointer we will increment is once as we done in the previous problems
  - Also we won't update the maxFreq variable each time as we move the left pointer, because we want an larger string length we have increment the size keeping the maxFreq stable 
6. Complexity:
  - `Time` -> *O(n)*: for external while loop 
  - `Space` -> *O(26)*: for hash array to store the freq of char
7. [To Table Of Content](#table-of-content)

## 5. Binary Subarrays With Sum 2⭐
- **Link** -> https://leetcode.com/problems/binary-subarrays-with-sum/description/
- **Difficulty** -> HARD
### Approach
> The optimal solution for above question is same as prefix sum question, but as externally mentioned the array will only contanin 1s and 0s then there is an scope of improvement for space complexity 
1. We will sove using a bit different compared to above solution, we use variables like start, end, sum, count = 0 fo sliding window
2. We will think in an bit different way we will try for all the subArrays with sum <= goal
  - Ex. [1 0 0 1 1 0]
  - at fist sum will be 1, moving further sum will be same as num is 0 which means we come accross an such an element after adding it the sum does not change so the number of subArrays will be [1] and [1 0]
  - Moving next sum still does not change so the number of sub array with sum <= goal will be like [1], [1 0], [1 0 0]
  - So each time while sum <= goal we will add (left - right + 1) to the count, and if the sum exceeds the goal shorten it from the start
  - Also there is an edge case so if the `goal is 0 then return 0`
3. We change the count only when the sum <= k so that there is no need for the while loop to move left pointer
4. So now if we simply do is `func(arr, goal) - func(arr, goal-1)` this will end up returning the all the subArray with sum = goal
5. Complexity:
  - `Time` -> *O(4n)*: 2n required of one function, n for external while loop and n for interanl while to move start pointer
  - `Space` -> *O(1)*
6. [To Table Of Content](#table-of-content)

## 6. Count number of Nice Subarrays 4⭐
- **Link** -> https://leetcode.com/problems/count-number-of-nice-subarrays/description/
- **Difficulty** -> HARD
### Approach
1. Just same as apove by an little bit of observation we can consider the odd numbers be `1` and even numbers as `0`
2. Then this question will be sonverted as the question above just while adding or substracting the sum mod it `sum += arr[end]%2` vice versa
3. Complexity:
  - `Time` -> *O(4n)*: 2n required of one function, n for external while loop and n for interanl while to move start pointer
  - `Space` -> *O(1)*
4. [To Table Of Content](#table-of-content)

## 7. Number of Substrings Containing All Three Characters 3⭐
- **Link** -> https://leetcode.com/problems/number-of-substrings-containing-all-three-characters/description/
- **Difficulty** -> HARD
### Approach
1. In this question we will apply sliding window but in an different way
2. Ex. bbacba, think like if we are standing at b at pos 4 looking behind do we have all the char 
3. We will store the there lastseen location in an hash array considering we are standing at b how many subarray can be formed acb, bacb, bbacb only behind it which will min({hash[0], hash[1], hash[2]}) + 1
4. With such approach we will iterate through an for loop from i -> n, hash array of size 3 initialized as -1
5. Each time we will update the lastSeen loc in the hash array, if all the elements are present != -1 then `count = count + 1 + min({hash[0], hash[1], hash[2]});`
6. Complexity:
  - `Time` -> *O(n)*: external for loop
  - `Space` -> *O(3)*: hash array of constant size 3
7. [To Table Of Content](#table-of-content)

## 8. Maximum Points You Can Obtain from Cards 3⭐
- **Link** -> https://leetcode.com/problems/maximum-points-you-can-obtain-from-cards/description/
- **Difficulty** -> MEDIUM
### Approach
1. First we will sumup k elements form the left side and store it in leftSum, assign maxSum as leftSum, and declare an rightSum variable
2. Inside an anothre for from k-1 -> 0 we will substract i element from leftSum and maintain and right = n-1 pointer add the right element to rightSUm
3. The maxSum = max(maxSum, leftSum+rightSum);
4. Complexity:
  - `Time` -> *O(2k)*: one for computing leftSum and one for removing left and adding from right
  - `Space` -> *O(1)*
5. [To Table Of Content](#table-of-content)