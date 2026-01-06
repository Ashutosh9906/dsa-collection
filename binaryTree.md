# Binary Trees

## Table of content
- [Binary Trees](#binary-trees)
  - [Table of content](#table-of-content)
  - [1. Preorder Traversal of Binary Tree `[DFS]` 4⭐](#1-preorder-traversal-of-binary-tree-dfs-4)
    - [Recursive Approach 4⭐](#recursive-approach-4)
    - [Iterative Approach 3⭐](#iterative-approach-3)
  - [2. Inorder Traversal of Binary Tree `[DFS]` 4⭐](#2-inorder-traversal-of-binary-tree-dfs-4)
    - [Recursive Approach 4⭐](#recursive-approach-4-1)
    - [Iterative Approach 3⭐](#iterative-approach-3-1)
  - [3. PostOrder Traversal of Binary Tree `[DFS]` 4⭐](#3-postorder-traversal-of-binary-tree-dfs-4)
    - [Recursive Approach 4⭐](#recursive-approach-4-2)
    - [Iterativ Approach I 3⭐](#iterativ-approach-i-3)
    - [Iterative Approach II 2⭐](#iterative-approach-ii-2)
  - [4. Level order Traversal / Level order traversal in spiral form `[BFS]` 3⭐](#4-level-order-traversal--level-order-traversal-in-spiral-form-bfs-3)
    - [Approach](#approach)

## 1. Preorder Traversal of Binary Tree `[DFS]` 4⭐
- **Link** -> https://leetcode.com/problems/binary-tree-preorder-traversal/description/
- **Difficulty** -> EASY
### Recursive Approach 4⭐
1. We use recursion to iterate through every node of tree and store the answer into an vector
2. If the node is NULL we terminate the recursive call else we store the node->val into tht vector
3. Further we do an recursive call passing node->left ans node->right each time
4. Complexity:
    - `Time`: *O(n)*: total number of nodes to touch each of them
    - `Space`: *O(n)*: recursive stack the depth of the tree at worst case may same as number of nodes
### Iterative Approach 3⭐
1. We use stack for the iterative approach of the preOrder store the node pointer, at first push the root into the stack
2. Iterate through an while loop until the stack is not empty, get the top element from stack pop it form stack, push it's value into the ans vector if present first push the node->right into the stack ans then push the node->left into the stack 
3. Complexity:
    - `Time` -> *O(n)*: to store an pop all the elements from the queue
    - `Space` -> *O(n)*: queue space to store the tree elements
4. [To Table Of Content](#table-of-content)

## 2. Inorder Traversal of Binary Tree `[DFS]` 4⭐
- **Link** -> https://leetcode.com/problems/binary-tree-inorder-traversal/description/
- **Difficulty** -> EASY
### Recursive Approach 4⭐
1. Same as Preorder traversal of binary tree the changee is just the sequence the call are made
2. At first the node is NULL stop the recursive and return
3. Call the left node at the very start, next push the node->val of current call into ans, next call the right node 
4. Complexity:
    - `Time`: *O(n)*: total number of nodes to touch each of them
    - `Space`: *O(n)*: recursive stack the depth of the tree at worst case may same as number of nodes
### Iterative Approach 3⭐
1. We will be using stack for iterative approach to store the node pointer
2. We assign an temp pointer node as root
3. If the node is not null push it into the stack and move the left usinng nod = node->left
4. If the node is null and stack is empty break, else not node = st.top() and also st.pop() push the node->vaal into the ans vector and move to the right using node->right
5. Complexity:
    - `Time` -> *O(n)*: to store an pop all the elements from the queue
    - `Space` -> *O(n)*: queue space to store the tree elements
6. [To Table Of Content](#table-of-content)

## 3. PostOrder Traversal of Binary Tree `[DFS]` 4⭐
- **Link** -> https://leetcode.com/problems/binary-tree-postorder-traversal/description/
- **Difficulty** -> EASY
### Recursive Approach 4⭐
1. Same as above two questions just change the sequence like call node->left, next call node->right, next push node->val into answer
2. Complexity:
    - `Time`: *O(n)*: total number of nodes to touch each of them
    - `Space`: *O(n)*: recursive stack the depth of the tree at worst case may same as number of nodes
### Iterativ Approach I 3⭐
1. We use two stack to store the the node pointer of the node, at the very beggining we push the root into st1 and iterate through st1 until it is empty
2. Inside the loop if present we push the node->right and node->left to the st1 for further computaion in the order left then right
3. At the end of iteration push the node into the st2 that will be sequence of the answer
4. After completion of the while loop push the st.top()->val into the ans vector which will be the required answer
5. Complexity:
    - `Time`: *O(n)*: total number of nodes to touch each of them
    - `Space`: *O(2n)*: recursive stack the depth of the tree at worst case may same as number of nodes
### Iterative Approach II 2⭐
1. We use one stack comparitive to above approach, initalize curr pointer with root->left and push root into the stack
2. If the current is not NULL directly push it into the stack
3. Else take an temp pointer haing st.top()->right, if temp is NULL then store temp and st.top() add temp->val to ans and iterate through through an while loop until it meats conditon temp == st.top()->right and store it's value in ans
4. If the temp is not null means tree ans node to the right assign curr the temp
5. Complexity:
    - `Time` -> *O(2n)*: one of external loop and n for push and pop operation into the stack
    - `Space` -> *O(n)*: exteranl stack space
6. [To Table Of Content](#table-of-content)
  
## 4. Level order Traversal / Level order traversal in spiral form `[BFS]` 3⭐
- **Link** -> https://leetcode.com/problems/binary-tree-level-order-traversal/description/
- **Difficulty** -> EASY
### Approach
1. We store the ans level wise we use queue data structure which will store the pointer of the node and to store ans vector<vector<int>> ans
2. At the very start before starting the iteration we push the root into the queue, we iterate through an while loop until queue in empty
3. At we declare vector level to store temp level wise answer, we iterate an new loop inside from o -> q.size() to compute each child of the root
4. For every root node if there exist an left and right which are not null we push them into the queue and push the node->val into the level DS
5. As at first only one node root is present the innser for loop will execute once it check any node on left and right (assum it has 2 and 3) and push them into the queue pop the root from the queue push the val into the level after temination of the for loop push the level into the ans now queue is not empty it has two element now 2 wii act as root once and 3 as root once 
6. Complexity:
    - `Time` -> *O(n)*: to store an pop all the elements from the queue
    - `Space` -> *O(n)*: queue space to store the tree elements
7. [To Table Of Content](#table-of-content)

