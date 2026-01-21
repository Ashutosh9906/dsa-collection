# HEAP

## Table Of Content
- [HEAP](#heap)
  - [Table Of Content](#table-of-content)
  - [1. Min heap implementation 4⭐](#1-min-heap-implementation-4)
    - [Approach](#approach)
  - [2. Max heap implementation 4⭐](#2-max-heap-implementation-4)
    - [Approach](#approach-1)
  - [3. Does array represent heap(Max heap) 4⭐](#3-does-array-represent-heapmax-heap-4)
    - [Approach](#approach-2)
  - [4. Convert min heap to max heap 3⭐](#4-convert-min-heap-to-max-heap-3)
    - [Approach](#approach-3)

## 1. Min heap implementation 4⭐
- **Link** -> https://www.geeksforgeeks.org/problems/min-heap-implementation/1
- **Difficulty** -> MEDIUM
### Approach
1. We declare an vector named arr for all the push an pop operation in heap and an size counter initialized to 0, in constructor push -1 as we are practicing heap starting from 1
2. `push()`
    1. Increment the heapSize, push val into the vector assign an temp variable index as heapSize
    2. We just added the new element into the array now we have to palce it to it's correct position
    3. Inside while until index > 1, the parent of the node will be index/2
        - `if` parent is bigger than the index then swap with parent and index = parent
        - `else` element is at the correct position
3. `pop()`
    1. According to the heap rules while poping always remove the root node
    2. We replace the last element with the fist element and decrease the heapSize
    3. Now we remoed the root now we have to place the root element to it's correct element
    4. Inside an while true
        - calculate the left and right node using `left = 2*index`(for 1 based indexing), `right = 2*index + 1`
        - Also maintain and largest temp variable to store the location of largest element initialize it as index
        - `if` left is greater then largest then assign largest as left
        - `if` right is greater then largest which also means right is greater then left assign largest as right
        - `if` largest is changes largest != index then swap the arr[largest] and arr[index] move index to largest
        - `else` break element is at it's correct position
4. Complexity
    - `Time` -> *O(logn)*: for push and peek operation, *O(1)*: for peek and size and the constructor
    - `Space` -> *O(n)*: to form the heap array
5. [To Table Of Content](#table-of-content)

## 2. Max heap implementation 4⭐
- **Link** -> https://www.geeksforgeeks.org/problems/max-heap-implementation/1
- **Difficulty** -> MEDIUM
### Approach 
1. Everything is just same as min heap just swap the operator 
2. [To Table Of Content](#table-of-content)

## 3. Does array represent heap(Max heap) 4⭐
- **Link** -> https://www.geeksforgeeks.org/problems/does-array-represent-heap4345/1
- **Difficulty** -> MEDIUM
### Approach
1. start fromt he index = size/2 as the all the elements ahead of it will be leaf node
2. Calculate the left and right child of the parent node, if at eny moment one of the child is greater then parent return false
3. It none of the if case passes then just decrement the index pointer by 1
4. Complexity
    - `Time` -> *O(n)*: as we are decrementing by 1 for each iteration
    - `Space` -> *O(1)*
5. [To Table Of Content](#table-of-content) 

## 4. Convert min heap to max heap 3⭐
- **Link** -> https://www.geeksforgeeks.org/problems/convert-min-heap-to-max-heap-1666385109/1
- **Difficulty** -> MEDIUM
### Approach
1. To convert the min heap to max heap we will use the logic to heapify any array
2. As an leaf is always an valid heap we will start from size/2 (if 1 based indexing) or size/2 - 1(for 0 based indexing), iterate til index >= 0
3. inside it we will run an while until true
    1. We will calculate the left and right child of the element, by comparision we will get the largest element among left and right
    2. If we get and element larger then current element then swap the arr[index] with the arr[largest] and move index = largest
    3. If we didn't get any largest element then just break through the while loop
4. Complexity
    - `Time` -> *O(n)*
    - `Space` -> *O(1)*
> Checkout the in detail explanation of time complexity to be *O(n)* not *O(nlogn)* may asked in interviews
5. [To Table Of Content](#table-of-content) 