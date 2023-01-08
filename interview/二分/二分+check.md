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

![image](https://assets.leetcode.com/users/images/ac44d5ae-4387-48dc-8666-5bcb32c6a0ab_1667608709.8977346.jpeg)
![image](https://assets.leetcode.com/users/images/7a1e7071-8565-4096-9cd0-a80aa53f8c5d_1667608714.7215807.jpeg)
![image](https://assets.leetcode.com/users/images/7901a325-6aee-465e-a2bc-fb92c491306a_1666748650.113328.jpeg)
![image](https://assets.leetcode.com/users/images/55af390e-f20b-413f-b863-0f8e64b108de_1666748650.9858263.jpeg)
![image](https://assets.leetcode.com/users/images/47b8674b-687b-404b-9a3b-04bae16e0ff7_1666748653.134939.jpeg)![image](https://assets.leetcode.com/users/images/47b8674b-687b-404b-9a3b-04bae16e0ff7_1666748653.134939.jpeg)

-------

[Microsoft | Onsite | Job Scheudling Quesiton](https://leetcode.com/discuss/interview-question/1850541/Microsoft-or-Onsite-or-Job-Scheudling-Quesiton)

You have a set of jobs J = [J_1..J_n]. Each job takes an arbitrary number of minutes, [m_1..m_n] to execute.

Let's say that the jobs can executre in parallel on nodes [N_1..N_k]. Assume we have a maximum wallclock time budget T, that is the maximum allowable elapsed time since the first job started executing. Write a function to give the minium number of nodes needed to executre these n jobs within time budget T.

不用二分+check 贪心思想即可 对[m_1..m_n] 从大到小排序 然后从大的开始放 dfs即可

----

[Sahaj software| OA off campus](https://leetcode.com/discuss/interview-question/2773806/Sahaj-softwareor-OA-off-campus)

![image](https://assets.leetcode.com/users/images/4d5a1e60-d73b-41dd-a8c4-1d6a0e306770_1667481568.5675087.jpeg)

----

[Media.net online coding quiestion online assessment](https://leetcode.com/discuss/interview-question/2748873/Media.net-online-coding-quiestion-online-assessment)

![image](https://assets.leetcode.com/users/images/82c7d5c0-2c9f-43ac-af03-5d227a6c0230_1666869343.270285.png)
![image](https://assets.leetcode.com/users/images/91fa0c92-edb9-4ceb-8239-ca5fa4235165_1666869384.0202844.png)
![image](https://assets.leetcode.com/users/images/8010b787-24a7-48fe-a6ea-8379bed3f68e_1666869411.337894.png)

----

[Can anyone give me the hint...](https://leetcode.com/discuss/interview-question/2799572/Can-anyone-give-me-the-hint...)

![image](https://assets.leetcode.com/users/images/36bfee5a-4a1e-4bb3-98ef-6a891cb54995_1668074350.9846668.png)

这里有贪心的思想 假设最小值是x 那么对于一个集合 肯定是符合条件的所有元素都放进去 这样剩下来的元素就最少 构成最小值也是x的概率就越大 因为少一个元素肯定比多一个元素好

----

[Walmart | OA | Subarray Sum Problem](https://leetcode.com/discuss/interview-question/2811647/Walmart-or-OA-or-Subarray-Sum-Problem)

An array of length N is given.  
1 <= N <= 21e5

In one operation you can add two adjacent numbers together  
Eg:  
1, 4, 2, 5 --> 1, 6, 5  
Elements at index 1 and 2 are combined.  
You can perform any number of operations.

The array needs to be made non-decreasing. Find the maximum length of the array such that it is non-decreasing.

Sample Input #1  
6  
5 1 6 7 8 2  
Sample Output #1  
4

( Array can be 5, 7, 7, 10 or 6, 6, 7, 10 whose length is 4 )

这题很有意思 两次二分+check

----

[Snowflake | OA | Server Selection](https://leetcode.com/discuss/interview-question/2594968/Snowflake-or-OA-or-Server-Selection)

![image](https://assets.leetcode.com/users/images/c5e3281f-990e-4b8f-aa1e-80a8103ed471_1663550925.3129776.png)
![image](https://assets.leetcode.com/users/images/c0933388-8297-4ce2-a1c9-d3510fd07c7d_1663550964.960472.png)
![image](https://assets.leetcode.com/users/images/a132338a-e4d0-4f1a-87ad-e9ad2f0b7589_1663550985.784426.png)


-----

[Red Hat Software Internship 2023 OA || Off-Campus](https://leetcode.com/discuss/interview-question/2833538/Red-Hat-Software-Internship-2023-OA-oror-Off-Campus)

![image](https://assets.leetcode.com/users/images/549fec1f-1dd5-41e2-a260-86e594dec00d_1668954724.0770314.jpeg)

简单二分+check

`Solution :`  [https://discuss.codechef.com/t/hackerrank-recycling-cartridges/85101/2](https://discuss.codechef.com/t/hackerrank-recycling-cartridges/85101/2)

----

[PayPal SDE1 OA](https://leetcode.com/discuss/interview-question/2800113/PayPal-SDE1-OA)

![image](https://assets.leetcode.com/users/images/b98e6b15-3215-434d-b90c-a9f69d2c5d9d_1668087437.365687.png)

简单二分

---

[DESHAW | OA | Off-campus](https://leetcode.com/discuss/interview-question/2813577/DESHAW-or-OA-or-Off-campus)

![image](https://assets.leetcode.com/users/images/ae50c4ef-2030-4c36-b3b7-cf32a9b5e377_1668422692.3826609.jpeg)
![image](https://assets.leetcode.com/users/images/46543e6b-a325-4937-bf59-8cf66ae21799_1668422711.005035.jpeg)

------

[DE Shaw OA Question? Any Approach?](https://leetcode.com/discuss/interview-question/2879828/DE-Shaw-OA-Question-Any-Approach)

Given an integer array of length n and two integers number_of_opr and subarray_length, in one operation you can choose any subarray of size subarray_length and increase the elements of it by 1, you have perform this operation number_of_opr times, find the maximum value of minimum element by doing this procedure.

ex:  
[1,2,3,4,5,1,2] number-of_opr=2, subarray_size=3  
select first subarray [2,3,4,4,5,1,2], select last subarray [2,3,4,4,6,2,3] hence max val of min element is 2.

Priority Queue failed for this.

用到差分的技巧

-----

[epiFi / Fi Online Assessment Questions [SDE II] - HackerRank](https://leetcode.com/discuss/interview-question/2945953/epiFi-Fi-Online-Assessment-Questions-SDE-II-HackerRank)

![image](https://assets.leetcode.com/users/images/e8c956b2-296d-4514-90f7-b58489735b87_1671889680.9089642.png)

二分 + 双指针 
这里不可以indirect transfer 不然的话答案肯定是1

----

[CRED Site Reliability Engineering Intern Questions](https://leetcode.com/discuss/interview-question/3011991/CRED-Site-Reliability-Engineering-Intern-Questions)

Please share nO(logn) approach for the below mentioned question. I was only able to implement n^2O(logn) and half of the test cases were passed.
![image](https://assets.leetcode.com/users/images/4c72c8a4-7cd4-40b5-9c1c-079df8ccd97f_1673071237.8259835.png)
PS:- using priority queue also it will be still n^2O(logn) in worst case.

二分答案 然后对于每一个job 二分检查最少需要























<!--stackedit_data:
eyJoaXN0b3J5IjpbMjIyMTg5Nzk5LC0xNTQ1MTk4MjQ1LDIwOT
czOTYwMjIsLTk3OTE3MjgxNCwxMjY2MDM1OTQ4LC04MjA1NDUz
MjMsODgxNDUzMjA3LDQ3OTYyNTU3OSwtMTYyMTUxNzc0NiwtNT
UzMDU2MjExLC0zMzQ4NDMyNTcsMTk3MjU0ODYzOSwtMTI1MzQ5
NjY3Niw2NTY5MDkxMTUsLTkwMDg4Mzc2NywxNTQ1MjA3NDMxXX
0=
-->