


[Google | OA | July 2021](https://leetcode.com/discuss/interview-question/1359174/Google-or-OA-or-July-2021)

![image](https://assets.leetcode.com/users/images/a6095eb4-e6f1-4b35-81c0-d9216b6e67c8_1627123260.9641178.jpeg)

这里需要先进行质因数分解

-----

[Google Phone Screen](https://leetcode.com/discuss/interview-question/1225209/Google-Phone-Screen)

Total number of unique path from (1,1) to (n * m) 2D grid.  
Allowed move, top,bottom,right,left.

Follow up: if 2D grid is filled with some cost values, minimum cost to reach end cell from first cell.

题目有问题
Looks like some constraint is missing. If you can move in any direction then infinite length path is also possible if grid size is greater than or equal to 2x2. hence the number of paths will also be infinte.  
Example grid size is 2x2 and you start from (1,1).  
Paths can be -  
1,1 -> 1,2 -> 2,2  
1,1 -> 1,2 -> 1,1 -> 1,2 -> 2,2  
1,1 -> 1,2 -> 1,1 -> 1,2 -> 1,1 -> 1,2 -> 2,2  
1,1 -> 1,2 -> 1,1 -> 1,2 -> 1,1 -> 1,2 -> 1,1 -> 1,2 -> 2,2

---------

[Google phone round](https://leetcode.com/discuss/interview-question/1107192/Google-phone-round)

Given an integer start and list edges, compute the lengths of shortest path from start and other vertices. This is basically a Djikstra's algorithm. The function should return an array which will have the lengths. How would you optimise it from O(v ^ 2) to O(V + E) using Priority Queue and Adjacency list where 'V' is number of verices and 'E' is number of Edges

public int[] findMinimal(int start, int[][] edges) {  
return new int[] {};  
}

------------

[Google phone interview](https://leetcode.com/discuss/interview-question/815580/Google-phone-interview)

1.  this question i coundn't solve  
    it was something like  
    two methods are liks :** int getTime(string city1, string city2)** and  **list getconnectedCities(String city);**

now find minimumCost distnce between these 2 given cities. I dont have complete question. can you please help me with leetcode question reference.

-----------

[Google | Interview Questions | SWE Intern Summer 2023 US | Coding Exercise](https://leetcode.com/discuss/interview-question/2707370/Google-or-Interview-Questions-or-SWE-Intern-Summer-2023-US-or-Coding-Exercise)

-   First interview, I got a graph, start, and destination point. Each node had a value of length. I had to find the shortest path to the destination. Also, There was an infected node with a virus and the path wouldn't work if I get to that node. In addition, the infected node had a virality, meaning that all the neiborghs connected to this infected node would get infected as well depending on the value of this virality. Ex, if virality is 2 all the first and second neiborghs connected to this infected node would get infected so that we can't use them on our possible paths. To solve this question I had to get a good understanding of Breath First Search in a graph so Dijkstra's Algorithm would be great.

---------

[Media.net | OA | Minimum cost to buy oranges](https://leetcode.com/discuss/interview-question/1463104/Media.net-or-OA-or-Minimum-cost-to-buy-oranges)

![image](https://assets.leetcode.com/users/images/96c685b2-9eb3-4f94-9d27-2c6cbbe1ceca_1664476876.0734234.png)

**Problem Description**

You live in orange town. There are a lot of markets around that are connected with roads. These markats sell oranges at some prices. The town is not very well developed and they still use carts to transport goods from one place to the other. The roads connect two markets together and have two attributes associated with them. One is the price to go from one market to the other in an empty cart and the other is the tax factor. The tax factor is the number by which the price associated with a road needs to be multiplied, so it can go from one market to the other if you are carrying oranges in your cart. So if a road's original price was 5 coins and tax factor was 6, then in an empty cart it would take 5 coins to travel the road, but if the cart contained oranges, it would cost 5*6=30 coins.

You wonder what would be the cheapest way to buy oranges if you were initially at each market. You can either buy at the market you are at or travel to some other market, buy oranges there, and travel back to the original market

You are given an integer A denoting the number of total markets in orange town, an integer array B denoting the price of purchasing oranges at each market and a 2-D array C containing the information about the roads. First two values denote the market numbers that are bi-directionally connected via a road, 3rd value is the price, while the 4th one is the tax factor.

Find and return the required array. The minimum cost to buy oranges at each market such that the starting and ending point is that market.

**Problem Constraints**

2 <= A <= 1e5  
B.size() == A  
1 <= B[i] <= 1e7  
1 <= C.size() <= 2e5  
1 <= C[0] <= A  
1 <= C[1] <= A  
1 <= C[2] <= 1e3  
1 <= C[3] <= 5

**Input Format**

The first argument is the integer A. The second argument is the integer array B, and the third argument is the 2-D integer array C.

**Output Format**

Return an integer array as per the given problem.

**Example Input**

Input 1:

A = 2  
B = [11 1]  
C = [ [2 1 1 2] ]

Input 2:

A = 2  
B = [1 1]  
C = [ [2 1 2 4] ]

**Example Output**

Output 1:  
[4 1]  
Output 2:  
[1 1]

**Explanation**

Explanation 1:

For the first market, you can travel to the second market (1 cost), buy oranges there (1 cost) and return back to the first market (1*2 cost) for a total of 4 cost.  
For the second market, 1 is already the lowest you can get.

时间复杂度有问题 感觉只能对每一个节点进行dijkstra 这的限制是10^3的话是可以

----

[Interesting Question](https://leetcode.com/discuss/interview-question/2839991/Interesting-Question)

This is a question which is given as an assignment at institute. It is not related to any company. I think that this question is too tough to solve or hard considering N in hundreds.

There are no constraints for this problem. This question is very similar to this  [https://leetcode.com/problems/number-of-ways-to-arrive-at-destination/](https://leetcode.com/problems/number-of-ways-to-arrive-at-destination/)

Problem Two: Grandma Planner

Bruce is planning a trip to his grandma’s house. There are n towns, numbered 1 to n.  
Bruce starts in town 1, and his grandma lives in town n. Between each pair of towns is a  
road, and we are given the length (distance) of each road.

Bruce wishes to arrive at his grandma’s with a box of cookies, so he must buy it along the  
way. Some of the towns have cookie stores; Bruce is required to hit at least one of these  
cookie towns on his way to his grandma’s.

Our task is twofold. First, we must determine the minimum distance needed for Bruce to  
get from his starting point to his grandma’s house, picking up a box of cookies along the  
way. That minimum distance does not tell us how many options Bruce has for getting to  
his grandma’s. Maybe there’s only one way that he can do it, with all other routes requiring  
greater distance, or there are several routs all with the same minimum distance. Second,  
we are asked to determine the number of these minimum distance routes.

因为必须要经过一个cookie 所以从起点和终点进行两次遍历 计算到每一个cookie的最短距离 然后取最短的就是答案 遍历的时候还需要记录到每一个点的最短距离的次数 并且还需要多一个变量计算到当前cookie时之前是否已经经过别的cookie
对于求有多少种可能 遍历每一个cookie 看它到起点和终点的距离和是不是最短和 
如果是的话还需要判断它之前有没有经历过别的cookie 如果经历过别的那么直接忽略 因为肯定会在别的cookie那里计算过
-----a------b------c------
假设a b c 三个cookie a和c到起点和终点的距离和都等于最小值 那么以a为cookie的情况一定包含了以c为cookie的所有情况

---

[SALESFORCE / OA VERY HARD/ DEC 2022](https://leetcode.com/discuss/interview-question/2872087/SALESFORCE-OA-VERY-HARD-DEC-2022)

![image](https://assets.leetcode.com/users/images/08e2553b-a02f-43af-9351-a59c6b5cab18_1670050800.342167.png)
![image](https://assets.leetcode.com/users/images/c99feb58-440a-492e-8f6f-94c3f69f1d0e_1670050809.424557.png)
![image](https://assets.leetcode.com/users/images/896f4494-5fe0-4085-aa88-8af3e0672368_1670050815.6082582.png)
![image](https://assets.leetcode.com/users/images/26d4cc06-0531-44d1-b9ed-77baa63e068c_1670050822.580976.png)
![image](https://assets.leetcode.com/users/images/99aa2b71-d845-41f0-be0f-16682bcc51f7_1670050831.459337.png)

这里如果回退1个格子 那么就是偶数正好 奇数还要多走一次 
如果回退大于1个格子 那么都是偶数正好 所以和回退1个格子一样

----

[Graph interview question](https://leetcode.com/discuss/interview-question/3012832/Graph-interview-question)

ou are given an undirected weighted graph and an integer representing the total of minutes. Each node is a city and the weights on the edges are the minutes that take to reach the next city. Starting from position 0 find the path that passes the most number of cities(nodes) and ends in position 0 under the given total time ( you can pass multiple times one city as the graph is undirected). Could you think of an algorithm for this problem?

![image](https://assets.leetcode.com/users/images/36c0a753-22c1-426e-9632-6bb99ef999bd_1673081592.7019997.png)
Minutes: 68 (integer)  
Path: 0->1->5->2->3->2->0

这里dijkstra计算回去的最短距离 出发只能用dfs遍历所有情况 然后剪枝


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEyNjk4NjY2MDIsMjA2NzI2MDM2MCwtMT
kzMTk1MzMyMyw2Mzg5MjgyOTUsLTE4ODg4NDIzNzMsLTUxNzg4
NTY4LC0xMjQ2NDEyNjIyLDE3NTM3MTEzMTAsMTc2MzIyNzIyOC
wtOTM3MDcxMDI3XX0=
-->