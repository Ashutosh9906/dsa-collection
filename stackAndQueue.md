# Stack And Queue

## Table of content
- [Stack And Queue](#stack-and-queue)
  - [Table of content](#table-of-content)
  - [1. Implement Stack using Queue 4⭐](#1-implement-stack-using-queue-4)
    - [Approach](#approach)
  - [2. Implement Queue using Stacks 4⭐](#2-implement-queue-using-stacks-4)
    - [Approach 1](#approach-1)
    - [Approach 2](#approach-2)
  - [3. Check for balanced paranthesis 3⭐](#3-check-for-balanced-paranthesis-3)
    - [Approach](#approach-1)
  - [4. Min Stack 2⭐](#4-min-stack-2)
    - [Approach](#approach-2)

## 1. Implement Stack using Queue 4⭐
- **Link** -> https://leetcode.com/problems/implement-stack-using-queues/description/
- **Difficulty** -> EASY
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
- **Difficulty** -> EASY
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

## 3. Check for balanced paranthesis 3⭐
- **Link** -> https://leetcode.com/problems/valid-parentheses/description/
- **Difficulty** -> EASY
### Approach
1. If is an oppening bracket push into an stack
2. If it is an closing bracket check at st.top() if it matches an opening bracket if no return false either continue
3. If after all the interations stack is not empty return false
4. If first element is not opening or length of string is 1 return false 
5. Complexity:
     - `Time` -> *O(n)*
     - `Space` -> *O(n)*
6. [To Table Of Content](#table-of-content)

## 4. Min Stack 2⭐
- **Link** -> https://leetcode.com/problems/min-stack/description/
- **Difficulty** -> HARD
### Approach
1. Basic and absolutely neive approach is maintain normal stack, when need minElement scan through while stack TC -> *O(n)*
2. We can use some mathematically formula to perfrom it in tc -> *O(1)*
3. `push()`: 
     1. We maintain and stack and an variable minVal if the stack is empty push into stack and change minVal
     2. If not empty and top element is smaller than the current val just push into stack not change minVal
     3. If current val is smaller than top then push in stack `2 * val * minVal` and change `minVal = val`
4. `pop()`:
     1. If the stack is empty just return
     2. If the top() is smaller than the minVal than change `minVal = 2 * minVal - top()`
     3. If top is bigger than just pop from the stack not change minVal
5. `top()`:
     1. If the top() is smaller than minVal return minVal
     2. Else return top() of stack
6. `minVal()`:
     1. Just return the minVal stored
7. Lookout for overflow use long long for stroing top() and use **2LL** insted of 2 while multypling
8. Complexity:
     - `Time` -> *O(1)*: `push()`, `pop()`, `top()`, `minVal()`
     - `Space` -> *O(n)* -> stack size
9. [To Table Of Content](#table-of-content)