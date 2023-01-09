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

[OA || Help needed! || Number of valid passwords with less than k consecutive repetitions allowed](https://leetcode.com/discuss/interview-question/2782808/OA-oror-Help-needed!-oror-Number-of-valid-passwords-with-less-than-k-consecutive-repetitions-allowed)

Saw the following problem in a New Grad OA a few days ago and could not come up with a solution. Does anybody know how to do this?

### Problem: Count number of valid passwords

A password is valid if:

-   It contains only lowercase English letters
-   No  _k_  consecutive characters are the same.

Given 2 integers  _n_  and  _k_, find the number of valid passwords possible. Report your answer as modulo(10 ^ 9 + 7)

Example: For n = 3, k = 3: There are 26 ^ 3 total possible passwords out of which 26 have 3 consecutive letters. So, valid passwords = 26 ^ 3 - 26 = 17550.

For n = 3, k = 2, we have 26 passwords with all characters the same and 26 * 25 + 26 * 25 passwords with 2 consecutive characters (corresponding to "aab" and "baa" types). So, valid passwords = 26 ^ 3 - 26 - 26 * 25 * 2 = 16250.

时间复杂度是O(26n)

---

[OA Question || need help](https://leetcode.com/discuss/interview-question/2784441/OA-Question-oror-need-help)

Alice has N coins of amount from 0 to (N-1). Bob wants to take k coins out of them, but Alice will only give if the set of K coins is interesting.

A set of coins is interesting if the sum of them is divisible by a unique integer M. Now Bob wants to know in how many ways he can get K coins.

Print the result by answer%(10^9+7)

Input format:- Three space separated integers N,K,M.

Any ideas how to approach this

Constraints:  
1 <= N, M <= 10^3  
1 <= K <= 10^2

dp[i][j][k] 从前i个硬币中选取j个并且和的模是k 有多少种选择

---

[Media.net | OA | July 2022](https://leetcode.com/discuss/interview-question/2352217/Media.net-or-OA-or-July-2022)

![image](https://assets.leetcode.com/users/images/c3ae564d-94a1-45b8-a5f9-e5886719b479_1659122058.8588572.png)

dp[i][j] 表示从i到leng-1区间进行匹配并且beauty的数量为j有多少种情况
倒叙dp 注意这里字符串D的长度可以为1到leng 总体时间复杂度应该是10^9

----

[Doordash OA 2023](https://leetcode.com/discuss/interview-question/2797857/Doordash-OA-2023)

**Problem 1 Application Deployment**  
Hackerrank developers want to deploy an application on a set of exactly k servers with different vulnerabilities. They have an option to choose the k servers from a sequence of n servers where vulnerability[i] represents the vulnerability of the ih server.

The vulnerability of the chosen & servers is defined as the maximum vulnerability amongst any of the chosen servers. To avoid congestion, they would like to choose : subsequence of & servers such that no two adjacent servers are chosen as part of the Xservers.

Given an array vulnerability and an integer k, find the minimum possible vulnerability of the chosen servers such that the above condition is respected.

_Example_  
Given n = 4, k = 2 and vulnerability = [2, 3, 5, 9], only 3 subsequences of k = 2 non-adjacent servers exists.  
• [2, 5] - max = 5  
• [3, 9] - max = 9  
• [2, 9] - max = 9  
Report 5 as the answer.

_Function Description_  
Complete the function getMinVulnerability in the editor below.  
getMin Vulnerability has the following parameters:  
in vulnerability[n]: An array of integers  
int k: the length of the subsequences to form

**Problem 2 Task Completion**  
Two interns at HackerRank are teamed up to complete a total of n tasks. Each task is to be completed by either of the two interns. Both interns have their reward points defined, where the first intern gains reward_1[i] points for completing the th task, while the second intern gains reward_ 2[i] points for completing the jth task. Since the interns work as a team, they wish to maximize the total reward points gained by both of them combined. Find the maximum combined reward points that can be gained if the first intern has to complete k tasks, and the second intern completes the remaining tasks.

Note: The k tasks completed by the first intern could  
be any amongst the n tasks.

_Example_  
Consider n = 5, reward_1 = [5, 4, 3, 2, 1], reward 2  
[1, 2, 3, 4, 5] and k = 3.  
Intern 1 has to complete 3 tasks, while intern 2 has to complete the remaining 2 tasks. In order to maximize the points gained, intern 1 completes the first 3 tasks, while intern 2 completes the last 2 tasks. Total reward points gained = 5 + 4 + 3 (from intern 1) + 4 + 5 (from intern 2) = 21, which is the maximum possible. Thus, the answer is 21.

时间复杂度都是O(nk)

---

[Microsoft coding round/difficult/](https://leetcode.com/discuss/interview-question/2799099/Microsoft-coding-rounddifficult)

![image](https://assets.leetcode.com/users/images/44b7eab0-7bfe-482b-8fc2-b406a4d2875f_1668063249.8687634.jpeg)
![image](https://assets.leetcode.com/users/images/5bdb08fd-d29c-4086-a074-50f2ee4a3347_1668063257.921846.jpeg)

类似wisdom油管上的那一道题目

---

[Snowflake OA](https://leetcode.com/discuss/interview-question/2801540/Snowflake-OA)

![image](https://assets.leetcode.com/users/images/1f08afec-0012-4fbc-8a48-32a5d9a06b9b_1668119821.2091281.png)

----

[Media.Net | Onsite | No. of ways an array can be split into two equal sum sequences](https://leetcode.com/discuss/interview-question/1006129/Media.Net-or-Onsite-or-No.-of-ways-an-array-can-be-split-into-two-equal-sum-sequences)

You are given an integer array of size N and you have to split it into two subsequences, both must have at least one element and equal sum. There can be some elements in the array which are left undistributed. Now, count the number of ways in which the integers can be split.

Example:  
Input -> [1,2,3,4,5,11]  
Output -> 8  
Explanation ->  
The splits are as follows:

-   [1,2], [3] (same as [3], [1,2])
-   [1,3], [4]
-   [1,4], [5]
-   [2,3], [5]
-   [3,4], [5,2]
-   [2,4,5], [11]
-   [3,4,5], [1,11]
-   [1,2,3,5], [11]

Note:

1.  I think the interviewer has missed some cases and the output should be more than 8 (E.g. the split [2,4], [1,5] should also be valid). (At that time the question was clear to me so I didn't verify the output that he provided)

Constraints:  
a. [N <= 100]  
b. [-1000 <= total sum <= 1000]

dp的状态值表示的是两个子序列的差值 如果对于正数没问题
如果对于负数 还需要另一个dp计算出所有的元素和为0的子序列有多少个 然后乘2 
最后把这一部分重复计算的刨掉

---

[Oracle OA 2022](https://leetcode.com/discuss/interview-question/2835274/Oracle-OA-2022)

Given a string S that consists of lowercase English letters, create a mapping M which assigns every lowercase letter (26 of them) to a distinct positive integer less than or equal to 100. Map the string to a series of integers where each letter is replaced by the integer it is mapped to. Formally, S = s1s2s3.....sn is now converted to the sequence M(s1), M(s2), M(s3),..., M(sn). Find a mapping M such that the bitwise XOR of all the numbers in the sequence is minimized.

For example, string s = abc and the mapping is M('a') = 65, M('b') = 66, M('c')=3. The strings is now converted to 65, 66, 3. XOR these numbers together to get 0(zero) which is the minimum. Other characters can be mapped to any other distinct numbers less than or equal to 100, so they are not shown here for convenience.

Function Description Complete the function mapLetters Two Numbers in the editor below. The function must return a vector that contains 26 distinct positive integers less than or equal to 100. Letters Numbers has the following parameter(s): s: the given input string

Constraints 1 < |S| <10^5 and S consists only lowercase English letters, ascii[a-z]

这里异或后的结果是有限的 最多255 
定义dp[i][j][k] 表示从100个的前i个元素取j个元素进行异或结果为k是否存在

---

[Correct execution sequence | StanC OA question](https://leetcode.com/discuss/interview-question/2809936/Correct-execution-sequence-or-StanC-OA-question)

A supercomputer has multiple processors(n) at its disposal ,each arranged in a sequence.  
The processors can be used to do the job in any order.  
The efficiency of a processor is subject to its adjacent processors.

for the ith processor , the efficiency is no_adjacent[i],one_adjacent[i],both_adjacent[i] when  
neither , one or both adjacent processors have been used respectively.

**example:**  
lets say n=4 then,  
The efficiency of a processor, Pi, is subject to following rule :

no_adjacent: [ 1,2,3,4 ]  
one_adjacent : [ 4,4,2,1]  
both_adjacent : [0,1,1,0]

so lets say they are used in the order 0->1->2->3 where these numbers refer to index in the array.  
then efficiency sum would be no_adjacent[0] + one_adjacent[1]+ one_adjacent[2] + one_adjacent[3]= 1+4+2+1=8

if the order is 3->2->1->0 the answer would be 4+2+4+4=14  
This 14 can be referred to as efficiency sum

so among all such arrangements we need to find the  **maximumpossibleefficiency sum**

**constraints:**

2<=n<=10^5  
1<= values in each of the 3arrays <= 10^9

dp[i][j]表示对于第i个元素它是在右边元素之前还是之后出现 j为1或者0表示之前还是之后

---

[Tiktok | Grad | Online Assessment](https://leetcode.com/discuss/interview-question/2864563/Tiktok-or-Grad-or-Online-Assessment)

**Can someone help me with this question?**  
The company OnlineShopping has a budget of N SGD this financial year. The Chief Marketing Officer (CMO) wants to advertise on TikTok to guide more traffic to the platform. The TikTok ad team shared different kinds of advertisement. Each advertisement can only run at most once. Below are some sample advertisement  
types ad team shared:  
• Type A: S$1000 can reach 3000 TikTok users  
• Type B: S$500 can reach 2000 TikTok users  
• Type C: S$200 can reach 1000 TikTok users  
• Type D: S$100 can each 800 TikTok users.  
• Type E: S$50 can reach 200 TikTok users  
For each type of advertisement, the performance differ. The advertisement types will be given by ad team  
**Write an alogrithm to help CMO evaluate the highest member of users it can reach by using the budget and the advertisement types array: M**  
**Input**  
Budget: N  
Advertisement types(2d array)  
**M: [[1000,3000], [500,2000], [200,1000],[100,800],[50,200]]**  
**Output:**  
Max number of users can reach Limit  
Time complexity should be at least **O(len(M) * N)**

0-1背包问题

----

[Starbucks | OA | Element Swapping](https://leetcode.com/discuss/interview-question/2902387/Starbucks-or-OA-or-Element-Swapping)

**Question:**

A software development firm is hiring engineers and used the following challenge in its online test.

Given an array arrthat contains n integers, the following operation can be performed on it any number of times (possibly zero):

• Choose any index i(O i < n - 1) and swap arr[i] and arr[i+1].  
• Each element of the array can be swapped at most once during the whole process.

The strength of an index i is defined as (arr[i] * (i + 1)), using 0-based indexing. Find the maximum possible sum of the strength of all indices after optimal swaps. Mathematically, maximize the following.

![image](https://assets.leetcode.com/users/images/4737dc64-49ec-4e86-b978-33c659ed64a1_1670792175.99601.png)

Example:  
Consider n = 4, arr=[2, 1, 4, 3].  
It is optimal to swap (arr[2], arr[3]) and (arr[0], arr[1]). The final array is [1 , 2, 3, 4]. The sum of strengths =(1 * 1 +2 * 2+3 * 3+4 * 4) = 30, which is maximum possible. Thus, the answer is 30.

**Function Description**:  
Complete the function getMaximumSumOfStrengths().

getMaximumSumOfStrengths() has the following parameter:  
_int arr[n]_:the initial array

**Returns**:  
_longint_: the maximum possible sum of strengths of all indices after the operations are applied optimally

**Sample Case:**  
getMaximumSumOfStrengths([1,9,7,3,2]) returns 66

----

[Media.Net | Onsite | Coding Round](https://leetcode.com/discuss/interview-question/2349539/Media.Net-or-Onsite-or-Coding-Round)

Can someone pls. help me with this problem?  
I have my coding round of  [Media.net](http://media.net/)  and this question was asked previously.

N strings of varying lengths are given. Each character used in the strings has some value. The value of a string is the sum of all characters used in that string. Given a length L, we have to use a subset of the given strings so that the total length of the strings used is L and the sum of values of all strings is maximised.  
Hint: Knapsack

简单背包

----

[ZOMATO INTERVIEW QUESTION](https://leetcode.com/discuss/interview-question/2906746/ZOMATO-INTERVIEW-QUESTION)

Tom is decorating the pavement in his garden with N square tiles. Each tile is divided into four triangles of different colors (white - 'W', red - 'R', green - 'G' and blue - 'B'). A tile is described as a string of four characters denoting respectively, the color of the upper, right, bottom and left triangle. For example, the tile in the figure below is described as "WRGB".

The image illustrates an examples of tile

Tom arranged the tiles in a row and decided to rotate some of them to obtain a pretty sequence. He considers a sequence of tiles pretty if each pair of adjacent tiles shares one side of the same color.

Write a function:

class Solution { public int solution(String[] A); }

that, given an array A of N strings, representing the sequence of tiles, returns the minimum number of 90-degree rotations (clockwise or counter-clockwise) that Tom has to perform.

Examples:

1.  Given A = ["RGBW", "GBRW"], the function should return 1.

The image illustrates the first example test.

Tom can rotate the second tile counter-clockwise once to obtain a pretty sequence.

The image illustrates the answer to the first example test.

2.  Given A = ["WBGR", "WBGR", "WRGB", "WRGB", "RBGW"], the function should return 4.

The image illustrates the second example test.

Tom can obtain a pretty sequence by rotating the first and third tiles counter-clockwise and the second and fourth tiles clockwise.

The image illustrates the answer to the second example test.

3.  Given A = ["RBGW", "GBRW", "RWGB", "GBRW"], the function should return 2.

The image illustrates the third example test.

Tom can rotate the first tile clockwise twice to obtain a pretty sequence.

The image illustrates the answer to the third example test.

4.  Given A = ["GBRW", "RBGW", "BWGR", "BRGW"], the function should return 2.

The image illustrates the fourth example test.

Tom can rotate the first two tiles clockwise to obtain a pretty sequence.

The image illustrates the answer to the fourth example test.

Write an efficient algorithm for the following assumptions:

N is an integer within the range [1..100,000];  
string representing a tile has 4 letters (exactly one occurrence of 'R', 'G', 'B' and 'W').

-----

[Chubb OA | Coloring Houses | DP](https://leetcode.com/discuss/interview-question/3015337/Chubb-OA-or-Coloring-Houses-or-DP)

I tried using recursive dp but there were too many cases.  
1 <= n <= 1e5.
![image](https://assets.leetcode.com/users/images/0f1794a2-9cc6-4be4-a15f-526258eee1f3_1673116672.9985902.png)

这题很有意思 
正确的dp顺序应该是 1 3 5 6 4 2
对于3 5 要求和前前一个元素不一样
对于6 4 要求和前一个元素并且和前前一个元素不一样
<!--stackedit_data:
eyJoaXN0b3J5IjpbNjU3Mjg0OTI1LDE4OTk2MjI2NCwxMTQ0MT
A5Mzg5LC0zMjcyODAxODgsLTE0NzgwOTY0OTcsODQwNDI3MzUw
LC02NzIzNzYwMjcsLTYzMDAzNTg2MywxMTg2MjI2ODIyLC0xOT
Y3NzA5MDY2LC00MjMxNDM5NzMsLTYwOTI4OTQxOCwtOTU1Mzk0
OTA4LC0xNjY0NTEwNjYxLC0yMjQwMzcyMzAsLTEzNjExNTgyMj
AsLTIwOTgyODUwODEsOTgxMzkxNjgxLC00OTc2MDg5MDMsLTkw
NDE5NjQ0N119
-->