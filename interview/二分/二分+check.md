[Facebook | Google | London | Offers](https://leetcode.com/discuss/interview-question/1110505/Facebook-or-Google-or-London-or-Offers)

-   check if there is a square of 1s in a 2d matrix (that contains 0s and 1s). the square has the size of at least sqrt(min(N,M)). the input either has one valid square or not (all 0s).
    

```
bool hasSquare(int[][] matrix)
```

-----------

[Google | OA | SDE (2020)| India](https://leetcode.com/discuss/interview-question/805468/Google-or-OA-or-SDE-%282020%29or-India)

1.  Given array A of N Integers a1  ,a2, a3...... aN  . You are also given two integers S and M. You can pick subarray of size S where you have to perform M operation by incrementing the value of each element value by 1. Find the maximum value of minimum value in array A.  
    Example

```
Input:
N = 6 ,M = 5 ,S =2
1 2 3 4 5 6
Output:
4
Explaination:
1st opertaion subarray index range (0,1) 2 3 3 4 5 6
2nd opertaion subarray index range (0,1) 3 4 3 4 5 6
3rd opertaion subarray index range (0,1) 4 5 3 4 5 6
4th opertaion subarray index range (2,3) 4 5 4 5 5 6
5th opertaion subarray index range (0,1) 5 6 4 5 5 6
```

----------

[Google | Phone Screen | Salary Adjustment](https://leetcode.com/discuss/interview-question/351313/Google-or-Phone-Screen-or-Salary-Adjustment)

Give an array of  `salaries`. The total salary has a  `budget`. At the beginning, the total salary of employees is larger than the  `budget`. It is required to find the number  `k`, and reduce all the salaries larger than  `k`  to  `k`, such that the total salary is  **exactly equal**  to the  `budget`.

**Example 1:**

```
Input: salaries = [100, 300, 200, 400], budget = 800
Output: 250
Explanation: k should be 250, so the total salary after the reduction 100 + 250 + 200 + 250 is exactly equal to 800.

```

You can assume that solution always exists.

Related questions:

-   [Array Adjustment](https://leetcode.com/discuss/interview-question/349612/Google-or-Phone-Screen-or-Array-Adjustment)

求一个前缀和 排个序

---------

[Google | New Grad | Onsite 2022 | USA](https://leetcode.com/discuss/interview-question/2104302/Google-or-New-Grad-or-Onsite-2022-or-USA)

You have a table with two columns with some text in them. Now you need to find column width such that the height of the table is minimum.

```
-------------------------------------
| some text            | Description  |
| some text            | some text    |
| some text            | some text    |
| some text            |              |
------------------------------------


```

Given,  
table width = 20  
text1 =  `some string`  
text2 =  `some string`  
return width of a column such that height is minimum

答案: 对高度进行二分

----------

[Snowflake | OA | 2022 | Minimize Array Value](https://leetcode.com/discuss/interview-question/2146013/Snowflake-or-OA-or-2022-or-Minimize-Array-Value)

Given an array arr of n positive integers, the following operation can be performed any number of times. Use a 1-based index for the array.

-   Choose any i such that 2<=i<=n
-   Choose any x such that 1<=i<=arr[i]
-   Set arr[i-1] to arr[i-1]+x
-   Set arr[i] to arr[i]-x

Minimize the maximum value of arr using the above operation and return value.

Example: arr=[1,5,7,6]  
arr becomes [1,9,3,6] after choosing i=3 and x=4 as x<=arr[3], i.e. 4<7  
arr becomes [5,5,3,6] after choosing i=2 and x=4 as x<=arr[2]  
arr becomes [5,5,4,5] after choosing i=4 and x=1 as x<=arr[4]  
output = 5

Example : arr = [5,15,19]  
output = 13

Example : arr = [10,3,5,7]  
output = 10

答案: 题目的意思就是可以把任意一个数往左边移

--------

[Thoughts on this good problem ?](https://leetcode.com/discuss/interview-question/2553496/Thoughts-on-this-good-problem)

You are playing a game, in which, in each turn, you can reduce the number of blocks in a pile by at max “k” blocks. Note that, in each turn, you can remove blocks on only one pile. You have t number of turns in which you are supposed to remove all blocks.

Determine minimum value of k to remove all blocks in t turns.

Example 1:  
Input: piles = [30,11,23,4,20], t = 5  
Output: 30

Example 2:  
Input: piles = [30,11,23,4,20], t = 6  
Output: 23

----------

 #### [Microsoft India | Technical Interview | August 2022](https://leetcode.com/discuss/interview-question/2532865/Microsoft-India-or-Technical-Interview-or-August-2022)
You are given a binary matrix (with 1's and 0's) of size n x n. you have to divide the matrix into 4 sections by dividing it by one row and one column. each section must have atleast one cell. score of a segment is the number of 1's in that section. You have 3 sisters and they are given with the sections that has the highest 3 scores, and you are left with the section having least score always.  
you have to divide the matrix in such a way that you will get the maximum score after providing to the sisters.

My Approach:  
we define dp[i][j] as sum from matrix[0][0] to matrix[i][j] rectangle. as preprocess and check for every value of i,j so o(n^2) complexity

二分＋check 类似二维版本 力扣1231 
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTU0NTIwNzQzMV19
-->