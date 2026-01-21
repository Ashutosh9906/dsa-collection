# SPECIALS

## Table of content
- [SPECIALS](#specials)
  - [Table of content](#table-of-content)
  - [Sell upto 2 \[MIN HEAP\] 2⭐](#sell-upto-2-min-heap-2)
    - [Approach](#approach)

## Sell upto 2 [MIN HEAP] 2⭐
- **Link** -> https://www.codechef.com/START222D/problems/SELL2
### Approach
1. As we have to get the maximum profit we will sell the maximum watches on the days having more price and only one watch on the smaller prices
2. We will use min heap concept, iterate from 0 -> n we will push the element into the heap twice implying two slots of watches can be selled on that day and immediately pop the element
3. The element which will be popped is the smallest element in the heap so all the the smallest price as the day passes we pe popped out
4. We are doing 2 push and 1 pop resulting n elements to be push into the heap, the sum of element that remains into the heap is the required max profit we can get
5. Complexity
    - `Time` -> *O(3 X nlog)*: each push and pop operation required logn complexity + *O(nlogn)*: to pop the root from heap and adding sum
    - `Space` -> *O(n)*: heap space
6. [To Table Of Content](#table-of-content)