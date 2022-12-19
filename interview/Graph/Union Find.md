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

[Microsoft | OA | April 2022 | Missing connections in binary tree](https://leetcode.com/discuss/interview-question/1939372/Microsoft-or-OA-or-April-2022-or-Missing-connections-in-binary-tree)

You are given a binary tree with distinct positive integer values. You can transform this binary tree to a graph by adding connections between any two nodes if they are not already connected. 2 nodes are connected if either of them is a child of the other node.

Your goal is to identify and enumerate the minimum number of connections that need to be drawn between the nodes of this tree so that the resulting graph fully contains the min-heap that can be formed using the value of the nodes.

Write a method that will take as input an array defining the tree. The root of the tree will be at index 0, the left and the right child of the element at the index i will be 2i+1 and 2i+2 respectively. A value of -1 indicates NULL. If an index has no defined left and right child, assume NULL.

The method will enumerate the connections as described above and identify the unique values that the connections must be set up for. For each of the connections, there will be 2 values denoting the ends of the connection to be built – add all of these values into an integer array sorted by the smallest value of the connection and then by larger value.

![image](https://assets.leetcode.com/users/images/018ee358-3983-4c38-a70c-c20740ec6b1a_1649763993.8070078.png)
![image](https://assets.leetcode.com/users/images/303df29f-b7e4-442d-b78c-19ce7483dffa_1649764018.3191926.png)

------

[Door Dash OA question](https://leetcode.com/discuss/interview-question/2773298/Door-Dash-OA-question)

![image](https://assets.leetcode.com/users/images/7b320571-b932-4f75-827c-9a49f0d5b45d_1667469116.9504898.png)
![image](https://assets.leetcode.com/users/images/c02d6795-ce48-4838-9d19-e59a9b7ea574_1667469116.7061868.png)

------

[Faltiron Health | Technical Interview | Currency Conversion](https://leetcode.com/discuss/interview-question/2794278/Faltiron-Health-or-Technical-Interview-or-Currency-Conversion)

I was asked the currency conversion problem for a Software Engineer role...

You are given a list of rates between two currencies, and a query, the query is two currencies and you are supposed to find/drive the rate between these two currencies.

Below is my code, the interviewer stated that I don't need to come up with an executable code, but I did, and the interview was very positive and got very good feedback while on the interview. Somehow got rejected afterwards, as they messed up my interview with someone else's, and I got feedback telling me that I wasn't able to build a data structure, which is very different from what happened! I literally built the graph in two minutes. After several back and fourth emails, I got nowhere with them and they weren't able to remember what happened in my interview and I lost interest...

```
rates = [("USD", "CAD", 1.3), ("USD", "GBP", 0.71), ("USD", "JPY", 109), ("GBP", "JPY", 155)]
query =  ["USD", "JPY"]

```

带权重的并查集

-----

[Media.net | Virtual Onsite](https://leetcode.com/discuss/interview-question/1336628/Media.net-or-Virtual-Onsite)

Given an array of size n+1 such that arr[i] = i.  
Given Q queries (Q<n) with condition:

1.  Given i : Update arr[i]=0
2.  Given (L, R) : Return max element in range (L,R)

Follow up: Consider the case where n is very large

答案: 
I think the interviewer meant that Q is much smaller than N, in which case this problem can be solved with O(logQ) (or even faster!) time complexity.  
The idea is to use DSU and initialize it normally (par[i] = i). Now, if we delete a note 'x', then we just join it to 'x-1'. Now it is easy to see that for a query (L,R), the answer will be the parent of 'R'. If this parent comes out to be less than L, then we can simple return 0 (because all numbers between L,R are set to 0).  
To improve Query time, we can use path compression in DSU.

---

[Media.net | Phone | India](https://leetcode.com/discuss/interview-question/703363/Media.net-or-Phone-or-India)

Role: Senior Software Engineer  
Location:- India

Phone Screen: 45Mins to 1 hr

Question 1:  
[https://leetcode.com/problems/non-negative-integers-without-consecutive-ones/](https://leetcode.com/problems/non-negative-integers-without-consecutive-ones/)

Question 2:

Given two arrays:  
Array-1 = [13, 11, 12, 22, 12, 17]  
Array-2 = [3, 0, 4]  
[36, 29, 23]  
Each index in Array-2 will divide the array into two segemts(considering the main array as one one segment) , you have to return the max of sum of each segment

Example:  
index 0 of array-2 will divide the array into [[ 13,11,12 ], [12,17]] at 3rd index ->  
sum of segement-1 => 36  
sum of segment-2 => 29  
max sum => max(36, 29) = 36

index 1 will divide the array into [[11,12 ], [12,17]] ->  
sum of segement => 23  
sum of segment-2 => 29  
max sum => max(23, 29) = 29

index 1 will divide the array into [[11,12 ], [17]] ->  
sum of segement => 23  
sum of segment-2 => 17  
max sum => max(23, 17) = 23

_I could not solve the 2nd question; it felt like I need a competitive programming spirit to solve this one._

时空倒流+并查集 并且用一个heap维护最大值

----

[Ticktok Telephonic Round](https://leetcode.com/discuss/interview-question/2840632/Ticktok-Telephonic-Round)

Given a Map<String, List[String]> where key is the distinct Videos say Video1, Video2 ... and value will be the list of tags associated with that video, like Action, Car, Gun..

We need to return a list of Videos where two videos can have any number of common tags. Note: It is not necessary that all the tags must be present for all videos. Below is an example to illustrate it better.

```
Input: 
<Video1 -> [Tag1]
Video2 -> [Tag2]
Video3 -> [Tag1, Tag2]
Video4 -> [Tag4]
Video5 -> [Tag4, Tag5]>

Output: [[Video1, Video2, Video3], [Video4, Video5]]

Explanation: As Video1 and Video3 have a coomon tag (Tag1) we'll combine them together and Video2 and Video3 have another tag (Tag2) as common, we'll combine all three videos as one list. Similar with Video4 and Video5.
```

----

[RedHat OA](https://leetcode.com/discuss/interview-question/2832770/RedHat-OA)

https://leetcode.com/discuss/interview-question/2844072/Find-The-STRING-Problem-(Hard).-I-am-not-getting-it

Q1) [https://leetcode.com/problems/count-vowels-permutation/](https://leetcode.com/problems/count-vowels-permutation/)

![image](https://assets.leetcode.com/users/images/d5672712-e282-4887-a971-41418184cb46_1668935500.978573.jpeg)
![image](https://assets.leetcode.com/users/images/778d2cca-1480-49cb-aad3-5d817494ca71_1668935501.2389295.jpeg)
![image](https://assets.leetcode.com/users/images/f3309733-5972-4bc8-a051-ed7f880025c4_1668935501.2661815.jpeg)

并查集+z array

----

[DE Shaw off campus OA for 2023 batch](https://leetcode.com/discuss/interview-question/2924772/DE-Shaw-off-campus-OA-for-2023-batch)

![image](https://assets.leetcode.com/users/images/1b1f9a4d-dea1-460c-8a86-fb79822a8114_1671354443.5641224.jpeg)
![image](https://assets.leetcode.com/users/images/173c7b71-bbec-4190-9e28-4de9d8ea16d0_1671354459.135055.jpeg)
![image](https://assets.leetcode.com/users/images/17bfe4b4-db0e-418d-9d18-c614aee3907f_1671354470.4818919.jpeg)
![image](https://assets.leetcode.com/users/images/4e923eb6-25dc-4392-ab2c-23343327f9b9_1671354485.7323103.jpeg)
![image](https://assets.leetcode.com/users/images/404e54d4-fd08-404d-ac5c-2a060e84f2d8_1671354515.8854613.jpeg)
![image](https://assets.leetcode.com/users/images/db65ec65-103f-47ec-a34a-03b0373469f6_1671354528.2080586.jpeg)
![image](https://assets.leetcode.com/users/images/d1f0c736-8228-4f30-9141-965a11d23689_1671354540.0082858.jpeg)

首先所有的disconnected nodes自己所在的集合先把边加满 然后根据贪心思想 所有的不存在disconnected nodes的集合肯定都是连接在节点数最多的一个disconnected nodes集合上

--









<!--stackedit_data:
eyJoaXN0b3J5IjpbNTQxODE3NDExLC0xNDcyMDIxODY3LC0xOD
c2MjU4NjUxLC02ODIwNDY3OTAsLTEyODE1Mzc0OCwtMTQ4ODkx
MDcwNCwtNDQyMjU0NzY1LDY4Mzc3OTQzOSwtNzM5NzQxNzQ0XX
0=
-->