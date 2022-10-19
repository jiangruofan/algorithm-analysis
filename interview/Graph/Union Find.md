[Google Onsite](https://leetcode.com/discuss/interview-question/2117543/Google-Onsite)

Problem Statement -  
Given a matrix of size n*m, where each position is representing a city.  
Initially all city are represented by zero. ( means they are not traversible ).  
On each day one city will randomly become traversible. ( matrix[i][j] = 1 )

Write an algorithm that can detect when there is a path from any city of first column to any city of last column.

并查集+设置两个虚拟节点 力扣1970

------

[Special Paths | Google OA | July 2022 | Graph](https://leetcode.com/discuss/interview-question/2260088/Special-Paths-or-Google-OA-or-July-2022-or-Graph)

You are given the following:

1.  A tree with N nodes
2.  An array A denoting the value of each node

A path is called special path if the following conditions are satisfied:

1.  All nodes in the path are traversed exactly once.
2.  The value of starting and terminating node in the path is same and startnode != terminating node
3.  The values of any node in the path are not greater than the value of starting node.

Task:  
Count the no. of special paths in the tree. (Two paths are different if they contain at least one different node.)

Example:  
N = 5  
edges = [(1,2), (1,3), (3,4), (3,5)]  
A = [2,3,1,2,3]
![image](https://assets.leetcode.com/users/images/63a29f35-a46e-4b9d-9e0e-30c1a0e4e900_1657392040.8452625.png)
Output:  
2

Explanation:  
path 1: 1(2)->3(1)->4(2)  
path 2: 2(3)->1(2)->3(1)->5(3)

Constraints  
1<= T <= 10  
2 <= N <= 10^5  
1<=Ai <= 10^9

并查集 并且并查集的祖先节点为val最大的节点 还要维护并查集最大元素的个数 

---------------------

[Google Onsite Question](https://leetcode.com/discuss/interview-question/1124989/Google-Onsite-Question)

I had a google virtual onsite round for their lateral hiring. The question I was giving was:  
Let us say that there is a home and a saloon that you want to visit. You have a routes built in across. You need to check that if there is a route that exists that lets you visit the saloon.  
For example: Here you have H which denotes your home and R is your route and S is your saloon.  
H R R .  
R . R .  
. . R .  
. . S .  
I applied DFS and was able to solve this question.

Now there was a follow up to this question: Let us consider that at first there was no route between both of them. And slowly a route starts developing. How will you be able to check that out?  

For example:  
First:  
H . . .  
. . . .  
. . S.

Second:  
H . . .  
. R . .  
. . S .

Third:  
H . . R  
. R . .  
. . S .

Fourth:  
H . . R  
R R . .  
. . S .  
and so on.

类似题目:  [305. Number of Islands II](https://leetcode.cn/problems/number-of-islands-ii/)

--------------

[Google Internship Test question.](https://leetcode.com/discuss/interview-question/848057/Google-Internship-Test-question.)

原题: #### [1697. Checking Existence of Edge Length Limited Paths](https://leetcode.cn/problems/checking-existence-of-edge-length-limited-paths/)

----------------

[GOOGLE OA 2021 SWE](https://leetcode.com/discuss/interview-question/805419/GOOGLE-OA-2021-SWE)

https://leetcode.com/discuss/interview-question/806191/Google-New-Grad-2021-or-OA

![image](https://assets.leetcode.com/users/images/d9244002-32da-4d2a-834a-e400a9b46bd2_1598123408.941765.png)
把所有能互换的看成一个连通分量 然后看这个连通分量有多少个元素符合条件 不符合条件的就是汉名距离

-----------

[Google phone round](https://leetcode.com/discuss/interview-question/392924/Google-phone-round)

There are n post offices in a row, You are given the distance of each post office from your home. A post office can send a post to another post office if the distance between the two places is less than or equal to x. You are given q queries. Each query contain indices of two post offices. You have to find whether the post offices can deliver post to each other or not. You may use any number of post offices between two post offices if they satisfy the distance criteria  
Expected time complexity= O(n+q)

可以不使用并查集

----------------------

[Meta question](https://leetcode.com/discuss/interview-question/2628139/Meta-question)

Does anyone know how we can solve this problem with python? Thanks  
You are given a directed acyclic graph as a list of pairs, where the first element is a source node and the second element the destination node. Write a function that takes two nodes and returns whether they have a common ancestor or not.

Example 1:  
Input: ([[A, B], [A, C], [A, D], [B, G], [E, F]] ; B; G)  
Output: True

Example 2:  
Input: ([[A, B], [A, C], [A, D], [B, G], [E, F]] ; B; F)  
Output: False

--------

[Microsoft | 2022 Aug OA | Codility Challenge 3](https://leetcode.com/discuss/interview-question/2450732/Microsoft-or-2022-Aug-OA-or-Codility-Challenge-3)

![image](https://assets.leetcode.com/users/images/c1bda41e-8fea-4ba2-aa2e-997c5ad9abb1_1660940007.4492052.jpeg)
![image](https://assets.leetcode.com/users/images/73762e85-6586-47c8-a3bb-5afb9370035f_1660940005.4988134.jpeg)

----------

[JP Morgan SDE OA](https://leetcode.com/discuss/interview-question/2680865/JP-Morgan-SDE-OA)

There are  `N cities and M roads`, and the cities are connected to other cities by those roads, Terrorists have planted bombs in every city. Each bomb will explode one after other(First bomb in City 1 then city 2 and so on)  
Each explosion will destroy  `the city and the roads which are connected to it`.  
For each explosion, you need to  `return the number of connected components of cities`.

Input format->  
N M  
A1 B1  
A2 B2....

Constraints->  
1<=N<=2 * 1e5  
0<=M<=min(2 * 1e5,N*(N-1)/2))

时空倒流

------

[TikTOk OA](https://leetcode.com/discuss/interview-question/2719860/TikTOk-OA)

![image](https://assets.leetcode.com/users/images/3b1b84b9-e4c4-47cd-bfb2-96b6300e308b_1666131522.6656868.jpeg)

------
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTQ0MjI1NDc2NSw2ODM3Nzk0MzksLTczOT
c0MTc0NF19
-->