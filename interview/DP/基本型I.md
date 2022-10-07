[Google | OA](https://leetcode.com/discuss/interview-question/2321791/Google-or-OA)
![image](https://assets.leetcode.com/users/images/f946eac8-5678-482f-8d7e-660a7711a28f_1658582421.127063.png)
Constraints :  
N,M<=5000  
MAX(ai,bi) <=5000

This is a standard Knapsack DP problem (I deleted my previous comment as I misread the constraint)  
Time Complexity  `O(5000N) or O(MN)`

Quite similar to  [https://leetcode.com/problems/choose-numbers-from-two-arrays-in-range/discuss/2324309/knapsack-1d-dp-java-osum-n-explained](https://leetcode.com/problems/choose-numbers-from-two-arrays-in-range/discuss/2324309/knapsack-1d-dp-java-osum-n-explained)

Just need to track the path and that's all.

---------

[Google | L3 - L4 | Europe | Reject](https://leetcode.com/discuss/interview-experience/1760495/Google-or-L3-L4-or-Europe-or-Reject)

You are given a non overlapping list of intervals that employees work during the year.  
It's hourly based so there are up to 24*365 working hours in a year.  
You can hire up to K contractors and each one of them can work for Q hours. Contractor work can overlap with each other and with employees.

Return the smallest possible not covered time in a year, using minumum number of contractors.

先求出所有和employee不重合的时间段 问题就转换成了 给定一个间隔和长度为l的k个间隔 问最多能覆盖多少 dp[i][j]表示使用j个长度为l间隔覆盖前i个间隔的最大长度 那么对于第i个间隔考虑覆盖或者不覆盖 如果覆盖的话需要用二分定位到长度为l的间隔可以覆盖到前面第几个间隔

----------

[Google | OA | July 2021](https://leetcode.com/discuss/interview-question/1359174/Google-or-OA-or-July-2021)

![image](https://assets.leetcode.com/users/images/12803e2b-972c-4ad4-a5f2-2dc3060e2022_1627123465.0391634.jpeg)

先做一个并查集 然后dp 类似 552. Student Attendance Record II

------------

[google interview Experience](https://leetcode.com/discuss/interview-question/1161158/google-interview-Experience)

https://leetcode.com/discuss/interview-question/1150720/Google-onsite%3A-Max-path-from-entry-row-to-exit-row

Given a matrix, we can consider any point on the first row as entry point and any point on last row as exit point. # is a wall and . is empty space. Find the path with max length. You can only go down, right or left and visit each cell only once.

I gave a DFS brute force approach but the interviewer wanted a DP solution.

find the length of longest path from first row to the last row ,  
also the time complexity.

这里的dp[i][j] 可以从上左右三个方向过来
对于从左右来的 需要分开计算 不能互相影响 

--------------

[Google Online Assessment](https://leetcode.com/discuss/interview-question/794917/Google-Online-Assessment)

I encountered a question in Google online assessment , it seems to be a variation of LIS.

A smart string is one with characters in strictly increasing or decreasing order. Given a string M, we need to determine the minimum number of contiguous substrings in which M can be broken so that each substring is smart.

Examples: Input: abcdcba  
Output: 2

partitioned into abc and dcba

Input: ffdhbbbdeeggbb  
Output:4

答案: dp[i][j] 表示前i个字符的最少分割次数并且第i个字符是处于上升还是下降的情况 j表示0代表上升 1表示下降
if s[i] > s[i-1]:  
dp[i][0] = dp[i-1][0]
dp[i][1] = min(dp[i-1]) + 1
elif s[i] < s[i-1]:
dp[i][0] = min(dp[i-1]) + 1
dp[i][1] = dp[i-1][1]
else:
dp[i][0] = dp[i][1] = min(dp[i-1]) + 1

------------

[Google | SWE Intern (Winter)| India | Sep 2022 | Rejected](https://leetcode.com/discuss/interview-question/2557189/Google-or-SWE-Intern-%28Winter%29or-India-or-Sep-2022-or-Rejected)

```
Given two lists of integers, A and B, list A represents the daily profit of working at CityA 
and list B represents the daily profit of working at CityB. You are a salesman and you have to
switch between cityA and cityB due to various client requirements. When you switch from cityA 
to cityB, you have to travel. The day you travel (T), cannot be considered as a working day,
and hence your net profit on travel days are 0. 
Your task is to output a schedule which includes working as well as travelling such that your profit is maximized. 

The only example testcase he provided, is given below-
Testcase1: 
Input:
A[] = [23,4,5,2], B[] = [20,1,10,100]

Output:
"ATBB"

Explanation -
An optimal schedule will be-
Day 1 : Work at cityA -> profit is 23
Day 2 : Travel -> profit is 0
Day 3: Work at cityB -> profit is 10
Day 4: Work at cityB -> profit is 100


```

After some questions from my side, he clarified these -

1.  The length of array A and array B will always be equal. Each index of array A/B is treated as day(i), and the value at day(i) is your profit for that day (if you worked). If you travelled at day(i), profit for that day won't be added to your net profit.
2.  You can work in a city for more than 1 day. But, travelling is mandatory. You cannot work in only city A or city B.
3.  There will be no dreaded zeroes in any of the array values.

After much struggle, I figured out it's recursion type problem. I said that, he agreed and asked me to show a memoized dynamic programming solution.

**Required Time Complexity - O(N)  
Required Space Complexity - O(N)**

答案:
The second problem is a very easy DP problem I think. Defind DP state: dp[i][j] while j has 4 states. 0 represents coming to i-th city A and never travelling before, 1 represents coming to i-th city A and traveled. 2 represents coming to i-th city B and never travelling before and 3 represents coming to i-th city B and traveled.  
dp[i][0] = dp[i-1][0] + numA[i]  
dp[i][1] = max(dp[i-1][1], dp[i-2][2], dp[i-2][3]) + numsA[i]  
dp[i][2] = dp[i-1][2] + numB[i]  
dp[i][3] = max(dp[i-1][3], dp[i-2][0], dp[i-2][1]) + numsB[i]  
The result should be max(dp[-1][1], dp[-1][3])

----------------

[Uber Intern OA](https://leetcode.com/discuss/interview-question/788899/Uber-Intern-OA)

https://leetcode.com/discuss/interview-question/2335969/UBER-OA-DP-Problem

[https://www.hackerrank.com/contests/codeagon/challenges/number-of-ways-1/problem](https://www.hackerrank.com/contests/codeagon/challenges/number-of-ways-1/problem)

![image](https://assets.leetcode.com/users/images/88403106-bd59-41a6-b850-29d650b72968_1658830804.235282.jpeg)

首先考虑一个子问题 给定一个字符串s 和另一个字符串t 求t可以有多少种方式由s构成 dp[i][j] = dp[i-1][j] + (dp[i-1][j-1] if s[i] == t[i])

对于原问题 假设三个字符串 x, y, t 
定义dp[i][j][k][flag]  - i表示x[:i]  -  j表示y[:j] - k表示t[:k] -flag表示0和1 0表示匹配的第k个字符在x字符串 1表示匹配的第k个字符串在y字符串
dp[i][j][k][0] = dp[i-1][j][k][0] + (dp[i-1][j][k-1][0] + dp[i-1][j][k-1][1] if x[i] = t[i]) 
dp[i][j][k][1] = dp[i][j-1][k][1] + (dp[i][j-1][k-1][0] + dp[i][j-1][k-1][1] if y[j] = t[j]) 
最后需要对x和y进行子问题处理 刨去这部分不符合题目要求的答案

-------

[Microsoft/Phonepe Interview question](https://leetcode.com/discuss/interview-question/2099443/MicrosoftPhonepe-Interview-question)

Enocunterd this question recently in PS/DS rounds of two companies :

Given a N by M matrix, find the maxium sum possible if we have to choose one element from each row. For example if matrix has N rows then this sum will be formed by N elements from each row. The only constraint is if we have picked an element from the ith row, then we cannot choose element from the same column in (i-1)th and (i+1)th row [if exist].

Example :  
1,2,3  
4,5,6  
7,8,9

Maxium sum is : 3 + 5+ 9  
Note that matrix elements can be random, not sorted as shown in example.

---------

[Lucid OA 2023 summer intern || HackerRank || Lecture of School](https://leetcode.com/discuss/interview-question/2670239/Lucid-OA-2023-summer-intern-oror-HackerRank-oror-Lecture-of-School)

![image](https://assets.leetcode.com/users/images/6d73ec27-4ee9-4396-b8ae-5b838d1b0acd_1665089892.9836583.png)
![image](https://assets.leetcode.com/users/images/05d15e82-1bda-491c-88a6-d90b964a4099_1665092353.0134552.png)

dp先对每一行预处理 求出这天跳过x节课的最小上课时间 然后再进行dp
dp[i][j]: t choose first i days and skip j lectures 
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTI4MjA4OTAsMzQxNzM5NDcxXX0=
-->