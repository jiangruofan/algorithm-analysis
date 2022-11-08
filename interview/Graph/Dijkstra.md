


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

时间复杂度有问题 感觉只能对每一个节点进行dijkstra


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE3MDE5NjA0MDEsMTc2MzIyNzIyOCwtOT
M3MDcxMDI3XX0=
-->