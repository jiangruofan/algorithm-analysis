[Google | onsite](https://leetcode.com/discuss/interview-question/1924901/Google-or-onsite)

Give a string, for example : input : a-(b+c+b) output : a-2b-c. need help here

----------

[Google | Onsite | Order of runners | Tree edge remove | Repair parentheses](https://leetcode.com/discuss/interview-question/2638572/Google-or-Onsite-or-Order-of-runners-or-Tree-edge-remove-or-Repair-parentheses)

**#Coding Interview 3**

Question:

Given a string containing only parentheses, scan it to see if the parentheses are well-nested, then:

-   If they are, return the string as-is.
-   If they are not, repair the string so that the parentheses are well nested and return the result

action can be:  
deleting, adding, changing

You must do string well-nested with minimum number of actions

Example:  
Input: (()  
Output: (()), or () or ()()

Input: (())))  
Output: ((()))

答案: 先扫描一遍string 用一个cnt记录多余的左括号 如果遇到了一个多余的左括号 用一个list记录index 并且把这个左括号变成右括号 将右括号的个数➕1 注意这里的右括号个数需要两个变量记录 一个记录原生的右括号 另一个记录左括号变成的右括号 遍历结束后如果左括号变成的右括号数量大于0 那么就需要把一些变成的右括号删除 如果原生的右括号大于0 直接在末尾加入左括号即可 

-------

[Bloomberg | 2023 | New Grad | First round](https://leetcode.com/discuss/interview-question/2723184/Bloomberg-or-2023-or-New-Grad-or-First-round)

```
Interview Duration : 1hr
Type : Online Zoom
Format: Candidate Background (10Mins) | Technical Assesment | Questions (10 Mins)

Asked questions from resume, and favorite project.

Technical Assessment
1. Given the root of a tree, check if its a BST or not
	a. if root is None: Return True
	b. if there are duplicates: Return False
	
2. Implement Stack using two queues (Push, Pop, Top, Empty)
	a. Push must be efficient O(1)
	b. Top must be efficient O(1)
	You have to use the methods provided by queue and no other method on top of it
	class MyQueue:
		def enqueue():
		def dequeue(): return int
		def empty(): return True/False
```

答案 https://stackoverflow.com/questions/688276/implement-stack-using-two-queues

------

[Roblox OA (US)](https://leetcode.com/discuss/interview-question/2476645/Roblox-OA-%28US%29)

#### Q4 - Query In A Binary String

Given a binary string  `s`  that contains only  `"0"`  and  `"1"`. You are also given an array  `query`  with the following operations:

1.  "Count" - The answer to this query is the number of 1s in the binary string.
2.  "Flip" - Flip the substring  `[0, idx]`  so that  `"0" -> "1" and "1" -> "0"`  and  `idx`  is the first  `"0"`  in the binary string. You are guaranteed that flip operation will only be called when there is at least one  `"0"`. The answer to the query is  `idx`.

**Constraints:**

-   `1 <= s.length() <= 100000 (1e5)`
-   `1 <= query.length <= 100000 (1e5)`

答案 使用 (l, r) 表示全部为0的区间的左端点和右端点 注意端点的处理即可

-----
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE0NzExMjQwNTYsLTE2MTk2MzQ4MjMsNT
kwMzA4OTk3LDczMDk5ODExNl19
-->