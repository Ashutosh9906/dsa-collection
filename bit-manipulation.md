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
  - [4. Power Set](#4-power-set)
    - [Approach](#approach-3)
  - [5. Find xor of numbers from L to R](#5-find-xor-of-numbers-from-l-to-r)
    - [Approach](#approach-4)
  - [6. Find the two numbers appearing odd number of times](#6-find-the-two-numbers-appearing-odd-number-of-times)
    - [Approach](#approach-5)

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

## 4. Power Set
- **Link** -> https://leetcode.com/problems/subsets/description/
- **Rating** -> 3⭐
- **Medium** -> MEDIUM
### Approach
1. As we know number of sub sets will be **2<sup>n</sup>** including the empty subset
2. We can use the bits of each number to decide wether to take the number or not
3. like 1 -> 001, 2 -> 010, 5 -> 101, 7 -> 111, 0 -> 000 we can use all those combination to form subArray
4. We would take the elements who have set bit, to find out which bit is set we can use `AND` operator and `LEFT SHIFT`
6. i & (1<<j) this will give us whether the bit is set or not if yes then we would take the num at pos **'j'**
7. Complexity:
  - `Time` -> *O(2<sup>n</sup> * n)*
  - `Space` -> *O(2<sup>n</sup> * n)* -> nearly ( close )
8. [To Table Of Content](#table-of-content)

## 5. Find xor of numbers from L to R
- **Link** -> https://www.geeksforgeeks.org/problems/find-xor-of-numbers-from-l-to-r/1
- **Rating** -> 3⭐
- **Medium** -> MEDIUM
### Approach
1. Try to do some observation in `XOR` till n
![observation](images/bit-manupulation-5.png)
2. As we can i forms an pattern for each number using those we can derive some conditions
3. For questions like from left to right we can use the above results
4. ex. 4 -> 8 we can do like xor(xor(1 -> 3) xor(1 -> 8)) -> (1^2^3) ^ (1^2^3^4^5^6^7^8)
5. If we observed carefuly xor of same is number is 0 so the above will result in 4^5^6^7^8
6. Complexity:
  - `Time` -> *O(1)*
  - `Space` -> *O(1)*
7. [To Table Of Content](#table-of-content)

## 6. Find the two numbers appearing odd number of times
- **Link** -> https://www.geeksforgeeks.org/problems/two-numbers-with-odd-occurrences5846/1
- **Rating** -> 3⭐
- **Medium** -> MEDIUM
### Approach
1. As we have done in single odd appearing number we will do `XOR` for all the elements
2. The main concern is how to seperate the numbers after the XOR of all the elements
3. XOR gives us the bit set where both the number differ 1010 ^ 1000 -> 0010 
4. We should find the right most set bit using setNum = (num & num-1) ^ num this will give us the right most set bit
5. We will create two buckets numbers haveing the bit set as **setNum** and another without
6. In each bucket we will get both the numbers seperated and if we perform the individual `XOR` we will get the number itself
7. **IMP** -> it the XOR of all elements comes out to be -2<sup>31</sup> doing something like -2<sup>31</sup> - 1 will overflow it so while storing the XOR of all the elements use `Long Long`
8. Complexity: 
  - `Time` -> *O(2N)*
  - `Space` -> *O(1)*
9. [To Table Of Content](#table-of-content)
