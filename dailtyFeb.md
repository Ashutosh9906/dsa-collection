# February Daily Questions

## Table of Content
- [February Daily Questions](#february-daily-questions)
  - [Table of Content](#table-of-content)
  - [**Leetcode 3010** \[ Divide an Array Into Subarrays With Minimum Cost I \] 4⭐](#leetcode-3010--divide-an-array-into-subarrays-with-minimum-cost-i--4)
  - [Approach](#approach)
  - [**Leetcode 3013** \[Divide an Array Into Subarrays With Minimum Cost II\] 2⭐](#leetcode-3013-divide-an-array-into-subarrays-with-minimum-cost-ii-2)
    - [Approach](#approach-1)

## **Leetcode 3010** [ Divide an Array Into Subarrays With Minimum Cost I ] 4⭐
- **Date** -> 01/02/2026
- **Link** -> https://leetcode.com/problems/divide-an-array-into-subarrays-with-minimum-cost-i/description/
- **Difficulty** -> EASY
## Approach
1. We want to delete the array into three sub-arrays and also include all the elements from the array
2. Thinking of which the first sub-array will always start from the pos 0 we have to decide the second and the third elements stating pos
3. To minimize the cost we will the two minimum elements pos min1 and min2, followed as min1 will always be lesser than the min2
4. At the very beginning we will assign pos 1 and 2 to min1 and min2 respectively as move on further until min2 reaches the last element
5. If we found an element smaller than min1 then min2 will take it's position and min1 will take min2 formerly position
6. Else if the element is only smaller than min2 then just change the min2 position wihout changing the min1
7. Addition of all the elements arr[0] + min1 + min2 will be the required cost to divide the given array into an subarray
8. Complexity:
    - `Time` -> *O(n)*: the for loop to look out for min1 and min2
    - `Space` -> *O(1)*
9. [Table of Content](#table-of-content)

## **Leetcode 3013** [Divide an Array Into Subarrays With Minimum Cost II] 2⭐
- **Date** -> 02/02/2026
- **Link** -> https://leetcode.com/problems/divide-an-array-into-subarrays-with-minimum-cost-ii/description/
- **Difficulty** -> HARD
### Approach
1. Same as yesterday's question the change is the difference between kth subArray's first element position and 2nd subArray's first element should be lesser then or equal to dist, also the sub number of subArray we have is k
2. So the least bit of observation is we have maintain the differnce between the postion less than or equal to dist each time this gives us an hint of sliding window of size dist+1
3. Next thing the cost of creation is the sum of first element of each subArray which we have to minimize so in the that specific window we will take the k-1 smallest element as the starting pos of each subArray
4. As we already took care of the diff of kth and 2nd subArray by taking the k-1 smallest element from the window we would get the asnwer
5. We will be using three function `Insert()`, `Delete()`, `reBalance()` as the operation to get the k-1 min element and an variable windowSum
6. We will use multiset<int> high and multiset<int> low for getting the k-1 smallest element, we will maintain k-1 element in low multiset
7. `Insert()`
    - If the element is greater than ot equal to the smallest element from the high while high is not empty add the element to the high
    - Else the element may one of the smallest element so add it to low and add it's value to windowSum
    - After all the operation give an call to `reBalance()`
8. `Delete()`
    - If the element is present into the low multiset erase it from low and substract from the windowSum
    - Else definetly it will be present into the high multiset remove it from there
    - As decided give an call to `reBalance()`
9. `reBalance`
    - If the high multiset is not empty and low.size() less than k-1 than add the high.begin() (lowest) to the low multiset
    - Else if the size of low more than k-1 than add the low.rbegin() (highest) to the hgih multiset
10. In the main function we will iterate form 1 -> n at the very begining we insert the element into low, if the i-dist-1 exceed's 0 than delte the i-dist-1 element, if the size of low is same as k-1 then record the answer
11. Complexity:
    - `Time` -> *O(log(dist))*: for Insert(), Delete(), reBalance() -> *O(nlog(n))*
    - `Space` -> *O(n)*
12. [Table of Content](#table-of-content)