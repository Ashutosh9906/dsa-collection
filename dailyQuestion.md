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
- 
## **Leetcode 955** [Delete Columns to Make Sorted II]
- **Date** -> 21/12/2025
- **Link** -> https://leetcode.com/problems/delete-columns-to-make-sorted-ii/description/
- **Rating** -> 3⭐
- **Difficulty** -> MEDIUM
