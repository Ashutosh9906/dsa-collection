# RECURSION 

## Table Of Content
- [1. Recursive Implementation of atoi()](#1-recursive-implementation-of-atoi)
- [2. Pow(x, n)](#2-powx-n)
- [3. Count Good numbers](#3-count-good-numbers)
- [4. Sort a stack using recursion](#4-sort-a-stack-using-recursion)

## 1. Recursive Implementation of atoi()
- Link -> https://leetcode.com/problems/string-to-integer-atoi/description/
- Rating -> 2 ⭐
- Difficulty -> **HARD**
### Problem Statement
- Implement the myAtoi(string s) function, which converts a string to a 32-bit signed integer.
- **Whitespace**: Ignore any leading whitespace (" ").
- **Signedness**: Determine the sign by checking if the next character is '-' or '+', assuming positivity if neither present.
- **Conversion**: Read the integer by skipping leading zeros until a non-digit character is encountered or the end of the string is reached. If no digits were read, then the result is 0.
- **Rounding**: If the integer is out of the 32-bit signed integer range [-231, 231 - 1], then round the integer to remain in the range. Specifically, integers less than -231 should be rounded to -231, and integers greater than 231 - 1 should be rounded to 231 - 1.
### Iterative Approach
1. Ignore Leading **WhiteSpaces**
2. If just after the whitespces it is '-', '+', '1 - 9' then only move forward else pass **NULL**
3. Convert the following numeric characters into an integer.
4. Stop when a non-digit character is found.
5. Clamp the result to the **32-bit signed integer range**:
   - If out of range, return `INT_MAX (2³¹ - 1)` or `INT_MIN (-2³¹)`.
6. Complexicity
   - Time -> O(N) 
   - Space -> O(1)
### Recursive Approach
1. Starting is same as **Iterative Approach** ignore the leading white space store the sign
2. Call an **Helper** function with first char after the sign with the sign passed as well
3. In each recursive step 
    - Stop if current char is non-digit.
    - Otherwise, accumulate the value
    - Move to the next index recursively.
4. Return the signed result (clamped to integer limits).
5. Complexicity
    - Time -> O(N)
    - Space -> O(N) -> For recursive stack space
- [To Table Of Content](#table-of-content)

## 2. Pow(x, n) 
- Link -> https://leetcode.com/problems/powx-n/description/
- Rating -> 3 ⭐
- Difficulty -> **MEDIUM**
### Problem Statement
1. mplement pow(x, n), which calculates x raised to the power n (i.e., x<sup>n</sup>).
2. **X** - can be real Number, **n** - negative, zero or positive
### Iterative Approach
1. use simple method like
    - n is even -> (x<sup>n/2</sup>)<sup>2</sup>
    - n is odd -> x*(x<sup>n-1</sup>)
2. Complexicity
    - Time -> O(Log n)
    - Space -> o(1)
### Recursive Approach
1. Same as iterative approach but insted of for for/while loop use recursive calling of same function
2. Complexicity
    - Time -> O(Log n)
    - Space -> o(Log n) -> recursive stack space
- [To Table Of Content](#table-of-content)

## 3. Count Good numbers
- Link -> https://leetcode.com/problems/count-good-numbers/description/
- Rating -> 2 ⭐
- Difficulty -> **EASY**
### Problem Statement
1. You are given a non-negative integer n
1. We define a good number of length n such that:
    - The digits at even indices (0, 2, 4, …) are even digits → {0, 2, 4, 6, 8} → 5 choices
    - The digits at odd indices (1, 3, 5, …) are prime digits → {2, 3, 5, 7} → 4 choices
1. Return the count of all possible good numbers of length n, modulo 10⁹ + 7.
- [To Table Of Content](#table-of-content)
### Approach
1. calculate 5<sup>[n/2]</sup> * 4<sup>[n/2]</sup>
2. Just look out for the everflow of the limit
3. same in **Iterative** and **Recursive** approach as just an set of calculation
4. Complexicity
    - Time -> O(N)
    - Space -> O(1) -> Iterative, O(N) -> Recursive stack space
- [To Table Of Content](#table-of-content)

## 4. Sort a stack using recursion
- Link -> https://www.geeksforgeeks.org/problems/sort-a-stack/1
- Rating -> 3⭐
- Difficulty -> **MEDIUM**
### Problem Statement
1. Sort the stack in ascending order
1. smallest element at the bottom and largest at the top
### Iterative Approach
1. Pop elements one by one from the original stack.
2. While the top of tempStack is greater than current element, move elements back to the original stack.
3. Push the current element into the tempStack.
4. Finally, copy back all elements from tempStack to st.
5. Complexicity
    - Time -> O(n<sup>2</sup>)
    - Space -> O(n) -> extra stack space
### Recursive Approach
1. Call the same function until the last element, before each call store the **st.top()**
2. After raching top pass the stored top and stack to helper function
3. Helper function will put the passed element at bottom while also comparing the top element before adding
4. return the from recursive call same process repets until it comes down to the first call
5. Complexicity
    - Time -> O(n<sup>2</sup>)
    - Space -> O(n) -> recursive stack space
- [To Table Of Content](#table-of-content)

## 5. 