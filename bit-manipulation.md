# Bit - Manipulation

## Table of content
- [Bit - Manipulation](#bit---manipulation)
  - [Table of content](#table-of-content)
  - [1. Divide two integers without using multiplication, division and mod operator](#1-divide-two-integers-without-using-multiplication-division-and-mod-operator)
    - [Approach](#approach)
  - [2. Count number of bits to be flipped to convert A to B](#2-count-number-of-bits-to-be-flipped-to-convert-a-to-b)
    - [Approach](#approach-1)
  - [3. Find the number that appears odd number of times](#3-find-the-number-that-appears-odd-number-of-times)
    - [Approach](#approach-2)

## 1. Divide two integers without using multiplication, division and mod operator
- **Link** -> https://leetcode.com/problems/divide-two-integers/submissions/1861400382/
- **Rating** -> 3⭐
- **Medium** -> MEDIUM
### Approach
1. we could just add up the **divisor** at many times until it reaches close to **dividend**  
2. By some reverse Engineering we colud do like divisor * 2<sup>0</sup>, divisor * 2<sup>1</sup>, divisor * 2<sup>2</sup>, divisor * 2<sup>3</sup> until it gets close to the dividend
3. We could reduce the numbers of additions like **n** times to some **log n**
2. Each time we will reduce the **divisor * 2<sup>count</sup>** from the dividend and count by simply adding 2<sup>count</sup>
3. Complexity:
    - `Time` -> *O(log<sub>2</sub>n)<sup>2</sup>*
    - `Space` -> *O(1)*
4. [To Table Of Content](#table-of-content)

## 2. Count number of bits to be flipped to convert A to B
- **Link** -> https://leetcode.com/problems/minimum-bit-flips-to-convert-number/submissions/1861474115/
- **Rating** -> 4⭐
- **Medium** -> EASY
### Approach
1. `FIRST APPROACH`: We can use **AND** operator AND with start and goal if it doesn't match increement the counter
2. Complexity:
    - `Time` -> *O(31)*
    - `Space` -> *O(1)*
3. `SECOND APPROACH`: we can use **XOR** like **start ^ goal** the number it will give we just have to count the number of set bits
4. We can also do like insted of counting the number of set bit just do the procedure to convert the number to binary and count the number of set bits
5. Complexity:
    - `Time` -> *O(logn)*
    - `Space` -> *O(1)* 
6. [To Table Of Content](#table-of-content)

## 3. Find the number that appears odd number of times
- **Link** -> https://leetcode.com/problems/single-number/description/
- **Rating** -> 3⭐
- **Medium** -> EASY
### Approach
1. As we know `1 ^ 1` results to **0**
2. So we can use the same concept we will xor all the numbers in the array, the number appeared once will only remail in the end
3. Complexity:
    - `Time` -> *O(n)*
    - `Space` -> *O(1)* 
4. [To Table Of Content](#table-of-content)