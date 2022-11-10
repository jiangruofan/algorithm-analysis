[Google OA](https://leetcode.com/discuss/interview-question/2257966/Google-OA)

**Partition String**  
You are given a string S of lenght N of digits 0 - 9. You need to partiton strings into K substrings such that

-   Each substring has a minimum lenght of M
-   Substring must start with even digit and ends with odd digit number

Determine the number of ways to partitioin the strings which satisfy the above condition  
You should find answer modulo 1e9 + 7

constraints :  
1 <= n<= 2x10^3  
1<= m<= n  
1<=k<=n

Test cases

```
n = 9 
m= 2
k = 3
s = '232387421'
So there are total 3 ways possible 
```
类似力扣1278

---

[uber online assesment coding question](https://leetcode.com/discuss/interview-question/2784595/uber-online-assesment-coding-question)

![image](https://assets.leetcode.com/users/images/1a3701eb-f502-4588-bb8a-7b725242512f_1667728199.5055761.png)

---

[Media.net SDE-1 | Bengaluru | Oncampus](https://leetcode.com/discuss/interview-question/2795802/Media.net-SDE-1-or-Bengaluru-or-Oncampus)

Problem Statement:  
N village are situated on a straight line. The villages are labeled from 1 to N. You are given the population - P[i] and location L[i] of each village. You need to construct K post offices on K different locations such that the average distance taken by person to go to the nearest office is minimized.

这里和力扣那个邮箱不太一样 这里需要预处理 如果把邮箱放在相邻的两个村庄之间 那么给定左边界的村庄和右边界的村庄可以计算出一个ax+b的公式 如果a大于0 那么邮箱放在右边的村庄 如果a小于0 那么邮箱放在左边的村庄 如果a等于0 那么邮箱放在村庄之间都可以 预处理时间复杂度是O(n^3) 然后还需要处理一下 对于给定左村庄和右村庄 计算出放置一个邮箱的最小距离 这个时间复杂度也是O(n^3) 然后就是套路dp

----

[Media.net SDE-1 | Bengaluru | Oncampus](https://leetcode.com/discuss/interview-question/2795802/Media.net-SDE-1-or-Bengaluru-or-Oncampus)

Problem Statement:  
You are given a string S consisting of only open-close paranthesis and an integer N. X and Y are prefix and suffix strings which can only contain open-close paranthesis. Find no of pairs of X and Y such that the combined string X + S + Y is of length N and is balanced.

ex.  
S = '(' N = 4  
Possible pairs of X and Y are  
X = '(' Y = '))'  
X = '()' Y = ')'  
X = '' Y = '())'  
X = '' Y = ')()'  
ans = 4

对于x来说 左括号一定比右括号多 对于y来说 右括号一定比左括号多
那么先dp预处理 对于长度为n的括号字符串 
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTc0MDIyOTc3MywtODMwNTAyNDM5LC0xMD
U1NzQzNTIzLDE1MzEyMTYxNjYsODM3MzY0MDgsNzMwOTk4MTE2
XX0=
-->