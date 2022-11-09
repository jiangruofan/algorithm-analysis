[Google SWE Intern OA (SEA)](https://leetcode.com/discuss/interview-question/887761/Google-SWE-Intern-OA-%28SEA%29)

![image](https://assets.leetcode.com/users/images/08356eb2-b2a5-4fad-8d21-ecd5d4245c90_1602324741.0080948.png)

答案:
Fast solution of Q1, doing only n times a gcd call. Observe that in the final array the minimal integer what we can get is the gcd of all numbers. If that is g=gcd(v[0],v[1],..v[n-1]) and the maximal number is m in the input vector then all numbers will be m-t*g in the final array, where t>=0 integer, hence the answer is just m-(K-1)*g if and only if it is positive.

--------------

[Microsoft OA, L61](https://leetcode.com/discuss/interview-question/2118664/Microsoft-OA-L61)

![image](https://assets.leetcode.com/users/images/8b44b73f-b8a2-474d-b338-5203228d67a8_1654524981.5471747.jpeg)
![image](https://assets.leetcode.com/users/images/c583b21d-44c9-4fc2-b5e4-96f2db6197fa_1654525040.6027477.jpeg)
![image](https://assets.leetcode.com/users/images/f410c76c-83ea-436e-8bed-5eed66ac5e0d_1654524981.1502728.jpeg)

质因数分解

---------------

[OA hard /2022/ help needed](https://leetcode.com/discuss/interview-question/2672379/OA-hard-2022-help-needed)

![image](https://assets.leetcode.com/users/images/38b09440-bbea-4a30-ada0-c6d882c4119f_1665144968.5736208.jpeg)
![image](https://assets.leetcode.com/users/images/ae09702f-897b-4e46-9ad1-cc26f5b6e5c4_1665144968.5567856.jpeg)
先对所有的数字做质因数分解 用hashmap存储质因数对应的数字个数

-------

[Swiggy OA Help](https://leetcode.com/discuss/interview-question/2721830/Swiggy-OA-Help)

Had 5 questions, solved other 4 but i was unable to this one.  
Pls share solution.

Problem Statement

Ram has an Array Arr which may or may not be in strictly increasing order. He wants to make this array increasing but does not wish to change the position of any element so he came with an idea that he will replace an element with any of its divisors i.e he changes an element X to M if X%M=0.  
Your task is to tell whether the given array can be transformed to strictly increasing by performing the operation given above.

Input

First line of input contains the size of the array N. Next line of input contains N space- separated integers depicting the values of the array Arr.

Constraints:-

1 <= N <= 100000  
1 <= Arr[i] <= 100000

Output

Print "YES" if the array can be transformed in the strictly increasing order else print "NO".

Example

Sample Input:-  
5  
1 2 16 16 16

Sample Output:-  
YES

Sample Input:-  
4  
1 3 8 4

Sample Output:-  
NO

答案: 贪心思想 遍历每一个数字看能整除哪些数字 选一个比前面数字大的最小的数字

----

[Intersting problem sap labs](https://leetcode.com/discuss/interview-question/2786561/Intersting-problem-sap-labs)

![image](https://assets.leetcode.com/users/images/013f7880-293d-46f3-8495-696abc590ec6_1667773157.679026.jpeg)

质因数分解+并查集

---

[Media.net | OA | SSE | Mar-2021](https://leetcode.com/discuss/interview-question/1096727/Media.net-or-OA-or-SSE-or-Mar-2021)

An array  **A**  is called "**PrimeArray**" if there is no two elements such that their product is a perfect square.  
A = { 1, 3, 5, 4}  
E.g.  `A[0]*A[3] = 4`which is  `2*2`  
Hence A is not a "**PrimeArray**"

If  **A**  is not a "**PrimeArray**", increment any of the elements by 1 to transform  **A**  into a "**PrimeArray**" (incrementing any one element by 1 counts as one operation, you can perform any number of such operations on any number of elements).

Find minimum number of operations to transform array into a "**PrimeArray**".

先排个序 枚举perfect square  然后进行分解 看等于哪两个数字相乘 得到两个数字后二分数组看最接近的两个数字 时间复杂度是 10^5*logn*logn 

----





















<!--stackedit_data:
eyJoaXN0b3J5IjpbMTQ5MjMzNjU0MSw0MTY1Njk5MzMsLTU5Mz
U0ODY0MCw0NzEwNDY3NSwzNzQ4ODY3NzcsLTU4NDgwODY1MF19

-->