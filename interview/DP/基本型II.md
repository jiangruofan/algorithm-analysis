[Trilogy Innovations OA Questions Help 😐 (For 2024 Batch , SDE-Intern Role)](https://leetcode.com/discuss/interview-question/2780180/Trilogy-Innovations-OA-Questions-Help-%28For-2024-Batch-SDE-Intern-Role%29)

![image](https://assets.leetcode.com/users/images/4ec0cca1-040a-4fe1-9f1b-dd37f45e8af3_1667629023.391552.jpeg)
![image](https://assets.leetcode.com/users/images/19acaa49-a180-45e4-b15c-6d0622ae0547_1667629026.4647093.jpeg)
![image](https://assets.leetcode.com/users/images/5d22d398-7218-4976-91ae-97ca808384c3_1667629029.6945503.jpeg)

定义dp[i][j]表示对于数组前i个元素并且最后一个消灭的元素index为j的最小值
每次更新 对于dp[i][j] 如果j小于i 那么dp[i][j]=dp[i-1][j] + 当前元素的值✖️(i-j) 
如果j等于i 那么dp[i][j]=min(dp[k] + sum(k到i) for k in range(0, i)) + B

----

[Media.net | OA](https://leetcode.com/discuss/interview-question/2415905/Media.net-or-OA)

![image](https://assets.leetcode.com/users/images/c3ae564d-94a1-45b8-a5f9-e5886719b479_1659122058.8588572.png)

Lexicographically Greater String

Given a string  **C**  consisting of lowercase alphabets of size  **A**. For each string  **D**  of length  **n**, its beauty relative to  **C**  is defined as the number of pairs of indexes i,j  `(1<=i<=j<=n)`  that substring  `D[i..j]`  is lexicographically larger than substring  `C[i..j]`

Return the count of strings  **D**, such that their beauty relative to  **C**  equals exactly  **B**

Since, the count can be very large you are required to return count modulo  **(10^9+7)**

**Input Format:**

```
The first argument is an Integer A. 
The second argument is an Integer B.
The third argument is String C.

```

**Constraints:**

```
1 <= A <= 2000
1 <= B <= 2000
```

https://codeforces.com/problemset/problem/360/C

这里的特殊情况就是如果当前的字符一样 那么需要往后遍历

---

[DE Shaw off campus OA for 2023 batch](https://leetcode.com/discuss/interview-question/2924772/DE-Shaw-off-campus-OA-for-2023-batch)

![image](https://assets.leetcode.com/users/images/e3136e52-13d3-4d25-83e9-552d02de7ccf_1671354141.5021994.jpeg)
![image](https://assets.leetcode.com/users/images/60630004-c7ad-4e70-a228-803051aed1fd_1671354146.3915162.jpeg)
![image](https://assets.leetcode.com/users/images/1ade8934-7845-4875-8d09-b53c326a8b29_1671354152.7762477.jpeg)
![image](https://assets.leetcode.com/users/images/f2251c8c-7b04-4319-a69d-bf98009fa062_1671354162.1698763.jpeg)

z-array 预处理

----

[An interesting OA problem](https://leetcode.com/discuss/interview-question/2969173/An-interesting-OA-problem)

given an array of integers and m. partition the given array in such a way that sum of elements in each part should be less than or equal to m and sum of maximum values in each part should be minimised.

1<=n<=1e6  
1<=m<=1e6  
1<=arr[i]<=1e6

i managed to solve this in O(n^2) using dp.

dp[0] = arr[0];  
dp[i] for remaining i= min(dp[j-1] + max[j:i]) for all j<=i and sum[j:i]<=m

How can i optimise it furthur and solve it in O(n)?

Solution:  
[https://www.youtube.com/watch?v=NIHYJIGYMww](https://www.youtube.com/watch?v=NIHYJIGYMww)

------
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEzNjg3ODkzNTUsLTIwMDg4NzU4OTMsLT
Y2MzQ4MDM0OSwtMTY5Nzk2MzI5OF19
-->