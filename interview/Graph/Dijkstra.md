


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


<!--stackedit_data:
eyJoaXN0b3J5IjpbMTc2MzIyNzIyOCwtOTM3MDcxMDI3XX0=
-->