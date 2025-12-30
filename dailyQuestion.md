# Daily Question Of Leetcode

## Table Of Content
- [Daily Question Of Leetcode](#daily-question-of-leetcode)
  - [Table Of Content](#table-of-content)
  - [**Leetcode 3433** \[ Count Mentions Per User \]](#leetcode-3433--count-mentions-per-user-)
    - [Approach](#approach)
  - [**Leetcode 3606** \[ Coupon Code Validator \]](#leetcode-3606--coupon-code-validator-)
    - [Approach](#approach-1)
  - [**Leetcode 2147** \[ Number of Ways to Divide a Long Corridor \]](#leetcode-2147--number-of-ways-to-divide-a-long-corridor-)
    - [Approach](#approach-2)
  - [**Leetcode 2110** \[ Number of Smooth Descent Periods of a Stock \]](#leetcode-2110--number-of-smooth-descent-periods-of-a-stock-)
    - [Approach](#approach-3)
  - [**Leetcode 955** \[Delete Columns to Make Sorted I\]](#leetcode-955-delete-columns-to-make-sorted-i)
  - [**Leetcode 955** \[Delete Columns to Make Sorted II\]](#leetcode-955-delete-columns-to-make-sorted-ii)
  - [**Leetcode 960** \[Delete Columns to Make Sorted III\]](#leetcode-960-delete-columns-to-make-sorted-iii)
  - [**Leetcode 2054** \[Two Best Non-Overlapping Events\]](#leetcode-2054-two-best-non-overlapping-events)
    - [Approach](#approach-4)
  - [**Leetcode 3074** \[Apple Redistribution into Boxes\]](#leetcode-3074-apple-redistribution-into-boxes)
    - [Approach](#approach-5)
  - [**Leetcode 3075** \[Maximize Happiness of Selected Children\]](#leetcode-3075-maximize-happiness-of-selected-children)
    - [Approach](#approach-6)
  - [**Leetcode 2483** \[Minimum Penalty for a Shop\]](#leetcode-2483-minimum-penalty-for-a-shop)
    - [Approach](#approach-7)
  - [**Leetcode 2402** \[Meeting Rooms III\] 1⭐](#leetcode-2402-meeting-rooms-iii-1)
    - [Approach](#approach-8)
  - [**Leetcode 1351** \[Count Negative Numbers in a Sorted Matrix\] 4⭐](#leetcode-1351-count-negative-numbers-in-a-sorted-matrix-4)
    - [Approach](#approach-9)
  - [**Leetcode 756** \[Pyramid Transition Matrix\] 2⭐](#leetcode-756-pyramid-transition-matrix-2)
    - [Approach](#approach-10)
  - [**Leetcode 840** \[Magic Squares In Grid\] 4⭐](#leetcode-840-magic-squares-in-grid-4)
    - [Approach](#approach-11)

## **Leetcode 3433** [ Count Mentions Per User ]
- **Date** -> 12/12/2025
- **Link** -> https://leetcode.com/problems/count-mentions-per-user/description/
- **Rating** -> 2⭐
- **Difficulty** -> Medium
### Approach
1. Declare three vector
   - `online` -> To track the users online currently
   - `mentions` -> TO store each mention of each user
   - `offlineEnd` -> To store the end of the **offline** period of the user
2. Sort the events vector according to `timeStamp` as pos **1** in tuple, If the conflict in the **MESSAGE** and **OFFLINE** occur for same `timeStamp` take **OFFLINE**
3. Seperate each term from the tuple as `type`, `timestamp`, `data`
4. Before entering the **if else** check the `offlinieEnd` if **timestamp** is more than offlineEnd than make the user **online**
5. Perform the task as per mentioned in the `type` using nested **if else** statements
    - `OFFLINE` -> make the **online** at id false and calculate the offlineEnd and store it
    - `MESSAGE` -> 
      - `HERE` -> **+1** for only the users who are online
      - `ALL` -> **+1** for each user rather it be offline
      - `id` -> **+1** only at the mentioned id if online
6. Complexicity ( **n = numberOfUsers, m = events.size(), k = average number of tokens in a "MESSAGE" event** )
   - **Time** -> *O(mlogm)+O(m⋅n)+O(m⋅k⋅n)​*
   - **Space** -> *O(m⋅n⋅k)​*
7. [Table Of Content](#table-of-content)

## **Leetcode 3606** [ Coupon Code Validator ]
- **Date** -> 13/12/2025
- **Link** -> https://leetcode.com/problems/coupon-code-validator/description/
- **Rating** -> 4⭐
- **Difficulty** -> Easy
### Approach
1. Loop the Whole code for number of elements in any one of **properties**
2. Declare seperate variable and store properties `Rcode`, `Rbussiness`, `Ractive`
3. Go through multiple **if else** statement if any of those case fails **continue**
   - `Rcode` -> loop through each char check wether it have any inValid char if any **continue**
   - `Rbussiness` -> If it does not belong to any of provided bussiness **continue**
   - `Ractive`  -> If it is false **continue**
4. If all the above cases pass store the answer
5. Things to taken care of
   - Sort **Rcode** in the result on the basis of there **Rbussiness**
   - `set` can be used but it does not allows **duplicates**, but it **sort** the elements on itself
   - Use alternative `multiset` it allows **duplicates** and also **sort** the elements on it's own
6. Complexicity ( **n: number of elements, l: length of Rcode** )
   - **Time** -> *O(n.L + nlogn)*
   - **Space** -> *O(nlogn)*
7. [Table Of Content](#table-of-content)

## **Leetcode 2147** [ Number of Ways to Divide a Long Corridor ]
- **Date** -> 14/12/2025
- **Link** -> https://leetcode.com/problems/number-of-ways-to-divide-a-long-corridor/description/
- **Rating** -> 3⭐
- **Difficulty** -> HARD
### Approach
1. parse through each char of `corridor`, count the number of **S** if the count is **ODD** return **0**
2. Parse through each char of `corridor` reach until we come across **2 Seats**
3. Count the number plants in between the last **2nd seat** and the first **1st seat**
4. No of ways will be `ways = (ways * (plantCount + 1)) % MOD;` where **MOD = 1e9 + 7**
5. Make the **palntCount = 0** after calclation
6. Complexicity
   - **Time** -> *O(n)*
   - **Space** -> *O(1)*
7. [Table Of Content](#table-of-content)

## **Leetcode 2110** [ Number of Smooth Descent Periods of a Stock ]
- **Date** -> 15/12/2025
- **Link** -> https://leetcode.com/problems/number-of-smooth-descent-periods-of-a-stock/description/
- **Rating** -> 2⭐
- **Difficulty** -> MEDIUM
### Approach
1. Every single day is a valid descent period so we start with `ans = 1` and `len = 1`
1. If today's price one less than yesterdays price increement `len`
3. Else pattern breaks and `len` is reset to **1**
4. At the end of every iteration add the `len` to the `ans`
5. Complexicity
   - Time -> *O(n)*
   - Space -> *O(1)*
6. [Table Of Content](#table-of-content)

## **Leetcode 955** [Delete Columns to Make Sorted I]
- **Date** -> 20/12/2025
- **Link** -> https://leetcode.com/problems/delete-columns-to-make-sorted/description/
- **Rating** -> 4⭐
- **Difficulty** -> Easy
- [Table Of Content](#table-of-content)
 
## **Leetcode 955** [Delete Columns to Make Sorted II]
- **Date** -> 21/12/2025
- **Link** -> https://leetcode.com/problems/delete-columns-to-make-sorted-ii/description/
- **Rating** -> 3⭐
- **Difficulty** -> MEDIUM
- [Table Of Content](#table-of-content)

## **Leetcode 960** [Delete Columns to Make Sorted III]
- **Date** -> 22/12/2025
- **Link** -> https://leetcode.com/problems/delete-columns-to-make-sorted-iii/description/
- **Rating** -> 1⭐
- **Difficulty** -> HARD
![Intution](images/daily22-12-1.png)
![Approach](images/daily22-12-2.png)
- [Table Of Content](#table-of-content)

## **Leetcode 2054** [Two Best Non-Overlapping Events]
- **Date** -> 23/12/2025
- **Link** -> https://leetcode.com/problems/two-best-non-overlapping-events/description/
- **Rating** -> 2⭐
- **Difficulty** -> MEDIUM
### Approach
1. We will sort the jobs by it's starting time 
2. We will start throught each job, with help of binary search we will find the first non-overlappng job
3. We will also generate an maxSuffix array containing the max values upto that location
4. Resulting we can get the max value beyond that job, as the job are sorted all the job after the job we found through BS is valid
5. We will return the max of all the combinations
6. Complexity
   - `Time` -> *O(nlogn)*
   - `Space` -> *O(n)*
7. [Table Of Content](#table-of-content)

## **Leetcode 3074** [Apple Redistribution into Boxes]
- **Date** -> 24/12/2025
- **Link** -> https://leetcode.com/problems/apple-redistribution-into-boxes/description/
- **Rating** -> 4⭐
- **Difficulty** -> EASY
### Approach
1. Count the total numbers of apples to be put into the boxes
2. Sort the `capacity` array, decrease the capacity of each box from the total of apples
3. Maintian the counter how much boxes we use
4. Complexity:
   - `Time` -> *O(n + mlogm)*
   - `Space` -> *O(1)*
5. [Table Of Content](#table-of-content) 

## **Leetcode 3075** [Maximize Happiness of Selected Children]
- **Date** -> 25/12/2025
- **Link** -> https://leetcode.com/problems/maximize-happiness-of-selected-children/description/
- **Rating** -> 4⭐
- **Difficulty** -> MEDIUM
### Approach
1. As we want maximum happiness and answer does not depend on the sewuence we sort the `happiness` vector
2. Inside an for loop we will start from the last element and add it to answer while also counting the number of rounds has been processed
3. Each time we will maintian an counter for nunmber of rounds has been completed and reduce it each time while adding happiness to answer
4. The pos we get the **happiness[i] - rounds** as 0 we will stop ( happiness can't be negative ) return the ans;
5. Complexity:
   - `TIme` -> *O(nlogn)*
   - `Space` -> *O(1)*
6. [Table Of Content](#table-of-content) 

## **Leetcode 2483** [Minimum Penalty for a Shop]
- **Date** -> 26/12/2025
- **Link** -> https://leetcode.com/problems/minimum-penalty-for-a-shop/description/
- **Rating** -> 3⭐
- **Difficulty** -> MEDIUM
### Approach
1. We will calculate the penalty for closing the store at 0
2. We will iterate through a for loop for further closig the store ahead from 0 1 -> n
3. Each time if `'Y'` occurs reduce the panlty or `'N'` increase the penalty
4. At the end of each penalty check for minPenalty and update the answer
5. Complexity:
   - `Time` -> *O(n)*
   - `Space` -> *O(1)*
6. [Table Of Content](#table-of-content) 

## **Leetcode 2402** [Meeting Rooms III] 1⭐
- **Date** -> 27/12/2025
- **Link** -> https://leetcode.com/problems/meeting-rooms-iii/description/
- **Difficulty** -> HARD
### Approach
![intuition and approach](images/daily27-12.png)
1. Complexity:
   - `Time` -> *O(mlogn)*
   - `Space` -> *O(n)*
2. [Table Of Content](#table-of-content) 

## **Leetcode 1351** [Count Negative Numbers in a Sorted Matrix] 4⭐
- **Date** -> 28/12/2025
- **Link** -> https://leetcode.com/problems/count-negative-numbers-in-a-sorted-matrix/description/
- **Difficulty** -> EASY
### Approach
1. Iterate an for loop from 1 -> n (size of 2D array)
2. As the sub arrays are sorted we can use binary search to find the first -ve element and calculate
3. For bit bit optimization if the first element itself is negative no need for binary search direct add the size
4. Manage as pos variable to keep track last negative element and make it 0 at start
5. If the pos is not changed from 0 then there is no negative number in the array add m(size of subArray) - pos to ans
6. Complexity:
   - `Time` -> *O(nlogm)*
   - `Space` -> *O(1)*
7. [Table Of Content](#table-of-content) 

## **Leetcode 756** [Pyramid Transition Matrix] 2⭐
- **Date** -> 29/12/2025
- **Link** -> https://leetcode.com/problems/pyramid-transition-matrix/description/
- **Difficulty** -> MEDIUM
### Approach
1. They have given the base of the pyramid we have to build the remaining above layres with the help of the allowed string
2. We will take the window two char from the base and lookout in allowed matching first two char to the window the 3rd char in the allowed string will be the char that will be placed at the top of those two char 
3. We have to find out whether we can form the pyramid or not using those allowed array and base
4. At first we will make an mp to store the allowed in from of `unordered_map<string, vector<char>> mp`
5. We will alse use an ds to store bad layers that can't be build further to avoid unnecessary recursive call of form `unordered_set<string> bad`
   - On purpose we choose the unordered_set as it have an look up time complexicty of *O(1)*
   - It uses hash table to store the values and prevent duplicates as well
6. We will have an temp string to store the next we will take first two char from base take it's allowed add the the temp and call with pos+1
7. At the point where the **pos == base.length()-1** we check with help of function `solve()` whether it id bad if not call the the backTrack with the temp as base and pos '0' 
8. If the call from the solve to backTrack return false add that srting to bad 
9. Likewise we try each combination of the allowed pyramid and if any point we reach base.length() == 1 return true;
10. Complexity: **(k is small (≤ 26, realistically ≤ 3–5), n ≤ 8)**
       - `Time` -> *O(k<sup>n</sup>)*
       - `Space` -> *O(k<sup>n</sup>)*: bad string if the base itslef fails + *O(n)*: recursive stack space + *O(A)*: storing mp for allowed pyramid
7. [Table Of Content](#table-of-content) 

## **Leetcode 840** [Magic Squares In Grid] 4⭐
- **Date** -> 30/12/2025
- **Link** -> https://leetcode.com/problems/magic-squares-in-grid/description/
- **Difficulty** -> Medium
### Approach
1. we iterate through row from i=0 -> i+2<n and cloumns j=0 -> j+2<m so that we can look out through every possible matrix
2. An important is check is the middle element should 5 (compulsary) else skip the iteration
3. An for for x=i -> i+3 inside it y=j -> j+3 to check all the elements for the matrix are unique and in the range of 0 -> 9
> this innser two for loop of x and y would not be considerd into the time compexity as they are iterating for an constant 9 times we wont add them up, time complexity counts those for loops who changes as per the input not constant for each test case
4. If all the elements are unique and in the valid range we check the combinations 3 row, 3 cloums, 2 diagonals
5. At any moment the combination break on the spot skip the iteration
6. At the end increment the counter for and magix matrix
7. Complexity:
   - `Time` -> *O(n * m)*: outer tow main loops
   - `Space` -> *O(1)*: no extra is used
8. [Table Of Content](#table-of-content) 