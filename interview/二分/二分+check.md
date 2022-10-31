[Facebook | Google | London | Offers](https://leetcode.com/discuss/interview-question/1110505/Facebook-or-Google-or-London-or-Offers)

-   check if there is a square of 1s in a 2d matrix (that contains 0s and 1s). the square has the size of at least sqrt(min(N,M)). the input either has one valid square or not (all 0s).
    

```
bool hasSquare(int[][] matrix)
```

-----------

[Google | OA | SDE (2020)| India](https://leetcode.com/discuss/interview-question/805468/Google-or-OA-or-SDE-%282020%29or-India)

1.  Given array A of N Integers a1  ,a2, a3...... aN  . You are also given two integers S and M. You can pick subarray of size S where you have to perform M operation by incrementing the value of each element value by 1. Find the maximum value of minimum value in array A.  
    Example

```
Input:
N = 6 ,M = 5 ,S =2
1 2 3 4 5 6
Output:
4
Explaination:
1st opertaion subarray index range (0,1) 2 3 3 4 5 6
2nd opertaion subarray index range (0,1) 3 4 3 4 5 6
3rd opertaion subarray index range (0,1) 4 5 3 4 5 6
4th opertaion subarray index range (2,3) 4 5 4 5 5 6
5th opertaion subarray index range (0,1) 5 6 4 5 5 6
```

----------

[Google | Phone Screen | Salary Adjustment](https://leetcode.com/discuss/interview-question/351313/Google-or-Phone-Screen-or-Salary-Adjustment)

Give an array of  `salaries`. The total salary has a  `budget`. At the beginning, the total salary of employees is larger than the  `budget`. It is required to find the number  `k`, and reduce all the salaries larger than  `k`  to  `k`, such that the total salary is  **exactly equal**  to the  `budget`.

**Example 1:**

```
Input: salaries = [100, 300, 200, 400], budget = 800
Output: 250
Explanation: k should be 250, so the total salary after the reduction 100 + 250 + 200 + 250 is exactly equal to 800.

```

You can assume that solution always exists.

Related questions:

-   [Array Adjustment](https://leetcode.com/discuss/interview-question/349612/Google-or-Phone-Screen-or-Array-Adjustment)

求一个前缀和 排个序

---------

[Google | New Grad | Onsite 2022 | USA](https://leetcode.com/discuss/interview-question/2104302/Google-or-New-Grad-or-Onsite-2022-or-USA)

You have a table with two columns with some text in them. Now you need to find column width such that the height of the table is minimum.

```
-------------------------------------
| some text            | Description  |
| some text            | some text    |
| some text            | some text    |
| some text            |              |
------------------------------------


```

Given,  
table width = 20  
text1 =  `some string`  
text2 =  `some string`  
return width of a column such that height is minimum

答案: 对高度进行二分

----------

[Snowflake | OA | 2022 | Minimize Array Value](https://leetcode.com/discuss/interview-question/2146013/Snowflake-or-OA-or-2022-or-Minimize-Array-Value)

Given an array arr of n positive integers, the following operation can be performed any number of times. Use a 1-based index for the array.

-   Choose any i such that 2<=i<=n
-   Choose any x such that 1<=i<=arr[i]
-   Set arr[i-1] to arr[i-1]+x
-   Set arr[i] to arr[i]-x

Minimize the maximum value of arr using the above operation and return value.

Example: arr=[1,5,7,6]  
arr becomes [1,9,3,6] after choosing i=3 and x=4 as x<=arr[3], i.e. 4<7  
arr becomes [5,5,3,6] after choosing i=2 and x=4 as x<=arr[2]  
arr becomes [5,5,4,5] after choosing i=4 and x=1 as x<=arr[4]  
output = 5

Example : arr = [5,15,19]  
output = 13

Example : arr = [10,3,5,7]  
output = 10

答案: 题目的意思就是可以把任意一个数往左边移

--------

[Thoughts on this good problem ?](https://leetcode.com/discuss/interview-question/2553496/Thoughts-on-this-good-problem)

You are playing a game, in which, in each turn, you can reduce the number of blocks in a pile by at max “k” blocks. Note that, in each turn, you can remove blocks on only one pile. You have t number of turns in which you are supposed to remove all blocks.

Determine minimum value of k to remove all blocks in t turns.

Example 1:  
Input: piles = [30,11,23,4,20], t = 5  
Output: 30

Example 2:  
Input: piles = [30,11,23,4,20], t = 6  
Output: 23

----------

 #### [Microsoft India | Technical Interview | August 2022](https://leetcode.com/discuss/interview-question/2532865/Microsoft-India-or-Technical-Interview-or-August-2022)
You are given a binary matrix (with 1's and 0's) of size n x n. you have to divide the matrix into 4 sections by dividing it by one row and one column. each section must have atleast one cell. score of a segment is the number of 1's in that section. You have 3 sisters and they are given with the sections that has the highest 3 scores, and you are left with the section having least score always.  
you have to divide the matrix in such a way that you will get the maximum score after providing to the sisters.

My Approach:  
we define dp[i][j] as sum from matrix[0][0] to matrix[i][j] rectangle. as preprocess and check for every value of i,j so o(n^2) complexity

二分＋check 类似二维版本 力扣1231 

-------

[Google OA | Array of Zeroes (HackerEarth OA)](https://leetcode.com/discuss/interview-question/2674448/Google-OA-or-Array-of-Zeroes-%28HackerEarth-OA%29)

![image](https://assets.leetcode.com/users/images/26424dcb-1564-4b53-8d13-a124a7251ba5_1665195746.7978594.jpeg)

-------

[OA Hard!!](https://leetcode.com/discuss/interview-question/2694139/OA-Hard!!)

![image](https://assets.leetcode.com/users/images/07f4c276-4559-4e11-bc7e-ee53e0f22103_1665572136.663208.png)
![image](https://assets.leetcode.com/users/images/4b357dce-4162-4cdc-8bb8-8978bb69da81_1665572160.1160605.png)
这里有一个贪心思路 就是如果要充电 每一次充电后走的路应该尽可能一样
对时间进行二分 因为要走的路程是定的 给定一个时间可以计算出充电的次数 然后计算出每一次充电后走多少路 然后知道了电池容量 看能不能走完 如果能走完 那么就把时间调小点

-------

[Google OA 2023 intern](https://leetcode.com/discuss/interview-question/2707531/Google-OA-2023-intern)

![image](https://assets.leetcode.com/users/images/19b37e62-d7f5-403f-972e-1102e94c76c9_1665868317.19674.jpeg)
any approaches? x and y can go till 10^9 and n till 10^5

二分是正确做法 刚开始想成线段树了 线段树是基于贪心思路 每次都是把当前的最大值最为major 线段树就是复杂点 逻辑应该也是正确的

------

[Cohesity OA | Minimize the edge weight](https://leetcode.com/discuss/interview-question/2738489/Cohesity-OA-or-Minimize-the-edge-weight)

You are given a weighted tree of  **A**  nodes. All the nodes have a node value assigned to it given by the array  **C**.  
_The ORSum is the OR of all the nodes of a connected component of a graph_.  
Now, you can remove any edges of the tree. The ORSum of each component must be  **at least B**.  
What is the  **minimum possible value of maximum edge weight that is not removed**.  
**Return 0**  if you can remove all the edges.

Given a 2D integer array D of size (A-1)*3 that represents the edges of the tree. The ith edge connects D[i][0] with D[i][1] and has a weight of D[i][2].

**Constraints**  
1 <= A <= 10^5  
1 <= B <= 10^6  
1 <= C[i] <= 10^6  
1 <= D[i][0], D[i][1] <= A  
D[i][0] != D[i][1]  
1 <= D[i][2] <= 10^6

_For Example_:  
**Input**:  
A = 4  
B = 3  
C = [3,1,2,5]  **(1-based indexing)**  
D = [[1, 2, 2],[1,3,4],[3,4,3]]

**Output**:  
3

**Explanation**:  
Remove the edge between the nodes 1 and 3.  
So, now there will be two seperate components: [1,2,2] and [3,4,3]

ORSum of component 1([1,2,2]) is: C[1] OR C[2] = 3 or 1 = 3 >=B  
ORSum of componet 2([3,4,3]) is: C[3] OR C[4] = 2 or 5 = 7 >=B

So, maximum of all edge weight = 3  
Hence, answer is 3

Here the goal is to minimise the maximum edge weight after removing all valid edges(valid edges: After removing the edge, the components ORSum must be atleast B).

Any approach to solve this in a linear time complexity? (Assumed linear time because of constraints)

------

[Lucid OA](https://leetcode.com/discuss/interview-question/2744375/Lucid-OA)

![image](https://assets.leetcode.com/users/images/3d36df5d-68bd-4cd8-b9c3-908868f7c03b_1666748648.759837.jpeg)
![image](https://assets.leetcode.com/users/images/e18643d4-33c9-439f-957e-d0e2c5a871e3_1666748649.6874275.jpeg)
![image](https://assets.leetcode.com/users/images/7901a325-6aee-465e-a2bc-fb92c491306a_1666748650.113328.jpeg)
![image](https://assets.leetcode.com/users/images/55af390e-f20b-413f-b863-0f8e64b108de_1666748650.9858263.jpeg)
![image](https://assets.leetcode.com/users/images/47b8674b-687b-404b-9a3b-04bae16e0ff7_1666748653.134939.jpeg)![image](https://assets.leetcode.com/users/images/47b8674b-687b-404b-9a3b-04bae16e0ff7_1666748653.134939.jpeg)

-------

[Microsoft | Onsite | Job Scheudling Quesiton](https://leetcode.com/discuss/interview-question/1850541/Microsoft-or-Onsite-or-Job-Scheudling-Quesiton)

You have a set of jobs J = [J_1..J_n]. Each job takes an arbitrary number of minutes, [m_1..m_n] to execute.

Let's say that the jobs can executre in parallel on nodes [N_1..N_k]. Assume we have a maximum wallclock time budget T, that is the maximum allowable elapsed time since the first job started executing. Write a function to give the minium number of nodes needed to executre these n jobs within time budget T.

不用二分+check 贪心思想即可 对[m_1..m_n] 从大到小排序 然后从大的开始放 dfsji ke
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTY1MDk2MzM5NCwxOTcyNTQ4NjM5LC0xMj
UzNDk2Njc2LDY1NjkwOTExNSwtOTAwODgzNzY3LDE1NDUyMDc0
MzFdfQ==
-->