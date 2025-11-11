# RECURSION 

## Table Of Content

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