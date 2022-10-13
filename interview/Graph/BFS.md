[Google OA](https://leetcode.com/discuss/interview-question/1440227/Google-OA)

Given an array of numbers A and two integers S and D, you can perform three operations

1.  x + A[i]
2.  x - A[i]
3.  x xor A[i] (bitwise xor)  
    Each of these operations cost one move. Task is to find the minimum number of moves in which S can be changed to D or return -1 otherwise.

**Sample TC:**  
A = [6, 2, 7, 7]  
S = 10  
D = 21

**Output:**  3

**Explaination:**  
10 + A[3] = 17  
17 + A[1] = 19  
19 + A[1] = 21

I was not able to come up with anything as I think it clearly is a Math problem.

**EDIT**  
**Constraints:**  
x lies in [0, 100000]  
1 <= A.size() <= 1000  
-10^9 <= A[i] <= 10^9

--------------

[Google On site](https://leetcode.com/discuss/interview-question/1290963/Google-On-site)

You're given a 2 grid array of subway stops.  
Each subway stop has a value that represents the current number of people waiting there  
Given 2 stops, return a stop with more people waiting that could've lead to both stops.  
The path to both stops must only contain other stops with a number of people less or equal to the current stop

If there are multiple valid stops, return the nearest stop.  
If there's no valid stop, return null.

Example Input:

Stop 1 has 5 people waiting at (2, 3)  
Stop 2 has 5 people waiting at (2, 1)

[5, 9, 7, 6]  
[7, 8, 1, 5]  
[6, 5, 2, 5]  
[9, 3, 3, 2]

Example Output: Stop with 9 people waiting at (0, 1)

Path for stop 1: 9 -> 7 -> 6 -> 5 -> 5  
Path for stop 2: 9 -> 8 -> 5

这题和苏伊士那道小红书的题目一样
只需要从两个点开始bfs 然后记录最短路径长度即可

------------

[AMAZON OA 2023 || REACH THE END IN TIME](https://leetcode.com/discuss/interview-question/2615840/AMAZON-OA-2023-oror-REACH-THE-END-IN-TIME)

![image](https://assets.leetcode.com/users/images/e29d552f-e962-4dab-9803-a8d949fcef53_1663978476.81918.png)
![image](https://assets.leetcode.com/users/images/97846768-3ed8-4648-8861-fd0c403b9b91_1663978486.6703243.png)
![image](https://assets.leetcode.com/users/images/de100ec8-2276-483b-84bc-e846f095cfbb_1663978496.047809.png)
![image](https://assets.leetcode.com/users/images/639bf83f-c3bc-4fff-a4b8-f35c2db31f0e_1663978503.540362.png)

-----------

[Codility Graph Hard Question OA](https://leetcode.com/discuss/interview-question/2694254/Codility-Graph-Hard-Question-OA)

This was the 2nd Question in coditlty Test.  
Can anyone provide the best Algo for this Problem.  
I was able to slove this problem using Bfs but my code is given TLE, Because I was caluclating path from every Hospital and taking the min from them.  
N, H Value Range from 1 to 100000
![image](https://assets.leetcode.com/users/images/3efc9a44-0b91-48c1-9f16-c8f06ff99dd7_1665574332.802469.png)

从有救护车的城市开始bfs 


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEwMDU1MDQxMjIsMzk3ODcxMjM2LDExNT
AzOTE0ODZdfQ==
-->