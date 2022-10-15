[Ebay OA](https://leetcode.com/discuss/interview-question/2704151/Ebay-OA)

Given a rectangular matrix matrix and an integer frameSize, consider the outer frames of all frameSize × frameSize contiguous square submatrices of matrix. Your task is the following:  
• Calculate the sum of all numbers located on the frame of each frameSize × frameSize submatrix.  
• Determine the maximum of all these sums.  
• Find all the distinct numbers that appear in at least one of the frames of frameSize × frameSize submatrices with a sum equal to the maximum. Each integer from these square frames should be calculated exactly once. Return the sum of these distinct numbers.  
Note: A frameSize × frameSize square frame contains max(1, 4 × (frameSize - 1)) cells. See example for better understanding.  
Example  
For  
matrix = [[9, 7, 8, 9, 2], [6, 9, 9, 6, 1], [4, 10, 1, 3, 10], [18, 2, 3, 9, 3], [4, 6, 8, 5, 21]]  
and frameSize = 3, the output should be solution(matrix, frameSize) = 92.

Note:  
If we consider all the 3 × 3 square frames in matrix, there are only 3 of them with a maximum sum of 54:  
[[9, 7, 8], [6, 9, 9], [4, 10, 1]]  
(9 + 7 + 8 + 6 + 9 + 4 + 10 + 1 = 54)  
[[4, 10, 1], [18, 2, 3], [4, 6, 8]]  
(4 + 10 + 1 + 18 + 3 + 4‍‍‌‌‌‌‌‍‌‌‍‌‍‍‌‍‌‍‍‌ + 6 + 8 = 54)  
[[1, 3, 10], [3, 9, 3], [8, 5, 17]]  
(1 + 3 + 10 + 3 + 3 + 8 + 5 + 21 = 54)  
The only distinct numbers are 1, 3, 4, 5, 6, 7, 8, 9, 10, 18 and 21. So the answer is 1 + 3 + 4 + 5 + 6 + 7 + 8 + 9 + 10 + 18 + 21 = 92.

2个set  -x是答案set  -y是暂存的unique数字
先预处理二维前缀和 然后就是滑动窗口了 每滑动一次 如果当前的窗口sum不是最大值 那么新增的unique数字就保存在y中 同时移除不是unique的数字 
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTI2MTM5ODYwNl19
-->