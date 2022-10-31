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

https://leetcode.com/discuss/interview-question/1816811/Microsoft-OA-or-Graph-Question

This was the 2nd Question in coditlty Test.  
Can anyone provide the best Algo for this Problem.  
I was able to slove this problem using Bfs but my code is given TLE, Because I was caluclating path from every Hospital and taking the min from them.  
N, H Value Range from 1 to 100000
![image](https://assets.leetcode.com/users/images/3efc9a44-0b91-48c1-9f16-c8f06ff99dd7_1665574332.802469.png)

从有救护车的城市开始bfs 注意bfs最后结果需要减1

-----

[Google | Onsite | SDE | Maze question | L4](https://leetcode.com/discuss/interview-question/2711886/Google-or-Onsite-or-SDE-or-Maze-question-or-L4)

I was asked the following maze traversal question and I was not able to solve a specific test case.

Question is to find the shortest distance between a Source and Destination node when there is an alarm node. During traversal when you step on this alarm node, the destination node gets locked. This means even if you enter the destination node you are not done yet. You will have to now traverse to a Switch node and then after visiting this Switch Node you can unlock the destination node and then now you can traverse to the destination node.

```
Given: Source Node (Src) , Destination Node (D), Alarm Node (A), Switch Node (Sw). 
To Find: Shortest distance between Source and Destination Node. If you step on an Alarm node, your destination gets locked. You need to visit a Switch Node to unlock your destination Node.

```

I just used a simple BFS with a varying destination node ( First the destination would be D, during traversal if I visited an alarm node, then the new destination node would be Sw and then once I visit the Sw node, the new destination would be D and then continue to traverse the graph)

I couldn't pass a test case where D got locked due to visiting an Alarm node and then the nodes from D to Sw were all visited and I couldn't go back to D.

Please let me know what would be the best solution for this question.

PS:  
Rejected due to the reason of "Efficacy", trying to learn from mistakes and hopefully can perform better next year.

答案: bfs即可 

-----

[Hard OA question](https://leetcode.com/discuss/interview-question/2740665/Hard-OA-question)

![image](https://assets.leetcode.com/users/images/b7c9aa97-c073-4c73-8767-e81e057f97e9_1666668488.8197927.png)

------
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE0MzMzODU5NTgsOTQ3ODM2NTIyLC02OD
cxMDYyNTYsMTMxNzMyOTQ3MSwtMTM5MjA5NzAyNywzOTc4NzEy
MzYsMTE1MDM5MTQ4Nl19
-->