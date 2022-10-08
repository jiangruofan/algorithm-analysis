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


















<!--stackedit_data:
eyJoaXN0b3J5IjpbMzc0ODg2Nzc3LC01ODQ4MDg2NTBdfQ==
-->