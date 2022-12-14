[Google OA](https://leetcode.com/discuss/interview-question/1440227/Google-OA)

Given an array of numbers A and two integers S and D, you can perform three operations

1.  x + A[i]
2.  x - A[i]
3.  x xor A[i] (bitwise xor)  
    Each of these operations cost one move. Task is to find the minimum number of moves in which S can be changed to D or return -1 otherwise.

**Sample TC:**  
A = [6, 2, 7, 7]  
S = 10  
D = 21

**Output:**  3

**Explaination:**  
10 + A[3] = 17  
17 + A[1] = 19  
19 + A[1] = 21

I was not able to come up with anything as I think it clearly is a Math problem.

**EDIT**  
**Constraints:**  
x lies in [0, 100000]  
1 <= A.size() <= 1000  
-10^9 <= A[i] <= 10^9

--------------

[Google On site](https://leetcode.com/discuss/interview-question/1290963/Google-On-site)

You're given a 2 grid array of subway stops.  
Each subway stop has a value that represents the current number of people waiting there  
Given 2 stops, return a stop with more people waiting that could've lead to both stops.  
The path to both stops must only contain other stops with a number of people less or equal to the current stop

If there are multiple valid stops, return the nearest stop.  
If there's no valid stop, return null.

Example Input:

Stop 1 has 5 people waiting at (2, 3)  
Stop 2 has 5 people waiting at (2, 1)

[5, 9, 7, 6]  
[7, 8, 1, 5]  
[6, 5, 2, 5]  
[9, 3, 3, 2]

Example Output: Stop with 9 people waiting at (0, 1)

Path for stop 1: 9 -> 7 -> 6 -> 5 -> 5  
Path for stop 2: 9 -> 8 -> 5

这题和苏伊士那道小红书的题目一样
只需要从两个点开始bfs 然后记录最短路径长度即可

------------

[AMAZON OA 2023 || REACH THE END IN TIME](https://leetcode.com/discuss/interview-question/2615840/AMAZON-OA-2023-oror-REACH-THE-END-IN-TIME)

![image](https://assets.leetcode.com/users/images/e29d552f-e962-4dab-9803-a8d949fcef53_1663978476.81918.png)
![image](https://assets.leetcode.com/users/images/97846768-3ed8-4648-8861-fd0c403b9b91_1663978486.6703243.png)
![image](https://assets.leetcode.com/users/images/de100ec8-2276-483b-84bc-e846f095cfbb_1663978496.047809.png)
![image](https://assets.leetcode.com/users/images/639bf83f-c3bc-4fff-a4b8-f35c2db31f0e_1663978503.540362.png)

-----------

[Codility Graph Hard Question OA](https://leetcode.com/discuss/interview-question/2694254/Codility-Graph-Hard-Question-OA)

https://leetcode.com/discuss/interview-question/1816811/Microsoft-OA-or-Graph-Question

This was the 2nd Question in coditlty Test.  
Can anyone provide the best Algo for this Problem.  
I was able to slove this problem using Bfs but my code is given TLE, Because I was caluclating path from every Hospital and taking the min from them.  
N, H Value Range from 1 to 100000
![image](https://assets.leetcode.com/users/images/3efc9a44-0b91-48c1-9f16-c8f06ff99dd7_1665574332.802469.png)

从有救护车的城市开始bfs 注意bfs最后结果需要减1

-----

[epiFi / Fi Online Assessment Questions [SDE II] - HackerRank](https://leetcode.com/discuss/interview-question/2945953/epiFi-Fi-Online-Assessment-Questions-SDE-II-HackerRank)

![image](https://assets.leetcode.com/users/images/913d906d-0896-4517-bc83-41bc4ed8292f_1671889695.283183.png)

和上题一样

-----

[Google | Onsite | SDE | Maze question | L4](https://leetcode.com/discuss/interview-question/2711886/Google-or-Onsite-or-SDE-or-Maze-question-or-L4)

I was asked the following maze traversal question and I was not able to solve a specific test case.

Question is to find the shortest distance between a Source and Destination node when there is an alarm node. During traversal when you step on this alarm node, the destination node gets locked. This means even if you enter the destination node you are not done yet. You will have to now traverse to a Switch node and then after visiting this Switch Node you can unlock the destination node and then now you can traverse to the destination node.

```
Given: Source Node (Src) , Destination Node (D), Alarm Node (A), Switch Node (Sw). 
To Find: Shortest distance between Source and Destination Node. If you step on an Alarm node, your destination gets locked. You need to visit a Switch Node to unlock your destination Node.

```

I just used a simple BFS with a varying destination node ( First the destination would be D, during traversal if I visited an alarm node, then the new destination node would be Sw and then once I visit the Sw node, the new destination would be D and then continue to traverse the graph)

I couldn't pass a test case where D got locked due to visiting an Alarm node and then the nodes from D to Sw were all visited and I couldn't go back to D.

Please let me know what would be the best solution for this question.

PS:  
Rejected due to the reason of "Efficacy", trying to learn from mistakes and hopefully can perform better next year.

答案: bfs即可 

-----

[Hard OA question](https://leetcode.com/discuss/interview-question/2740665/Hard-OA-question)

![image](https://assets.leetcode.com/users/images/b7c9aa97-c073-4c73-8767-e81e057f97e9_1666668488.8197927.png)

------

[Microsoft | SDE2 | OA | Jan 2022](https://leetcode.com/discuss/interview-question/1734444/Microsoft-or-SDE2-or-OA-or-Jan-2022)

Given a string S consisting of N lowercase alphabets, the task is to find the length of the smallest unique substring in S.

Input: S = “abaaba”  
Output: 2  
Explanation:  
The smallest unique substring in the string S, whose occurrence is exactly 1 is “aa” . Length of this substring is 2.  
Therefore, print 2.

Input: S = “zyzyzyz”  
Output: 5

先找出最小的字母 然后对所有最小字母的index进行bfs 直到某一层的最小字母的index个数为1 需要借助dic来进行操作 只有26个字母

----

[Doordash phone screen](https://leetcode.com/discuss/interview-question/2768603/Doordash-phone-screen)

// # A DashMart is a warehouse run by DoorDash that houses items found in convenience stores, grocery stores, and restaurants. We have a city with open roads, blocked-off roads, and DashMarts.  
// # City planners want you to identify how far a location is from its closest DashMart.  
// # You can only travel over open roads (up, down, left, right).  
// # Locations are given in [row, col] format.  
// # [  
// # # 0 1 2 3 4 5 6 7 8  
// # ['X', ' ', ' ', 'D', '1 ', '1 ', 'X', ' ', 'X'], # 0  
// # ['X', ' ', 'X', 'X', ' ', '1 ', ' 1', ' ', 'X'], # 1  
// # [' ', ' ', ' ', 'D', 'X', 'X', ' 1', 'X', ' '], # 2  
// # [' ', ' ', ' ', 'D', ' ', 'X', '1', ' ', ' '], # 3  
// # [' ', ' ', ' ', ' ', ' ', 'X', 'O', ' ', 'X'], # 4  
// # [' ', ' ', ' ', ' ', 'X', ' ', ' ', 'X', 'X'] # 5  
// # ]

// # ' ' represents an open road that you can travel over in any direction (up, down, left, or right).  
// # 'X' represents an blocked road that you cannot travel through.  
// # 'D' represents a DashMart.

// # # list of pairs [row, col]  
// # locations = [  
// # [200, 200],  
// # [1, 4],  
// # [0, 3],  
// # [5, 8],  
// # [1, 8],  
// # [5, 5]  
// # ]

// # answer = [-1, 2, 0, -1, 6, 9]

// # Provided:  
// # - city: char[][]  
// # - locations: int[][2]

// # Return:  
// # - answer: int[]

----

[OA 2022 | Pythagorean Triplets](https://leetcode.com/discuss/interview-question/2788156/OA-2022-or-Pythagorean-Triplets)

![image](https://assets.leetcode.com/users/images/71e73a9a-40fc-4771-9a5c-b43962d77f3c_1667810418.8833017.png)
![image](https://assets.leetcode.com/users/images/6da14756-6bfb-466e-b207-6fbcce8431a5_1667810425.0042746.png)
![image](https://assets.leetcode.com/users/images/6a6d085f-a7c7-4ef8-8a72-4a9d3a36e0ed_1667810430.303579.png)

三次bfs 然后遍历每个点进行判断即可

----

[interesting directed acyclic graph problem](https://leetcode.com/discuss/interview-question/2800205/interesting-directed-acyclic-graph-problem)

![image](https://assets.leetcode.com/users/images/cb323cfa-b088-4afe-8fee-ebe5edf97e44_1668089207.1800365.png)
和上题一样

---

[Google vo problem](https://leetcode.com/discuss/interview-question/2794952/Google-vo-problem)

My friend got this problem on Google vo. Does anyone have a clue how to solve it?  
Given a grid, two cars a, b, and two locations A, B on the graph, is it possible to park a to A and park b to B?  
There are some obstacles on the grid as well.

----

[Google | Phone Screen](https://leetcode.com/discuss/interview-question/2795760/Google-or-Phone-Screen)

Given an n*(n-1) matrix with 0 or 1 in cells. Starting from top-left, you need to reach bottom right making sure you visit equal number of dark(0) and light(1) cells.

0表示1 1表示-1 要求加起来为0
这里的visited需要记录三个属性 x和y表示位置 还有一个表示sum

---

[Block | connect four modified](https://leetcode.com/discuss/interview-question/2798371/Block-or-connect-four-modified)

I got somewhat medium but bit harder to come up solutions for my telephone round for square.

There were three parts

1.  Create 2 d array of the connect four grid. Example 3x6 grid.

```
- - - - - - 
- - - - - - 
- - - - - - 

```

2.  Display the grid after playing . play(column, color). Always start placing the color at the bottom row up

After play(0,'R'), looks like below

```
- - - - - - 
- - - - - - 
R - - - - - 

```

3.  Additional parameter given called toWin: which is the number of consecutive same color in east, west, north, south direction, not diagonal. Basically, find path from a certain location in grid using left,right, up & down movement of same color. This is where I got stuck. Although i was given hint of BFS, i could not complete and result was rejected.  
    Example winner after play(2,'R') and toWin=5 as total Rs is 6 from position (0,2)

```

Y R R - - - 
Y Y R - - - 
R R R - - - 
```

简单bfs

---

[TikTok | On-Site Round 1](https://leetcode.com/discuss/interview-question/2804546/TikTok-or-On-Site-Round-1)

Q. Given a Binary Tree print the sum of egdes formed by the triangle.

Example : Output : 1+2+3+4+7+8..+13 = 80. Tried solving using Level order traversal but got rejected.

```
          1
		  /\
		 2  3
		/\  /\
	   4  5 6 7
	  /\ /\ /\ /\
	 8 9 10 11 12 13 
```

---

[Google | Cloud Engineer | L4 | Pune | Round 1 | Router Question](https://leetcode.com/discuss/interview-question/2914144/Google-or-Cloud-Engineer-or-L4-or-Pune-or-Round-1-or-Router-Question)

Given a set of N routers in 2-D coordinate, a source router, a destination router. The problem is to find if it is possible to transmit a signal from source to destination.

[(0,0),(0,8),(11,0),(20,30)]

Range = 10

so if we start from (0,0) we can reach to (0,8) and range is less than 10  
similarly, from (0,8) - (11,0) but then from (11,0) - (20,30) we couldn't reach as from 0 to 30 we can not travel in range 10

I reached to solution by DFS in half an hour and then interviewer asked me to code it and then came with followed up question I was able to code that as well.

bfs即可

----

[Amazon | VO | Treasure hunt new version](https://leetcode.com/discuss/interview-question/2930385/Amazon-or-VO-or-Treasure-hunt-new-version)

#### [864. Shortest Path to Get All Keys](https://leetcode.cn/problems/shortest-path-to-get-all-keys/)

Get a question realated to treasure hunt questions asked before, but this was an newer version.

Given a char[][] representing a graph, where 'O' is empty space, 'X' is block which you can't go in, and 'T' is treasure. The method takes in a start posisiton and an end position, returns the minum path starting from start, end at end, and collect all treasures in the map.

This is really harder than previous questions.

这里的visited记录的是位置和已经收集到的宝藏 
如果已经经过了这个点但是回来了并且收集到了新的宝藏 这是可以的 但是如果是重复经过一个位置但是却没有收集到新的宝藏 这种情况是不需要的

-----
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTg1NjMzODI5NSwtMTAxNTQ0NjY1OCwxND
U3MTM5MDQyLC02MjY3NzE4MDYsLTkxNzI3OTg1MCwxNzIxNzYw
OTIwLC05NjcxMDYyOTUsMTQzMjc1OTM4NCwxNzU5MTEwNDYsMT
cxMTQxMzg1OCw5NDc4MzY1MjIsLTY4NzEwNjI1NiwxMzE3MzI5
NDcxLC0xMzkyMDk3MDI3LDM5Nzg3MTIzNiwxMTUwMzkxNDg2XX
0=
-->