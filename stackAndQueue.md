# Stack And Queue

## Table of content
- [Stack And Queue](#stack-and-queue)
  - [Table of content](#table-of-content)
  - [1. Implement Stack using Queue 4⭐](#1-implement-stack-using-queue-4)
    - [Approach](#approach)
  - [2. Implement Queue using Stacks 4⭐](#2-implement-queue-using-stacks-4)
    - [Approach 1](#approach-1)
    - [Approach 2](#approach-2)

## 1. Implement Stack using Queue 4⭐
- **Link** -> https://leetcode.com/problems/implement-stack-using-queues/description/
- **Medium** -> EASY
### Approach
1. `push()` at first push the element in the queue, iterate from 1 -> n-2 perform q.push(q.front) and q.pop
2. `POP()` to pop element it is same as pop operation as queue
3. `top()` to top element return the front from the queue
4. `empty()` maintain the size if 0 return true if more than 0 return 1
5. Complexity:
    - `Time` -> *O(n)*: `push()`, *O(1)*: `pop()`, `top()`, `empty()`
    - `Space` -> O(1)
6. [To Table Of Content](#table-of-content)

## 2. Implement Queue using Stacks 4⭐
- **Link** -> https://leetcode.com/problems/implement-queue-using-stacks/description/
- **Medium** -> EASY
### Approach 1
1. `push()` we can maintain two stack whenever we want to push and element we first copy all the elements from s1 to s2 -> s1.push() -> from s2 to s1
2. `pop()` same as pop operation of stack
3. `peek()` same as top operation of stack
4. `empty()` maintain an size if 0 return true if more than 0 return 1
5. Complexity:
    - `Time`: *O(n)*: `push()`, *O(1)*: `pop()`, `peek()`, `empty()`
    - `Space`: *O(n)*
6. Drawback to many operation if s1 is to big ( not preferable )
### Approach 2
1. `push()` maintain two stack push into s1 
2. `pop()` if s2 is empty transfer all elements from s1 to s2 and return remove top, if not empty just remove the top element
3. `peek()` same as pop if s2 is empty transfer and return top, if not empty just return top
4. `empty()` maintain an size if 0 return true if more than 0 return 1
5. Complexity:
    - `Time` -> *O(n)*: `pop()`, `peek()` **( Occassionally )**, *O(1)*: `push()`, `empty()`
    - `Space` -> *O(n)*
6. [To Table Of Content](#table-of-content)