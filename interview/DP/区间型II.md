[Walmart Intern Question](https://leetcode.com/discuss/interview-question/2792749/Walmart-Intern-Question)

**Can anyone tell the code for this question!**

Alice is playing a game. In this game, an array A of N cards is given with some associated points. The task is to reduce the array to a single element. It can be achieved by operating a certain number of times. For every operation, Alice is awarded some points, and the total score would be the sum of points awarded overall operations.

The operation is defined as:

Select a contiguous subarray (i,j) starting at index i and ending at index j from A with at least two elements, and replace it with the sum of the subarray elements. The points awarded for this operation is (-1+1)"ming, where ming represents the minimum value in subarray (i,j).

• Print the maximum possible score Alice can get.

Constraints:  
1 <= n <= 60  
-1e9 <= A[i] <= 1e9

---

[Please answer this question](https://leetcode.com/discuss/interview-question/3015774/Please-answer-this-question)

Tesla is having an army of Highly Advanced Al based Robots. The  
robots are designed in such a way that Tesla can fuse 2 robots in order  
to make a single robot of an upgraded level. In doing so, the power and  
intelligence of both the robots gets fused into that single robot (need  
not always increase) and the level of the fused robot gets upgraded i.e.  
if two robots of level L₁and L2 gets fused, the final robot obtained is of  
level L₁ + L₂. A robot of higher level is always better than a robot of  
lower level.

Tesla is having N robots standing in a queue (all of Level 1). He wants  
to fuse all the robots into each other in order to make a final robot of  
level N. However he can only combine the adjacent robot and there is  
an additional cost that Tesla has to incur in order to successfully  
perform the fusion. The cost of the fusion depends on the (power,  
intelligence) tuple of the robots.

If there are two robots standing adjacent to each other, where the  
(power, intelligence) tuple of the first robot is (a, b) and that of the  
second robot is (b, c) respectively then the cost of fusion comes out to  
be: a *b *c. Also the (power, intelligence) tuple of the resultant robot  
is (a,c).

You have to find out the minimum cost that Tesla has to incur in order  
to perform this task of fusion.

Note: It is guaranteed that the for all the adjacent robots, the intelligence of the ith robot is same as the power of (i+1)th robot.

Input

• First line of input contains an integer N. describing the number

of robots standing in the queue.

Then N lines follows, each line containing 2 integers representing the power and intelligence of each of the N robots.

Output

A single line which denotes the minimum cost of fusion

Constraints

1 <= N <= 100

1 <= Power <= 1000

1 <= Intelligence <= 1000

Sample test case

Input

3

2.10

10 3

34

Output

84

EXECUTION TIME LIMIT

2 seconds

类似戳气球

----
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTM5MzU3MzUwOSwtMTI5MDkyNDE0OSw3Mz
A5OTgxMTZdfQ==
-->