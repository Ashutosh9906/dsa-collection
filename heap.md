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
  - [5. Kth largest element in an array 4⭐](#5-kth-largest-element-in-an-array-4)
    - [Approach](#approach-4)
  - [6. Kth smallest element in an array 4⭐](#6-kth-smallest-element-in-an-array-4)
    - [Approach](#approach-5)
  - [7. k sorted array 4⭐](#7-k-sorted-array-4)
    - [Approach](#approach-6)
  - [8. Merge k sorted lists 3⭐](#8-merge-k-sorted-lists-3)
    - [Approach](#approach-7)
  - [9. Task Scheduler 2⭐](#9-task-scheduler-2)
    - [Approach](#approach-8)

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

## 5. Kth largest element in an array 4⭐
- **Link** -> https://leetcode.com/problems/kth-largest-element-in-an-array/description/
- **Difficulty** -> MEDIUM
### Approach
1. As we know when we pop an element from the max heap it gives the largest element 
2. so we push all the element into the min staack in pop k times so we will get the kth largest element
3. Complexity:
    - `Time` -> *O(nlogn)*: to push elements into the heap + *O(klogn)*: to pop out k elemets from the heap
    - `Space` -> *O(n)*: heap space
4. [To Table Of Content](#table-of-content) 

## 6. Kth smallest element in an array 4⭐
- **Link** -> https://www.geeksforgeeks.org/problems/kth-smallest-element5635/1
- **Difficulty** -> MEDIUM
### Approach
1. Same as above just change the the max heap to min heap using `priority_queue<int, vector<int>, greater<int>> pq`
2. Same for time complexity as well
3. [To Table Of Content](#table-of-content) 

## 7. k sorted array 4⭐
- **Link** -> https://www.geeksforgeeks.org/problems/k-sorted-array1610/1
- **Difficulty** -> EASY
### Approach
1. use pair<int, int> in the priority_queue as the data type store the arr[i] element ans the pos i itself
2. It will store the elements on the basis of element
3. Into an for loop we can check whether the the current pos and the pos it is when sorted is less than or equal to k
4. Complexity
    - `Time` -> *O(nlogn)*: to push all the elements into the stack + *O(nolgn)*: to verigy the locations of the elements
    - `Space` -> *O(n)*: heap space
5. [To Table Of Content](#table-of-content) 

## 8. Merge k sorted lists 3⭐
- **Link** -> https://leetcode.com/problems/merge-k-sorted-lists/description/
- **Difficulty** -> HARD
### Approach
1. First i transfered all the elements val and there pointer as an pair into the heap, and in the next for loop i pop out element from the heap one by one and formed an new linked list using the existing node
2. To optimize it a bit we can do is push only the head of each linked list into the heap
3. In the second while loop we will pop the element store it in linked list and push it's next node into the heap, this way we can combine all the osrted elements
4. Complexity:
    - `Time` -> *O(klogk)*: to push all the head into the heap + *O(nlogk)*: to pop and store the the linked and also push the next element into the heap
    - `Space` -> *O(k)*
5. [To Table Of Content](#table-of-content) 

## 9. Task Scheduler 2⭐
- **Link** -> https://leetcode.com/problems/task-scheduler/description/
- **Difficulty** -> MEDIUM
### Approach
1. We will count the freq of all the task and store it into an vector
2. We will push all the freq in to the max Heap using priority queue
3. We will be using one queue to calculate the unit os time needed of data type pair<int, int>
4. At first we will pop the element from the heap if is's freq is greater than 0 than we could push it into the queue qhile decresing the freq by one with the time + k at which we can use it again
5. In the queue if the the element in the front have the time_at_availabele as current time than push it's frequenct into the max heap and pop the element from the queue
6. Complexity:
  - `Time` -> *O(n)*: to calculate the freq + *O(n)*: to push all tasks into the heao + *O(n+total_intervals)*: for task scheduling
  - `Space` -> *O(26)*: for all the space used (vector, priority_queue, queue)
7. [To Table Of Content](#table-of-content) 