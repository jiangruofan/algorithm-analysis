[Google | Onsite](https://leetcode.com/discuss/interview-question/1901074/Google-or-Onsite)

Basically, 124. Binary Tree Maximum Path Sum, but with an extra requirement: the path with exactly length of K. Anyone can solve it? Need help here. Thanks.

----------

[Google | Phone Screen](https://leetcode.com/discuss/interview-question/2775420/Google-or-Phone-Screen)

Given a hierarchy of managers and employees working under them, as a tree, every person has some seniority level based on their experience in company.  
You need to call them for the party and you want to get maxSeniorityPoints.

```
Employee {
Integer id,
List<Employee> subordinates;
Integer seniorityLevel;
}

```

If you are calling manager you cannot call their direct sub-ordinates and vice versa.

```
             A(10)		 
  /              |      \           \        \
b(4)            c(9)     d(9)     e(9)     f(9)
|     \
x(9)    y(9)

```

Ans for above will be:  
we will take x, y, c, d, e, f

and we will not call A and b.

Ans : 54

Similar to LC337- House Robber 3

----

[Walmart | OA | Subtree Product](https://leetcode.com/discuss/interview-question/2811667/Walmart-or-OA-or-Subtree-Product)

You are given a tree of N nodes.  
You can break the connection between any 2 nodes.  
This can be performed multiple number of times.  
What is the maximum product of the number of nodes of the subtrees formed.

Sample Input #1  
5  
1 2  
2 3  
3 4  
4 5  
Sample Output #1  
6

( As connection between 2 and 3 can be broken and  
the remaining subtrees are 1, 2 and 3, 4, 5 which have 2 and 3 nodes each.  
2 * 3 = 6 )

Sample Input #2  
3  
1 2  
2 3  
Sample Output #2  
3

( No connection is broken )

----

[Seap Trees | Inflection.io | OA 2023](https://leetcode.com/discuss/interview-question/3001318/Seap-Trees-or-Inflection.io-or-OA-2023)

![image](https://assets.leetcode.com/users/images/ea56165d-2a6d-4758-abee-22c064f8f87b_1672898238.5163288.png)

-----

[Reverse Edges | OA 2023](https://leetcode.com/discuss/interview-question/3001299/Reverse-Edges-or-OA-2023)

The country of hackerland can be represented as represented as as a graph of g_nodes cities connected with  `g_nodes -1`  uni-directional edges. The ith edge connects cities`g_from[i]`  to  `g_to[i]`.  
The graph is such that if the roads were bidirectional, every node would be reachable from every other node. Note that if the edges were undirected, the resulting graph would be a tree.  
For each city  `i ( 1<= i <= g_nodes)`  find the minimum number of edges that must be reversed so that it is possible to travel from ith city to any other city of the graph using the directed edges.  
For ex.
```
g_nodes = 4
g_edges = 3
g_from = [1, 2, 3]
g_to = [4, 4, 4]
```
![image](https://assets.leetcode.com/users/images/3e5ec820-fe7f-491a-aa50-03767b8edb89_1672897366.4790876.png)

这题和dfs那几题类似 

-----

<!--stackedit_data:
eyJoaXN0b3J5IjpbNTA5NTczMTg4LC0xMDU2NjI2NDM5LC0xMj
I2Mzk2MzQ5LC0yMDUxMzY3NDMzLC0xNzkyMTMzNDA3LC0xNjMx
MDY0NTY3XX0=
-->