[Google | OA | Remove maximum edges](https://leetcode.com/discuss/interview-question/2401866/Google-or-OA-or-Remove-maximum-edges)

**Problem statement:**

Given a tree with N nodes and N-1 edges. Each node has a value associated with it.  
You have to remove maximum number of edges such that the value of each resulted connected component is same.  
The value of a connected component is the sum of values of it's nodes.

**Note:**  Answer always exists as you can always remove zero edges, so that the whole tree remains connected.

  
**Input Format:**

First line contains integer N (number of nodes)  
Second line contains N integers, where ith integer is value of ith node.  
Next N-1 lines contains 2 integers u, v denoting there is an edge between node u and v of tree.

  
**Constraints:**

1 <= N <= 10^5  
1 <= a[i] <= 10^3

  
**Output:**

The maximum number of edges you can remove from the tree such that it holds the condition given in the problem.

  
**Example:**

![image](https://assets.leetcode.com/users/images/942f7b79-a03e-4c1a-b606-cda8ec30c0e1_1660042185.9176202.png)

**Input:**  
5  
3 2 1 1 1  
1 2  
1 3  
2 4  
2 5

**Output:**  
1

```
nums = [1,5,5,4,11]
edges = [[0,1],[1,2],[1,3],[3,4]]

tree=collections.defaultdict(set)
for i,j in edges:
     tree[i].add(j)
     tree[j].add(i)

def check(cur,prev,target):
    val=nums[cur]
    for kid in tree[cur]-{prev}):
       if i:=check(kid,cur,target)==-1:
           return -1
       val+=i          
    return val%target if val<=target else -1

tot=sum(nums)
for n in range(min(tot//max(nums),len(nums)),0,-1):  # for simplicity, i do not use O(n^1/2) approach to find all factors here
    if not tot%n and check(0,-1,tot//n)==0:
       return n-1
```

----

[Google | Phone Interiew](https://leetcode.com/discuss/interview-question/2279055/Google-or-Phone-Interiew)
 
Question:  
Given some names and their values. Write a function which takes name as input and outputs full value, also replacing the name in the value if present.

```
AXA = '/leetcode/config'
BYB =  '/%AXA%/interview/corner/file'
LCLS = '/tmp/file/usr/shared/%BYB%'

Input: BYB
Output: '/leetcode/config/interview/corner/file'

Input: LCLS
Output: '/tmp/file/usr/shared/leetcode/config/interview/corner/file'

```

可以使用dfs 类似力扣excel表格 然后带上记忆化

------------------

[Google](https://leetcode.com/discuss/interview-question/1807365/Google)
We are given a list of Employees with their  **ID**,  **manager ID**, and  **Name**. The question ask us to print the names of all the employees in a hierarchy.  
**Note:**  [The  _**Ultimate manager**_  is the one with the  _**highest ID Value**_  and whose  _**ID**_  is same as the  _**Manager ID**_]

List of Employees  **INPUT**:-

```
    { id: 8, managerId: 8, name: "Alice" },
    { id: 2, managerId: 8, name: "Bob" },
    { id: 3, managerId: 2, name: "Emp3" },
    { id: 4, managerId: 3, name: "Emp4" },
    { id: 5, managerId: 4, name: "Emp5" },
    { id: 6, managerId: 3, name: "Emp6" },
    { id: 7, managerId: 8, name: "Emp7" },
];

```

**Output:-**

```
// ---Bob
// ------Emp3
// ---------Emp4
// ------------Emp5
// ---------Emp6
// ---Emp7
```

dfs遍历即可

-------------------------

[Google | onsite](https://leetcode.com/discuss/interview-question/1921324/Google-or-onsite)
remove Leaves of Binary Tree , like (366. Find Leaves of Binary Tree) , but need remove

follow up: 1. remove new created leaves first (after remove 4,5, we need remove 2 immediately..then 6,7 ....)  
1  
/ \  
2 3  
/ \ / \  
4 5 6 7  
follow up: 2 remove new created leaves last

答案: 和力扣366一样

-------------

[Google | onsite](https://leetcode.com/discuss/interview-question/1921039/Google-or-onsite)

A binary tree, return all root-to-node paths. For example,  
1  
/ \  
2 3  
\  
5  
return : ["1","12","125","13"]

-----------------

[Google | Onsite | USA](https://leetcode.com/discuss/interview-question/1856575/Google-or-Onsite-or-USA)

Given a n-ary tree, print the nodes in the required format.  
**Follow-up:**  given the printed string, make the tree and return the root.

```
Example:
		   1
   /       |       \
  2        3        4 
  |       /  \      |
  5      6    7     8
              |
			  9
print the output in this format (append a dash "-" to each node value and keep adding dashes for each level)
-1
--2
---5
--3
---6
---7
----9
--4
---8
```

------------------------

[Google | OA](https://leetcode.com/discuss/interview-question/1586927/Google-or-OA)

Question 1:  
You are given an array of integers. Your task is to create pairs of them, such that every created pair has the same sum. This sum is not specified, but the number of created pairs should be the maximum possible. Each array element may belong to one pair only.

```
    Write a function:

```

class Solution { public int solution(int[] A); }

that, given an array A consisting of N integers, returns the maximum possible number of pairs with the same sum.

```
    Examples:

    1. Given A = [1, 9, 8, 100, 2], the function should return 2. The pairs are (A[0], A[1]) and (A[2], A[4]); the sum of each pair is 10.

    2. Given A = [2, 2, 2, 3], the function should return 1. Although, for instance, A[0]+A[1] = A[0]+A[2], the pairs (A[0], A[1]) and (A[0], A[2]) cannot exist at the same time, because they both contain a common element, A[0].

    3. Given A = [5, 5], the function should return 1.

    Assume that:

    N is an integer within the range [2..50];

    each element of array A is an integer within the range [1..1,000].

    In your solution, focus on correctness. The performance of your solution will not be the focus of the assessment.
```

available = [True, True, .......]
dfs(sum1)
每次先看哪些节点available 然后枚举遍历这些节点

--------------

[Google | Phone Interview | Rejected](https://leetcode.com/discuss/interview-question/1593355/Google-or-Phone-Interview-or-Rejected)

Cord tree
1. given an index, get the character at that index
2. given the left and right index, get the substring between the border

-----------

[Google | L3 - L4 | Europe | Reject](https://leetcode.com/discuss/interview-experience/1760495/Google-or-L3-L4-or-Europe-or-Reject)

You are given a list of points in a 2d plane. Points are all placed in (0, 0) - (1, 1) sqaure.  
Return the id of smallest possible squre that all points fit into.  
Square ids can be indefintelly shrinked in such a way:

![image](https://assets.leetcode.com/users/images/a2fc8af6-47c9-470b-b62a-2e6bda6c46d3_1644490463.9130516.png)

List of points can looks something like this: [[0.312, 0.1][0.410, 0.198][0.289, 0.03][0.11, 0.2]]

简单明了

-----------

[Google Phone Interview](https://leetcode.com/discuss/interview-question/1442346/Google-Phone-Interview)

This was the question asked at my recent Phone Interview with Google.  
Given a 2-D matrix that contains binary digits of 1's and 0's. Return the boundary coordinates of each region covered by 1's.

Example:

Input:

0 0 0 0 0 0  
0 1 1 0 1 1  
1 1 1 1 0 1  
0 1 1 0 1 1  
0 0 0 0 1 0

Output:

Here we have two region boundaries and they are marked with numbers 2 and 3.  
(For representation alone. The result should just be the boundary coordinates)

0 0 0 0 0 0  
0 2 2 0 3 3  
2 1 1 2 0 3  
0 2 2 0 3 3  
0 0 0 0 3 0

The expected output in this case is:  
Two regions boundary points.  
Region 1-  
[[1,1],[1,2],[2,0],[3,1],[3,2],[2,3],  
Region 2-  
[1,4],[1,5],[2,5],[3,4],[3,5],[4,4]]

The result should be a List containing the boundary coordinates marked with the numbers 2 and 3.

P.S: The region does not check for diagonal 1's. (It only considers top,bottom,right and left to mark the regions)

答案:
"The result should be a List containing the boundary coordinates marked with the numbers 2 and 3."

This makes it seem like they don't care if you distinguish between islands. If this is true, then this is pretty easy. You just have to iterate across all '1' cells and return the [i, j] index of any cell that is  _not_  completely surrounded by 1s in all four directions.

If they do care about distinguishing between islands, it's still not too bad - just do a regular island BFS/DFS, then remove any cell that is completely surrounded by 1s in all four directions. This effectively does the same thing as the solution above, but it gives you the cells separated by their island.

Similar question: [https://leetcode.com/problems/coloring-a-border/](https://leetcode.com/problems/coloring-a-border/)

--------------

[Chances of google L4](https://leetcode.com/discuss/interview-question/1490881/Chances-of-google-L4)

find number of islands in a matrix with 0 and 1.  
Followup:  
[https://cses.fi/problemset/task/1192](https://cses.fi/problemset/task/1192)

-----------

[Google Online Assessment Question](https://leetcode.com/discuss/interview-question/1368797/Google-Online-Assessment-Question)

**Second question**  was based on to find count of subsets with given sum.  
There are Q number of queries and each query contains two integers, first integer represent the type and second integer represent value

type 0: insert value x  
type 1: remove value x  
type 2: find count of subsets of sum x

input type:  
7  
0 1  
0 2  
2 3  
0 2  
2 3  
1 2  
2 1

ouput:  
1 2 1

Explanation :-  
1st Query -> [1]  
2nd Query -> [1, 2]  
3rd Query -> {1,2} => no of subsets with sum = 3  
4th Query ->[1,2,2]  
5th Query -> {1,2}, {1,2} => no of subsets with sum = 3  
6th Query -> [1,2]  
7th Query -> {1} -> no of subsets with sum = 1

类似 [40. Combination Sum II](https://leetcode.cn/problems/combination-sum-ii/)
维护有序序列意义不大 因为没法像数组一样定位

---------------

[Google Interview](https://leetcode.com/discuss/interview-question/1355948/Google-Interview)

Got question similar to  [https://leetcode.com/problems/reconstruct-itinerary/](https://leetcode.com/problems/reconstruct-itinerary/)  but also the list has depart times and arrive times

[ABC 9:00 DEF 1:00,  
DEF 1:30 GHI 3:00,  
DEF 12:00 GHI 2:00,  
JKL 1:00 MNO 16:00]

so the first element is depart ABC at 9 and arrive at DEF and 1:00  
Return true/false if there is a path between start city and end city.

Example:  
ABC - GHI returns true  
ABC - MNO returns false.

答案: dic = defaultdict(tuple)   (depart time, destination, arrive time)

----------

[Google Phone Interview](https://leetcode.com/discuss/interview-question/1123994/Google-Phone-Interview)

Had Google phone interview , question was very broad(context was parking lot). Job is to figure out the path to exit the parking lot.  
It can be easily considered as a 2D matrix with some blocks. You need to find out the path to the exit. Start From (x,y) & exit at (rows-1,cols-1).  
Gave multiple approaches as a thought process --> BFS and DFS. Interviewer expected asked me code the DFS solution and also come up with test cases. Was able to provide an optimal solution using DFS.  
Got a call back from Recruiter saying a blanket statement that I need to improve on DS and Algo. I asked her for specific feedback as to where I was wrong so that I can improve. She told, she can't give complete feedback as it is company policy. I wonder what company policy withholds one from giving proper feedback.  
Location : India.  
Please do let me know what you think of it, based on your experience

答案: 使用dfs即可 需要使用一个visited保存访问过的节点 和 path 路径

-------------

[Google | Onsite | Phone Interviews](https://leetcode.com/discuss/interview-question/882062/Google-or-Onsite-or-Phone-Interviews)

```

https://leetcode.com/discuss/interview-question/125301/Find-longest-consecutive-path-in-a-matrix

Essentially this question but a starting point is given.
So it is not the max possible length overall but max possible length from a given starting point
```

Given a 2d matrix, each element in this matrix is unique, i.e. in a matrix of m*n, it contains integers from 1,2,3,..m*n.  
Find the longest consecutive path in it. You could go in the four directions: right, left, up and down, no other directions allowed.

e.g.

in this matrix:

```
int[][] grid = new int[][]{
				{1,  2, 13,  5},
				{11, 10,  9,  6},
				{3,  4,  8,  7},
				{12, 14, 15, 16},
		};

```

The result should be this list: 5, 6, 7, 8, 9, 10, 11

------------

[Google online assessment](https://leetcode.com/discuss/interview-question/806141/Google-online-assessment.)

Generalization of the maximum path sum  [https://leetcode.com/problems/binary-tree-maximum-path-sum/solution/](https://leetcode.com/problems/binary-tree-maximum-path-sum/solution/)

Consider any node in the given graph as the root of an n-ary tree and apply the same algorithm

----------

[Bloomberg Team X || rouund 1](https://leetcode.com/discuss/interview-question/2611397/Bloomberg-Team-X-oror-rouund-1)

Hey guys,

Just completed OA for bloomberg for SDE3 role. It was held on hacker rank.

The interviewer was kind, and patient.  
The Question was to flatten a linkedList with downNode values.

eg :  
1 - 2 to 1-3-2  
|  
3

-----------

[Google | Onsite | Maximum number of orders from ribbon inventory](https://leetcode.com/discuss/interview-question/1754070/Google-or-Onsite-or-Maximum-number-of-orders-from-ribbon-inventory)

You are given an integer array  `Inventories`  representing the ribbon inventories, where  `Inventories[i]`  represents the length of the  `ith`  ribbon, and an array of  `orders`. Each  `order`  in  `orders`  is an array of integers, representing the ribbons needed with certain lengths for that order. For example, if order = [1,2], then that means this order need a ribbon with length 1 and a ribbon with length 2. You may cut any of the ribbons  **in the inventory**  into any number of segments of positive integer lengths, or perform no cuts at all. However, you  **cannot**  combine two ribbons in the inventory to form a longer ribbon and fullfil an order. Each segment/ribbon in the inventory cannot be reused. The question is, what is the maximum number of orders that can be fulfilled?

Example 1:  
Input:  `Inventories = [1,8,7], orders = [[1, 2], [4, 3, 6]]`  
Output:  `2`  
Explanation:  
First cut inventories[1] into [2,6], then the inventory become [1, 7, 2, 6]. Use inventories[0] and inventories[2] for the first order. The rest of the inventories are [7,6], then cut the ribbon with the length of 7 into 4 and 3 to fulfill the second order. So in total 2 orders are fulfilled.

Example 2:  
Input:  `Inventories = [1,2,3], orders = [[3, 3], [4]]`  
Output:  `0`  
Explanation:  
None of the orders can be fulfilled. Notice we cannot combine inventories[0] and inventories[1] for orders[0].

Example 3:  
Input:  `Inventories = [3], orders = [[2]]`  
Output:  `1`  
Explanation:  
Cut the ribbon into 2 and 1, and use the first segment for that order.

I found this queston so hard that I cannot even come up with a solution better than bruteforce. Please forgive my poor English.

答案:
这题是np-hard题目 
首先二进制枚举选择哪些orders 然后check
二进制枚举可以使用  **Gospers-Hack**

--------------

[Microsoft | OA Codility](https://leetcode.com/discuss/interview-question/2056068/Microsoft-or-OA-Codility)
![Battleships is a game played on a rectangular board. You are given a representation of such a board of size N (height) x M (w](https://media.cheggcdn.com/media/4cf/4cf56d1b-9bae-4b5d-bc5b-e4d66db2a3aa/phpWysgec)
![def solution (B)
that, given an array B consisting of N strings of length M each, returns an array R of three integers, such](https://media.cheggcdn.com/media/38a/38a43679-cc2e-4ca8-9b88-f0b13e330349/phpWBtImp)

因为只有三个形状 dfs即可

----------

[Tiktok OA](https://leetcode.com/discuss/interview-question/2646621/Tiktok-OA)

![image](https://assets.leetcode.com/users/images/c02758b4-7846-4f06-adf9-871e0e226148_1664640163.6964607.png)

-----

[Google | Onsite | Order of runners | Tree edge remove | Repair parentheses](https://leetcode.com/discuss/interview-question/2638572/Google-or-Onsite-or-Order-of-runners-or-Tree-edge-remove-or-Repair-parentheses)

**#Coding Interview 2**

Given a tree of N vertices and an edge E, calculate the number of vertices in each of the connected components remaining after removal of the edge.

After he gave follow up question:  
Given a tree of N vertices and a list of M edges E, calculate number of vertices in each of the connected components remaining after removal of each edge Ei  _independently_.

![image](https://assets.leetcode.com/users/images/388aeec4-3778-4634-8df4-71d816675abf_1664454493.443516.png)

1,3  
5,2  
1,3

Result:  
3,8  
2,9  
3,8

对于删除的边 可以用一个dic = defaultdict(lambda:Counter())来记录index

-------

lucid oa 被删除了
题目是 给定一个🌲 一些节点的值为1代表硬币 一些节点的值为0 要求一条最短的路径 使得可以获得所有的硬币 路径的起始点任意 但是起点和终点必须一样 获得硬币的方式为 如果你在一个节点 那么可以获取路径最大为2内的所有节点上的硬币

https://leetcode.com/discuss/interview-question/2751188/Lucid-OA-new-grad-SWE 

![image](https://assets.leetcode.com/users/images/1ef8a0eb-dcda-4762-bc28-8bc7563bfa6c_1666935515.1989486.png)
![image](https://assets.leetcode.com/users/images/752b7014-d4ea-4448-9c31-3670f5496535_1666935514.7778208.png)
![image](https://assets.leetcode.com/users/images/90ae341e-b5c4-4eec-90e7-a51ee9ed3426_1666935514.902003.png)

答案: 首先先计算经过哪些节点一定可以获得所有的硬币 类似于监控二叉树 不过这里的路径是2 

total = [] #表示所有的需要经过

    def dfs(node):
      if not node:
        return (-1, -1)
      x1, y1 = dfs(node.left)
      x2, y2 = dfs(node.right)
      if y1 == 0 or y2 == 0:
        total.append(node)
        return (1, -1)
      elif y1 == 1 or y2 == 1:
        if x1 == 1 or x2 == 1:
          return (0, -1)
        else:
          return(-1, 0)
      elif node.val == 1:
        if x1 == -1 and x2 == -1:
          return (-1, 1)
        else:
          return (0 if x1 == 1 or x2 == 1 else -1, -1)
      else:
        return (0 if x1 == 1 or x2 == 1 else -1, -1)
  
 return (x, y) 
这里的x表示当前节点或者下面节点的监控情况 如果是1 表示当前节点放一个摄像头 如果为0表示下面一层节点有一个摄像头 如果为-1 表示没有摄像头
这里的y表示当前硬币的距离 1表示当前节点是一个硬币 0表示下面一层存在一个硬币 -1表示没有硬币

 然后就是求连接total这些节点的最短路径加起来乘2
 再次使用dfs 

     sum1 = 0
     def dfs(node):
       if not node:
         return 0
       res = []
       for child in node.children:
         x = dfs(child)
         if x != 0:
           res.append(x)
       if not res and not node.val:
         return 0
       if len(res) == 1 and not node.val:
         return res[0] + 1
       sum1 += sum(res)
       return 1

------

[Airbnb coding round 2](https://leetcode.com/discuss/interview-question/2695021/Airbnb-coding-round-2)

A patron at a restaurant tells the waiter that out of the given menu, they’d like to order exactly $15.05 worth of appetizers. He offers the waiter computer science literature to help solve the problem.

// You are the waiter in this story. Given a total sum for appetizers (in the example $15.05), write a program which writes to the screen what the customer’s order could be.

// Menu:  
// (“Fruit”, 2.15);  
// (“Fries”, 2.75);  
// (“Salad”, 3.35);  
// (“Wings”, 3.55);  
// (“Mozzarella”, 4.20);  
// (“Plate”, 5.80);

// Examples  
// possibleOrders(4.30) -> [[“Fruit”, “Fruit”]]  
// possibleOrders(4.90) -> [[“Fruit”, “Fries”]]  
// possibleOrders(5.50) -> [[“Fries”, “Fries”], [“Fruit”, “Salad”]]

// possibleOrders(15.05) -> [[“Fruit”, “Wings”, “Wings”, “Plate”], [“Fruit”, “Fruit”, “Fruit”, “Fruit”, “Fruit”, “Fruit”, “Fruit”]]  
// 2.15+3.55+3.55+5.80 = 15.05  
// if not possible return empty list  
// Unique possible combination solution

答案: DFS回溯即可

-----

[Google phone screen question: Find the direction map of a given matrix.](https://leetcode.com/discuss/interview-question/2665860/Google-phone-screen-question:-Find-the-direction-map-of-a-given-matrix.)
   
   Given an matrix populated with numbers from 1-7. Each of the number represents a direction in the entire matrix. e.g: if matrix[0][0] = 2, and if 2 represents 'B', then the only valid move is to go down.

From the given input matrix find any single possible direction map that allows us to move from top left to bottom right cells.

Direction map is the, map defining the direction each number means. There are only 4 valid directions. 'U' - Up, 'D' - Down, 'L' - Left, and 'R' - Right.

Sample input:

1 2 6 4  
3 1 2 3  
7 5 4 6  
3 7 2 1

Output - {1: 'R', 2: 'D', 3:'L', 4: 'R', 5: 'L', 6: 'D',7:'L'} or {1: 'D', 2: 'R', 3: 'R', 4: 'D', 5: 'R', 6: 'D',7:'L'} or anything that can get us answer.

答案 简单dfs+backtracking即可 需要使用seen记录访问过的节点

----

[Tough Question OA India Infosys (Harder than Amazon)](https://leetcode.com/discuss/interview-question/2731930/Tough-Question-OA-India-Infosys-%28Harder-than-Amazon%29)

![image](https://assets.leetcode.com/users/images/008bd7f1-53d2-4d9c-9d38-1d68597bf641_1666434350.8451607.jpeg)
![image](https://assets.leetcode.com/users/images/ab66eaf2-02c1-4679-8b2c-0ee21cd324cb_1666434418.429493.jpeg)
![image](https://assets.leetcode.com/users/images/fc65b739-7263-410a-8e80-e069325d12cc_1666434424.779617.jpeg)

先dfs计算出总路径 x 然后bfs计算出起点到终点的距离 y 最后x-y即可

---
  
[Microsoft | OA](https://leetcode.com/discuss/interview-question/1803811/Microsoft-or-OA)

Given an n-ary tree with N nodes numbered 0..N-1. Each node is marked as 'a' or 'b'.  
Find longest path in a tree with alternating characters.

Input : parent array of size n, string tag

```
Example 1 :
parent : [-1, 0, 1] , tag ="abb"
       0 'a'
	   |
	   1 'b'
	   |
	   2 'b' 
	   
Path length = 2 (0->1)


Example 2:
parent : [-1, 0, 0] , tag ="abb"
        0 'a'
	 /     \
   1 'b'   2'b'
   
Path length = 2 (1->0->2)
```

----

[Google| telephonic round](https://leetcode.com/discuss/interview-question/2771105/Googleor-telephonic-round)

recently, one of my friend gave google interview and the question goes

Given a hierarchy of managers, as a tree, with every mode value is the salary of the manager, find out the number of managers underpaid.  
How are they underpaid? if salary of manager is lesser than the average of its children nodes salary.

I understand the problem, just dont know how to optimally aproach it... any solutions please?

------

[Bloomberg London | Phone | New Grad](https://leetcode.com/discuss/interview-question/2773700/Bloomberg-London-or-Phone-or-New-Grad)

![image](https://assets.leetcode.com/users/images/4700aa48-e6c3-4032-8667-e8625369a89a_1667478459.2025282.jpeg)

----
     
https://www.chegg.com/homework-help/questions-and-answers/given-tree-treenodes-vertices-labeled-1-treenodes-vertex-associated-value--define-beauty-v-q101036741

![Given a tree of tree_nodes vertices labeled from 1 to tree_nodes, each vertex is associated with a value \( a[i] \). We defin](https://media.cheggcdn.com/study/017/0175c9dd-e74e-46e0-8242-b7a586dd12d9/image)
![For vertex 1 , beauty is \( \operatorname{dis}(1,1) * 3+\operatorname{dis}(2,1) * 4=0 * 3 \) \( +1 * 4=4 \).
For vertex 2 , b](https://media.cheggcdn.com/study/4bd/4bd767d2-b085-47c7-8894-e9aaf61d3bfe/image)
![Sample Case 0
Sample input
Sample Output
8
Explanation
For vertex 1 , distances to nodes 1,2 and 3 are 0 ,
1 , and 2 . Its be](https://media.cheggcdn.com/study/7fe/7fe7fc4a-57ec-4e84-bd55-2f53b67ffcc7/image)

----
     
[Media.net online coding quiestion online assessment](https://leetcode.com/discuss/interview-question/2748873/Media.net-online-coding-quiestion-online-assessment)

![image](https://assets.leetcode.com/users/images/73cd93cb-bda0-48f7-9898-7df6f54a2638_1666869445.5854404.png)
![image](https://assets.leetcode.com/users/images/52cdec36-d7b1-4dd9-a354-f25918c1ecd9_1666869462.536593.png)

----

[Media.net OA|SDE|2022](https://leetcode.com/discuss/interview-question/2803576/Media.net-OAorSDEor2022)

![image](https://assets.leetcode.com/users/images/e6d9b7bd-50e5-4bed-b561-1140fc7d2e5c_1668173206.950137.png)
![image](https://assets.leetcode.com/users/images/c017b7f0-386a-4244-901b-21385072d9b2_1668173207.2163472.png)

dfs即可 注意对于每一个节点 摇的前几次是没有苹果掉下来的 后面才会有苹果掉下来 所以complete tree 是关键 这样前几次没有苹果掉下来的次数是一样的 然后计算苹果能往下掉多少次 假设所有父节点中掉落苹果的最大次数为x 那么对于当前节点 它掉落的次数至少为x-1次 第x次的时候苹果存在当前节点还没有掉下去 再计算父节点中其他节点的掉落次数之和 假设为sum 取min1 = min(capacity-1, sum) 最后答案就是x + min1

---

[Media.Net(Directi) OA On campus Questions :)](https://leetcode.com/discuss/interview-question/2639890/Media.Net%28Directi%29-OA-On-campus-Questions-:%29)

![image](https://assets.leetcode.com/users/images/c2eb8756-db23-47b5-9674-02edee503efc_1664476866.0531662.png)

和那个chegg类似

---

[Google | Onsite | Coding Interview](https://leetcode.com/discuss/interview-question/2836771/Google-or-Onsite-or-Coding-Interview)

Given a (n-ary)tree and a list of node values such as [“a", "b", "c”], determine if the  
list of nodes exists in the tree in that order.

```
             O(r)
           /       \
          O          O(a)
        /   \         /  \    \        \
       O   O       O(b)  O(z) O(d)
                  /
                O(c)

```

[“a", "b", "c”]  
["b", "a", "c"] => false  
["a", "c"] => false  
[] => true  
null => true  
[r a b] => true  
[r a b z] => false  
[r] => true  
[a] => true  
[c] => true

I tried a recursive approach. But not sure if it is optimal. Curious to know other/optimal ways to solve this.

如果是offline的话 那么可以构造一个trie对于所有的query

----
   
[DoorDash | SDE | Tech Phone Interview | 2021](https://leetcode.com/discuss/interview-experience/1482159/DoorDash-or-SDE-or-Tech-Phone-Interview-or-2021)

Q. Compute the total number of operations required to convert one N-ary tree to another.

```
class TreeNode {
        String key;
        int value;
        List<TreeNode> children;
    }


```

Tree-1

```
               a(1)                                                
            /       \                                                          
         b(2)       c(3)                                               
        /     \         \                                                         
      d(4)    e(5)      f(6)      

```

Tree-2

```
            a(1)
                \
               c(3)
                   \
                   f(66)


```

Operations:

1.  b(2) was removed from Tree-1 (Count = 1)
2.  Childrens of b(2) are removed, i.e. d(4) & e(5) (Count += 2)
3.  f(6) was updated to f(66) in Tree-2 (Count += 1)

Total Operations done  **(Count = 4)**

对tree-a进行dfs 并且设置另外一个dfs负责求某个节点构成的树的节点数目 要么是删除 要么是增加 要么是修改

----
  
[Snowflake | Phone Screen | Patching Array](https://leetcode.com/discuss/interview-question/424385/Snowflake-or-Phone-Screen-or-Patching-Array)

I recently interviewed with Snowflake for their Data Platform team. So, as there are not many posts regarding Snowflake's interview process. I would like to shed some light on their interview process and also some of the questions that I was asked during the phone screens.

**Initial Recruiter Phone Screen (25 mins)**  - Basically the recruiter goes through your interests and gives you some background about the different teams at Snowflake. Some information gathering regarding any outstanding offers that you might have and some behavioral questions. After this they setup two phone screens with two of their engineers.

----------

**Phone Screen 1 (60 mins)**  
10 mins - General Introduction (Background and Resume)  
40 mins - Coding  
10 mins - Any questions regarding Snowflake

So the interviewer told me that he is going to ask me two questions starting with an easier problem.  
Q1 - Remove all the element of B which are present in A (A and B are arrays). Both the array can consist of duplicates and are not sorted.  
Q2 -  [https://leetcode.com/problems/binary-tree-inorder-traversal/](https://leetcode.com/problems/binary-tree-inorder-traversal/)  He told me I would get a bonus point if I could do it in constant space (Basically using Morris Inorder Traversal)

----------

**Phone Screen 2 (60 mins)**  
He skipped the 10 min resume review portion as I had already talked about it in my previous interview as he wanted to give me more time for the problem.  
50 mins - Coding  
10 mins - Any questions regarding Snowflake

Q1 -  [https://leetcode.com/problems/patching-array/](https://leetcode.com/problems/patching-array/)

I feel the interviewers were super nice and helped me when I got stuck. The asked many follow ups on code optimization.

Once you pass the phone screen there is a 3 round onsite including Coding, System Design, Lunch and Behavioral.

morris遍历

-----

[Need help understanding the solution](https://leetcode.com/discuss/interview-question/2877365/Need-help-understanding-the-solution)

There are m campus bus routes. The i-th one (0 <= i < m) takes you from building u_i to building v_i (but not the other way around). These buses run very frequently. A building x is accessible from a building y if you can get from y to x taking at most two buses. how many buildings the most accessible building is accessible from and list all of them.

Sample Input 1  
6 5  
0 1  
1 2  
2 3  
3 4  
4 5  
Sample Output 1  
3  
2 3 4 5  
Sample 1 Explanation  
The first line indicates that there are 6 buildings and 5 bus routes.  
The bus routes are described in the next 5 lines. For instance, the second route takes you from building 1 to building 2.  
Building 0 is only accessible from itself. Building 1 is accessible from building 0 and itself. The remaining buildings are all accessible from 3 buildings, including themselves.

Sample Input 2  
6 8  
0 1  
2 1  
1 3  
4 3  
3 5  
0 1  
3 0  
1 0  
Sample Output 2  
5  
0 3

dfs只要进行两层 用一个cnt记录每一个元素的accessible的个数

---

[can anyone solve this question?](https://leetcode.com/discuss/interview-question/2870539/can-anyone-solve-this-question)

![image](https://assets.leetcode.com/users/images/d1117a63-dc09-46b1-b47d-a5db5b7d84d8_1670001662.0808864.jpeg)
![image](https://assets.leetcode.com/users/images/012df55f-0cee-4372-8155-ed3baed2ca5c_1670001661.5800242.jpeg)

不知道数据范围 暴力方式是n^3

----

[Maximum Disjoint Subtree Product](https://www.hackerrank.com/contests/world-codesprint-10/challenges/maximum-disjoint-subtree-product/problem)

先进行预处理 对每个节点计算4个数值 1. 以当前节点为根的子树的maxsum(必须包含当前节点) 2. 以当前节点为根的子树的maxsum(不一定包含当前节点) 3. 以当前节点为根的子树的minsum(必须包含当前节点) 4. 以当前节点为根的子树的minsum(不一定包含当前节点)
然后就是dfs遍历

    def dfs(node, sum1, hi)

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEyMTQ3MTc4OTgsMTk0NjAyNTMwNCwtND
YwMjk5NTMwLDEzMjg3Mzc1MDEsLTEzMTc5OTM4MjgsODM0NDM5
Nzc3LC05NDM1MjU3LDk2MDY2ODg0MSwtMTUzMDc3NTA0MCwtMT
MzMzU1MzI0LDEyNjAwNjQ5NzMsNDUyODU1NDgwLC0xNjU5Mjg4
MzY2LC04NzQ3NTAyNDUsMTA3MTU3ODg0OCwxNTg5NjQ3MDQxLD
E5NTAzMjAxOCwtMTkxNjM3OTM5MywxNDEyNDE3NDczLC0xMTY2
MTEwNzQxXX0=
-->