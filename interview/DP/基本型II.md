[Trilogy Innovations OA Questions Help 😐 (For 2024 Batch , SDE-Intern Role)](https://leetcode.com/discuss/interview-question/2780180/Trilogy-Innovations-OA-Questions-Help-%28For-2024-Batch-SDE-Intern-Role%29)

![image](https://assets.leetcode.com/users/images/4ec0cca1-040a-4fe1-9f1b-dd37f45e8af3_1667629023.391552.jpeg)
![image](https://assets.leetcode.com/users/images/19acaa49-a180-45e4-b15c-6d0622ae0547_1667629026.4647093.jpeg)
![image](https://assets.leetcode.com/users/images/5d22d398-7218-4976-91ae-97ca808384c3_1667629029.6945503.jpeg)

定义dp[i][j]表示对于数组前i个元素并且最后一个消灭的元素index为j的最小值
每次更新 对于dp[i][j] 如果j小于i 那么dp[i][j]=dp[i-1][j] + 当前元素的值✖️(i-j) 
如果j等于i 那么dp[i][j]=min(dp[k] + sum(k到i) for k in range(0, i)) + B

----

[Media.net | OA](https://leetcode.com/discuss/interview-question/2415905/Media.net-or-OA)

## 2. Lexicographically Greater String

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

---
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTY5MjA5MDU0NSwtMTY5Nzk2MzI5OF19
-->