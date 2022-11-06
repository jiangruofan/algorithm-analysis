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


<!--stackedit_data:
eyJoaXN0b3J5IjpbMTc2MzE3NzAyNywtMjA1MTM2NzQzMywtMT
c5MjEzMzQwNywtMTYzMTA2NDU2N119
-->