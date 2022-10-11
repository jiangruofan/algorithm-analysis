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

答案: 先扫描一遍string 用一个cnt记录多余的左括号 如果遇到了一个多余的左括号 先把这个左括号变成右括号 将you 遍历结束后
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTMyMzYzNDA1Nyw1OTAzMDg5OTcsNzMwOT
k4MTE2XX0=
-->