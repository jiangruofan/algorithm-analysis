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
        if x1 == -1 or x2 == -1:
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
   x = dfs(node.left)
   y = dfs(node.right)
   if x != 0 and y != 0:
     sum1 += x + y
     return 1
   elif node in total:
     sum1 += x + y
     return 1
   elif x == 0 and y == 0:
     return 0
   else:
     return 1 + (x if x != 0 else y)
     
     
   
  
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTYxODE0NzkxNywxMTU1MTE2NDg4LC0xNj
Y0MTg3MDUsLTE3MTU4ODE0NCwzODk0Nzc5MzYsLTQ0NzQzMTgw
MSw5ODg5MTA1OCwtMTY4NzA5NTY5OCwtMTIyNzYzMjYwMCwxMD
QwOTAwMDY3XX0=
-->