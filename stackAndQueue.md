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
  - [5. Infix to Postfix Conversion 4⭐](#5-infix-to-postfix-conversion-4)
    - [Approach](#approach-3)
  - [6. Infix To Prefix Conversion 4⭐](#6-infix-to-prefix-conversion-4)
    - [Approach](#approach-4)
  - [7. Postfix to Infix Conversion 4⭐](#7-postfix-to-infix-conversion-4)
    - [Approach](#approach-5)
  - [8. Prefix to Infix Conversion 3⭐](#8-prefix-to-infix-conversion-3)
    - [Approach](#approach-6)
  - [9. Postfix to Prefix Conversion 3⭐](#9-postfix-to-prefix-conversion-3)
    - [Approach](#approach-7)
  - [10. Prefix to Postfix Conversion 3⭐](#10-prefix-to-postfix-conversion-3)
    - [Approach](#approach-8)
  - [11. Next Greater Element - I 3⭐](#11-next-greater-element---i-3)
    - [Approach](#approach-9)
  - [11. Next Greater Element - II 2⭐](#11-next-greater-element---ii-2)
    - [Approach](#approach-10)
  - [12. Next Smaller Element 4⭐](#12-next-smaller-element-4)
    - [Approach](#approach-11)
  - [13. Number of NGEs to the right 3⭐](#13-number-of-nges-to-the-right-3)
    - [Approach](#approach-12)
  - [14. Trapping Rainwater 3⭐](#14-trapping-rainwater-3)
    - [Approach - I](#approach---i)
    - [Approach - II](#approach---ii)
  - [15. Sum of subarray minimum 2⭐](#15-sum-of-subarray-minimum-2)
    - [Approach](#approach-13)
  - [16. Astroid Collison 3⭐](#16-astroid-collison-3)
    - [Approach](#approach-14)

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

## 5. Infix to Postfix Conversion 4⭐
- **Link** -> https://www.geeksforgeeks.org/problems/infix-to-postfix-1587115620/1
- **Difficulty** -> MEDIUM
### Approach
1. We iterate througn each char of the string, maintain and ans string and stack st
2. If the char is operand add it to string
3. If the char is oppening bracket push it into stack
4. If the char is closing bracket add the st.top() to answer and pop, don't miss to pop the openning bracket at the last
5. Else it is operator check it's priority with st.top() cond: **((precision(c) < precision(st.top()) || (precision(c) == precision(st.top()) && c != '^')))** if true add st.top() to ans and pop after the end of for loop push the operator into the stack
6. After complete iteration of the for loop add st.top() to the answer until stack is empty return ans
7. Complexity:
     - `TIme` -> *O(n): outer loop + O(n): inner while loops*
     - `Space` -> *O(n)*: stack space
8. [To Table Of Content](#table-of-content)

## 6. Infix To Prefix Conversion 4⭐
- **Link** -> https://www.geeksforgeeks.org/problems/infix-to-prefix-notation/1
- **Difficulty** -> MEDIUM
### Approach
1. Reverse the provided expression 
2. The further code is just same is infixToPostfix() expression each and every step just an small change of condition is else part
3. If the operator is `^` and the st.top() is ^ as well pop it and add the stack, there cant be two ^ in stack
4. Else use the condition: **precision(c) < precision(st.top()) **, point to be noted only less than
5. At end reverse the ans once to get the required prefix expression
6. Complexity:
     - `TIme` -> *O(n): outer loop + O(n): inner while loops + O(2n): reverse the string*
     - `Space` -> *O(n)*: stack space
7. [To Table Of Content](#table-of-content)

## 7. Postfix to Infix Conversion 4⭐
- **Link** -> https://www.geeksforgeeks.org/problems/postfix-to-infix-conversion/1
- **Difficulty** -> MEDIUM
### Approach
1. We iterate through an for loop for each charchter and maintain an stck st
2. If the char is operand push it into the stack
3. If the char id operator pop the top1 an top2 from the stack add them in an temp string like `"(" + t2 + c + t1 + ")"`(here c is the operator) and push the string into the stack
4. Point to mention declare the stack as an collection of string and while push single char into the stack push it like `st.push(string(1, c))`
5. At the end return the st.top() as the answer
6. Complexity:
     - `Time` -> *O(n): outer loop + O(n): may need to add string of size n*
     - `Space` -> *O(n)*: stack space
7. [To Table Of Content](#table-of-content)

## 8. Prefix to Infix Conversion 3⭐
- **Link** -> https://www.geeksforgeeks.org/problems/prefix-to-infix-conversion/1
- **Difficulty** -> MEDIUM
### Approach
1. Same as we do for postficToInfix just chage in formula while adding the string use `"(" + t1 + exp[i] + t2 + ")"`
2. Other then that whole process is same return st.top() as the answer
3. Complexity:
     - `Time` -> *O(n): outer loop + O(n): may need to add string of size n*
     - `Space` -> *O(n)*: stack space
4. [To Table Of Content](#table-of-content)

## 9. Postfix to Prefix Conversion 3⭐
- **Link** -> https://www.geeksforgeeks.org/problems/postfix-to-prefix-conversion/1
- **Difficulty** -> MEDIUM
### Approach
1. We will iterate through whole expression and maintain an stack st
2. If the char is operand push it into the stack
3. Else pop the top1 and top2 elements of the stack add them like `c + t2 + t1`(c is the operator) push it into the stack
4. Take same precautiosn while pushing single char into the stack using `st.push(string(1, c))`, return st.top() as answer
5. Complexity:
     - `Time` -> *O(n): outer loop + O(n): may need to add string of size n*
     - `Space` -> *O(n)*: stack space
6. [To Table Of Content](#table-of-content)

## 10. Prefix to Postfix Conversion 3⭐
- **Link** -> https://www.geeksforgeeks.org/problems/prefix-to-postfix-conversion/1
- **Difficulty** -> MEDIUM
### Approach
1. Just same process as we seen in conversion of postfixToPrefix just with an simple change in adding string
3. To add the top1 and top2 use `t1 + t2 + exp[i]`
3. Take precautions while adding single char, retuen st.top() as answer
4. Complexity:
     - `Time` -> *O(n): outer loop + O(n): may need to add string of size n*
     - `Space` -> *O(n)*: stack space
5. [To Table Of Content](#table-of-content)

## 11. Next Greater Element - I 3⭐
- **Link** -> https://leetcode.com/problems/next-greater-element-i/submissions/1868363525/
- **Difficulty** -> MEDIUM
### Approach
1. Here we are using `Monotonic Stack` all the elements we add into the stack are in specific array
2. We use unordered_map `mp` to map the next gretest element and vector `nge` to store the ans fot the subarray
3. We start from the last, at the very start of loop we remove all the element from stack who are smaller or equal to the current element
4. If the stack is empty at the the nums2[i]th pos into the mp we insert -1, else we insert the st.top()
5. At the end of iteration we push the current element into the stack
6. As in the very start we remove the all the smaller element than the current num to maintain the decreasing sequence of numbers which is `Monotonix Stack`
7. In the another for loop we iterate from 0 -> m-1 and push the nge[i] = mp[nums1[i]], leading to required ans
8. Complexity:
     - `Time` -> *O(2n)*: to generate the mp + *O(m)*: to push the nge into the ans
     - `Space` -> *O(n)*: to store mp + *O(n)*: stack space + *O(n)*: to store the answer
9. [To Table of Content](#table-of-content)

## 11. Next Greater Element - II 2⭐
- **Link** -> https://leetcode.com/problems/next-greater-element-ii/submissions/1868492885/
- **Difficulty** -> MEDIUM
### Approach
> If the question about circular array double the array hypothetically iterate 2n-1 -> 0 vice versa while using use i%n
1. We will use the concept of circulat array by hypothetically doubling the array
2. Same process as the last question empty the stack the until st.top() is bigger than current element
3. If the stack is empty push -1 in ans else push st.top() into the answer
4. At the end of iteration push the current element into the stack
5. Complexity:
     - `Time` -> *O(4n)*: to iterate through each element twice and push and pop from stack twice as n
     - `Space` -> *O(2n)*: stack space + *O(n)*: to store the answer
6. [To Table of Content](#table-of-content)

## 12. Next Smaller Element 4⭐
- **Link** -> https://www.geeksforgeeks.org/problems/immediate-smaller-element1142/1
- **Difficulty** -> EASY
### Approach
1. Same as Question no 10. Next Greter element but in the opposite way
2. We will empty the stack until the st.top() is smaller than the current element
3. If the stack is empty push -1 into the answer, else push st.top()
4. At the end of iteration push the current element into the stack
5. Complexity:
     - `Time` -> *O(2n)*: to compute and store the gte n for iteration n for push and pop operation in stack
     - `Space` -> *O(n)*: stack space + *O(n)*: to store the answer
6. [To Table of Content](#table-of-content)

## 13. Number of NGEs to the right 3⭐
- **Link** -> https://www.geeksforgeeks.org/problems/number-of-nges-to-the-right/1
- **Difficulty** -> Easy
### Approach
> Lookout for the optmal approach, this question can't be solved usng monotonic stack lonely it is optimized with the help of high level algorithm
1. The absolute brute force approach is we loop into the indices array 
2. Inside it we loop from the pos it contains till the end of the arr and maintain the counter to count the nge
3. At the end we push the count into the ans 
4. Complexity:
     - `Time` -> *O(n * m)*
     - `Space` -> *O(n)*: to store the answer
5. [To Table of Content](#table-of-content)

## 14. Trapping Rainwater 3⭐
- **Link** -> https://leetcode.com/problems/trapping-rain-water/submissions/1869184349/
- **Difficulty** -> HARD
### Approach - I
1. We will do some pre computation of prefix ans postfix
2. The prefix array will contain the max until that element from the left
3. The postfix array will contain the max until that element from the right
4. We will iterate through each element store the lMax from prefix[i] and rmax from postfix[i]
5. The unit of water can be stored will be min(lmax, rmax) - arr[i] add those to the ans
6. Complexity:
     - `Time` -> *O(2n)*: to precompute prefix ans postfix + *O(n)*: actual calculation of unit of water
     - `Space` -> *O(2n)*: to store the prefix as postfix
### Approach - II
1. We will maintain two pointers and iterate through whole array through them
2. Decide which side to proceed using `arr[l] <= arr[r]`
3. In left we see if scope to store the water and do `total += lMax - arr[l]`, else store lMax = arr[i] and move l++
4. In right we do the same as we perform into the left check store using `total += rMax - arr[r]`, else store rMax = arr[i] and move r++
5. Complexity:
     - `Time` -> *O(n)*
     - `Space` -> *O(1)*
6. [To Table of Content](#table-of-content)

## 15. Sum of subarray minimum 2⭐
- **Link** -> https://leetcode.com/problems/sum-of-subarray-minimums/description/
- **Difficulty** -> MEDIUM
### Approach
1. Looking at the problem a bit different way we have to find that specifc element can contribute in how many sub Array as smallest
2. We will find the nse(next smallest elemtn) to right and pse(previous smallest elemtn) to right for each specifc element
3. Those will be boundary of the that element for contributation
4. We can calculate the ans using `left = i - pse[i];` and `right = nse[i] - i` using those total can be calculated like `total = (total + ((right * left * 1LL * arr[i]) % mod)) % mod` here **mod = 1e9 + 7**
5. We would calculate the nse ans pse as usual we found in *11. Next Greater Element*
6. A small in finding pse would be insted of removing element >= we will only remove them if they are > element
7. This alteration is used to avoid mis calculation in test case like [1, 1], to avoid considering same sub array twice
8. Complexity:
     - `Time` -> *O(2n)*: to find nse + *O(2n)*: to find pse + *O(n)*: to calculate final ans
     - `Space` -> *(2n)*: for nse and stack + *O(2n)*: for pse and stack
9. [To Table of Content](#table-of-content)

## 16. Astroid Collison 3⭐
- **Link** -> https://leetcode.com/problems/asteroid-collision/submissions/1870059716/
- **Difficulty** -> MEDIUM
### Approach
1. We will iterate through each element into the array
2. If the element is positive directly push it into the stack
3. else `while (!st.empty() && st.top() > 0 &&st.top() < abs(arr[i]))` pop the top element
4. At the end perform some check to handle edge case like if `st.top() == ans(arr[i])` pop the element if the stack is empty or st.top() is -ve push the element into the stack
5. Complexity:
     - `Time` -> *O(n)*: external for loop + *O(n)*: to pop using interanl while loop
     - `Space` -> *O(n)*: stack space + *O(n)*: to store the answer
6. [To Table of Content](#table-of-content)