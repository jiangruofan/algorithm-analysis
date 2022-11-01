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
dp[i][j]: the minimal time we can get if we choose first i days and skip j lectures 

-------

[Lucid Online Assessment Question : Balanced Words](https://leetcode.com/discuss/interview-question/2657751/Lucid-Online-Assessment-Question-:-Balanced-Words)

![image](https://assets.leetcode.com/users/images/67215adc-0743-4c51-b648-d2971e09f6b1_1664848582.1809986.png)

dp可以优化

-------

[UIPath OA](https://leetcode.com/discuss/interview-question/2666678/UIPath-OA)

![image](https://assets.leetcode.com/users/images/72e0a5a7-4d9b-4b45-98fe-36f631296521_1665023080.2083519.png)

Q.1 constraints arr length <=5000 and threshold <=500.

-------

[GOOD QUESTIONS UB](https://leetcode.com/discuss/interview-question/2708906/GOOD-QUESTIONS-UB)

![image](https://assets.leetcode.com/users/images/e62740af-af82-4519-8768-ba797444f548_1665901065.143898.png)
![image](https://assets.leetcode.com/users/images/a68633b2-f438-44c6-a188-b670d4c87d4c_1665901068.260328.png)
类似背包问题 dp[i][j][k]表示前i层使用j个o和k个🌟所能构成的方案数 对于第前i层 如果使用j个o 那么可以计算出🌟的数量 如果使用k个🌟 那么可以计算出o的数量 所以遍历i 每次的时间复杂度是10^5
i最大为多少可以计算出来 n(n+1)/2 = 2 * 10 ^ 5 
总体时间复杂度应该是小于10^8

-------

[Cisco | Summer Intern | Software Engineer 1](https://leetcode.com/discuss/interview-question/2712200/Cisco-or-Summer-Intern-or-Software-Engineer-1)

Given an array of integers, what is the most amount of cookies you can collect.  
If you collect from jar[y] you can not select from jar[y-1] or jar[y+1]

----

[Expedia OA Summer 2023 Software Engineering Intern - Hard?](https://leetcode.com/discuss/interview-question/2744346/Expedia-OA-Summer-2023-Software-Engineering-Intern-Hard)

HackerBit designed a game based on binary digits. You are required to find the answer to the following problem to win the game.  
A binary string is a string consisting only of digits 0 and 1. A binary string is said to be good if:

-   The digit 1 only appears in groups of size one_group, if it appears at all. For example, for one_group =2 , "011110110" satisfies this condition while "01101010" does not.
    
-   The digit 0 only appears in groups of size zero group, if it appears at all. For example, for zero group =3 , "11" satisfies this condition while "101010" does not. For example, for one group=2, zero_group =1 , the strings "011", "000" are good while the strings "001" and "111" are not.
    

You are given four integers min_length, max_length, one_group, and zero group. Find the number of good binary strings such that their lengths are in the range [min_length, max_length]. As the answer can be large, compute it modulo (10 ^9 +7)

Example Consider min_length=1, max_length=3, one group=2 and zero group=1  
"0"  
"11"  
"00"  
"110"  
"011"  
"000"  
Ans- Total count = 6

-----

[Microsoft Interview Problem](https://leetcode.com/discuss/interview-question/1857043/Microsoft-Interview-Problem)

**Given an array A of size N. Find the maximum subset-sum of elements that you can make from the given array such that for every two consecutive elements in the array, at least one of the elements is present in our subset.**  
Input: N = 4, A[] = {1,-1,3,4}  
Output: 8  
Explanation: We can choose 1st, 3rd and 4th index, you can check that this is maximum possible sum.

-   Can aynone please :) solve this problem using recursion + memoization?

Let's say dp[i][0] denotes the maximum subset-sum in the array ending in the ith index, and the ith element is not chosen while dp[i][1] denotes the answer when the ith element is chosen.  
So dp[i][0] = dp[i - 1][1], dp[i][1] = max(dp[i - 1][0], dp[i - 1][1]) + A[i].  
The final answer is max(dp[N][0], dp[N][1])

------

[Microsoft - Job Max Profit](https://leetcode.com/discuss/interview-question/1784110/Microsoft-Job-Max-Profit)

I was asked this question during virtual onsite for SDE 1/2 hiring event - not sure what to make of it. Is there an existing question for this on LC?

Input:  
List of job ID's ("a", "b", "c", "d" etc)  
List of job duration (1, 2, 4, 6, etc)  
List of profit you get for scheduling that job (2, 4, 6, 10, etc)  
Duration of time you have to schedule the jobs, (e.g. 8)

What is the maximum amount of profit you can make from scheduling jobs?  
Each job can only be scheduled at most once.  
My intuition was to sort the jobs by how much profit-per-hour they make and then do some kind of backtracking or DP, but I couldn't wrap my head around it. I think that backtracking would work if you have some way to know at what point you will not find a more profitable job combination by continuing the backtracking, but not sure if that is the right line of thinking.  
Anybody have any ideas?  
Thanks

Edit:  
Turns out this is called a '0-1 knapsack problem'.  
Thanks to all who commented.

背包问题

----

[need help(OA 2022) Gamescraft](https://leetcode.com/discuss/interview-question/2754597/need-help%28OA-2022%29-Gamescraft)

A student is asked to assign numbers to his classmates represented in an array arr. The arrangement of numbers is good if the absolute difference between any two consecutive students is less than or equal to 1. For example, the array [1, 2, 1] is good, while [2, 1, 3] is not because abs(1-3)= 2, which is greater than 1.

An array arr of n integers has some missing elements denoted by arr[i]=0. Find the number of ways to replace some or all of the missing elements with arbitrary integers such that the resulting array is good. Since the answer can be large, compute it modulo (10^9+7)  
.Example

Consider n = 3, arr = [0, 0, 1].

There are 9 ways to replace Os to make the array good.

arr = [0, 0, 1]  
arr = [1,0,1]  
arr=[-1,0,1]  
ar-[0, 1, 1]  
arr=[1, 1, 1]  
arr[2, 1, 1]  
arr-[1,21]  
arr=[2, 2, 1]  
arr=[3, 2, 1]

In each of these arrays, the absolute difference between each pair of consecutive elements is less than or equal to 1.  
contraints- 1<n<1500

这里的dp用字典

----

[NAVI OA](https://leetcode.com/discuss/interview-question/2758884/NAVI-OA)

![image](https://assets.leetcode.com/users/images/4e402497-e9bd-43e8-acdf-4198b42aeb7c_1667112870.6965601.png)

先从小到大排个序 那么对于每一个元素 贪心思想 最优解一定这个元素和它前面或者后面组成一个pair

----
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTQ5NzYwODkwMywtOTA0MTk2NDQ3LDE2OT
AwNDI5MzgsNzI4NDg3NTc4LDgxNTQxOTI3OCw3OTEyMzY3NzAs
MTAyMjIwODM1NCwtOTEwMzUyODg4LDYzNjE2MzQwNywtMTQ2Mj
MzNDk0NCwtOTQ4ODQ1Mjg3LDIwODY1MzAxMjcsMzQxNzM5NDcx
XX0=
-->