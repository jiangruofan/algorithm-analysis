[Google interview question](https://leetcode.com/discuss/interview-question/2064289/Google-interview-question)

Given an integer array  `a`, and 2 integers -  `c`  and  `k`, where  `c`  is the favourite number and  `k`  is the maximum number of replacements we can make. We have to find the maximum number of contiguous elements which are equal to  `c`. We can replace  `k`  number of elements with any number we want.

Example -  `a = [1,2,2,3,2,2,2,4], c=2, k=2`.

-   In this case, without any replacement, maximum number of contiguous elements will be 3 (from index  `4`  to index  `6`).
-   We can replace element at index  `3`  with number  `2`  so now array will be  `a = [1,2,2,2,2,2,2,4]`  , maximum number of contiguous elements will be 6 (from index  `1`  to index  `6`).
-   For last replacement, we can replace either element at index  `0`  or index  `7`  with number  `2`, so maximum number of contiguous elements will be  `7`, which is the answer..

滑动窗口即可

------------

[Google phone round](https://leetcode.com/discuss/interview-question/1107192/Google-phone-round)

Given two lists of numbers. Write a function that computes the probability that x < y, where x and y are randomly sampled elements from the first and second list respectively.

答案:
```
public double probability(int[] list1, int[] list2) {
    int[] greaterElements = new int[list1.length];
    for (int i = 0; i < list1.length; i++) {
        int y = 0;
        for (int j = 0 ; j < list2.length; j++) {
            if (list2[j] > list1[i])
                y++;
        }
        greaterElements[i] = y;
    }

    int count = 0;
    for (int i = 0; i < list1.length; i++)
        count += greaterElements[i];
   
    return count / (list1.length * list2.length);
}
```

---------------

[Uber OA | 6 Month Internship | 2023 | Off Campus](https://leetcode.com/discuss/interview-question/2624313/Uber-OA-or-6-Month-Internship-or-2023-or-Off-Campus)

You are standing at the start of a very long straight road. On the road, there are  `n`  cupcakes present. You are given the distance of each cupcake from the start of the road. Each of these distances is an integer, and multiple cupcakes can be present at the same distance from the start of the road.

You have to select 2 intervals of length  `k`  on the road and collect all the cupcakes that lie inside either of the intervals. The intervals are allowed to intersect.  
For example, for  `k = 3`, the interval [1, 4] is a valid interval of length 3, and by  
choosing that interval, you can collect all the cupcakes that lie at a distance of 1, 2, 3 or 4 from the start of the road.

**Find the maximum number of cupcakes that you can collect by picking 2 intervals as described above.**

**Sample Test Cases**

`n = 6`

`k = 1`

`distance = [ 1, 1, 2, 6, 8, 9 ]`

`expected output = 5`

**Explanation : -**

We can pick the 2 intervals [1, 2] and [8, 9]. Both these intervals have length of 1 and there are a total of 5 cupcakes that lie in these intervals.

-   **[execution time limit] 1 seconds (cpp)**
    
-   **[input] integer n**
    
    The number of cupcakes : -
    
    ```
      1 <= n <= 2 * (10 ^ 5)
    
    ```
    
-   **[input] integer k**
    
    the length of the intervals that you can pick :-
    
    ```
      1 <= k <= 10^9
    
    ```
    
-   **[input] array.integer distance**
    
    Array of  `n`  integers. The  `i th`  integer describes the distance of the  `i th`  cupcake from the start of the road.
    
    `1 <= Ai <= 10^9`, where  `Ai`  is the  `i th`  element in the array. All the  `Ai S`  are  **NOT NECESSARILY DISTINCT**.
    
-   **[output] integer**
    
    The maximum number of cupcakes you can collect.

-------------

[Microsoft Online assessment question 5 tasks in 90 min (2)](https://leetcode.com/discuss/interview-question/2220156/Microsoft-Online-assessment-question-5-tasks-in-90-min-%282%29)

anagram
![image](https://assets.leetcode.com/users/images/621c675c-b777-4559-8080-13c050cffda8_1656625048.6044838.png)

---------

[Microsoft | SDE-1 | OA 2022](https://leetcode.com/discuss/interview-question/2055241/Microsoft-or-SDE-1-or-OA-2022)

Q2)  **A patient needs rehabilitation in next N days(0, N-1), The rehabilitation consists of X sessions. for every rehabilitation session other than the last one session, the next session is exactly Y days later.**

**You are given an array A of N integers listing the costs of the individual rehab session on the N days, that is rehab on kth days costs A[k]**

**write a function**

```
    def solution (A, X,Y):

```

**that given the array A and the two integers X and Y return the minimum cost of rehabilitation. It is guaranteed that it is always possible to complete all rehab sessions**

Ex:  
**A = [4,2,3,7] X = 2 Y = 2**  
o/p 7 (sum of cost of day 0 and 2);

**A = [10, 3 ,4, 7] X = 2 Y = 3**  
o/p 17 (sum of day 0 and day 3)

**A = [4,2,5,4,3,5,1,4,2,7] X = 3 Y = 2**  
6 (day 4, 6 , 8)

多起点的滑动窗口 

-----------

[Roblox OA question](https://leetcode.com/discuss/interview-question/2567955/HARD-Roblox-OA-question)

You are given an array of integers numbers and a positive integer k. Your task is to count the number of contiguous subarrays having at least k duplicate pairs, the indices of which are pairwise distinct.  
More formally, your task is to count the number of contiguous subarrays numbers[i..j] for which there exist 2 * k pairwise distinct indices i ≤ i1, j1, i2, j2, ..., ik, jk ≤ j, such that numbers[i1] = numbers[j1], numbers[i2] = numbers[j2], ..., numbers[ik] = numbers[jk].  
Example  
• For numbers = [0, 1, 0, 1, 0] and k = 2, the output should be solution(numbers, k) = 3.  
There are 3 subarrays that satisfy the criteria of containing at least k = 2 pairs of duplicate elements with pairwise distinct indices:  
o numbers[0..3] = [0, 1, 0, 1]  
o numbers[1..4] = [1, 0, 1, 0]  
o numbers[0..4] = [0, 1, 0, 1, 0]  
In each of the subarrays above we can form one pair of 0s and one pair of 1s.  
• For numbers = [2, 2, 2, 2, 2, 2] and k = 3, the output should be solution(numbers, k) = 1.  
There is only 1 applicable subarray: numbers[0..5] = [2, 2, 2, 2, 2, 2], which contains three pairs of 2s.  
• For numbers = [1, 3, 3, 1] and k = 1, the output should be solution(numbers, k) = 4.  
There are 4 subarrays that satisfy the criteria of containing at least k = 1 pair of duplicate elements:  
o numbers[0..2] = [1, 3, 3]  
o numbers[0..3] = [1, 3, 3, 1]  
o numbers[1..2] = [3, 3]  
o numbers[1..3] = [3, 3, 1]  
In each of the subarrays above, there is at least a pair of 3s.  
Input/Output  
• [execution time limit] 4 seconds (py3)  
• [input] array.integer numbers  
An array of integers.  
Guaranteed constraints:  
2 ≤ numbers.length ≤ 2000,  
0 ≤ numbers[i] ≤ 104.  
• [input] integer k  
A positive integer.  
Guaranteed constraints:  
1 ≤ k ≤ numbers.length / 2.  
• [output] integer  
Return the number of contiguous subarrays which contain at least k pairs of duplicate elements with pairwise distinct indices.

----

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
先预处理二维前缀和 然后就是滑动窗口了 每滑动一次 那么新增的unique数字就保存在y中 同时移除不是unique的数字 如果当前窗口等于最大sum 那么就把y中的数字合并到x中

------

[infosys hard question (if you solve it before 25 min you can easily getinto faang)](https://leetcode.com/discuss/interview-question/2734425/infosys-hard-question-%28if-you-solve-it-before-25-min-you-can-easily-getinto-faang%29)

![image](https://assets.leetcode.com/users/images/f8b0f336-efa4-4b19-9163-eda3436eb372_1666499390.9713988.jpeg)
![image](https://assets.leetcode.com/users/images/2b638a44-fe8b-44aa-82a4-86e4c23fe46b_1666499408.7006721.jpeg)

given k and list1

    l, r = 0, len(list1) - 1
    list1.sort()
    cntl = cntr = 0
    while 1:
      while cntl <= cntr and cntl + (l + 1) * (list1[l+1] - list1[l]) <= k:
        cntl += (l + 1) * (list1[l+1] - list1[l])
        l += 1
      if l == r:
        return list1[r] - list1[r-1]
      elif l == r + 1:
        return list1[l] - list1[r]
      while cntr <= cntl and cntr + (len(list1)-r) * (list1[r] - list1[r-1]) <= k:
        cntr += (len(list1)-r) * (list1[r] - list1[r-1])
        r -= 1
      if l == r:
        return list1[l+1] - list1[l]
      elif r == l - 1:
        return list1[l] - list1[r]
      if cntl + (l + 1) * (list1[l+1] - list1[l]) > k and cntr + (len(list1)-r) * (list1[r] - list1[r-1]) > k:
        break
    return list1[r] - list1[l]

------
      
[Microsoft | Phone | SDE 2 | Subsequence Max Product](https://leetcode.com/discuss/interview-question/1742147/Microsoft-or-Phone-or-SDE-2-or-Subsequence-Max-Product)

1 hour scheduled call with senior dev on a team (MS Teams call, no video). Couple minutes of introductions, then straight to the Codility problem

-   Given a large number of upto 100 digits, the objective is to find the subsequence of n digits with max product

ex: num = 145623 , n = 3  
answer would be 120, the product of 4 x 5 x 6

I quickly came up with a O(n2) solution like this:

```

for(int i = 0; i < nums.Length - 1; i++) {
	int product = nums[i];
	for(int k = 1; k < n; k++) {
		product = product * nums[k];
	}
}

```

This solution passed test cases, but then the interviewer pushed me to find a solution with faster time complexity. I mentioned that a sliding window could be used here instead, but through my anxiety it took me longer than expected to type out a sliding window solution. Eventually got it all working, but had lots of issues with zeroes in the num string.

注意对于0的特殊处理

----

https://www.chegg.com/homework-help/questions-and-answers/2-minimum-segments-given-array-consisting-n-intervals-ith-interval-type-b--also-given-inte-q87487454

![2. Minimum Segments
Given is an array consisting of n intervals. The ith interval is of type
(a[i], b[i]). Also given is an i](https://media.cheggcdn.com/media/b4e/b4e55df5-ea5e-4b3d-aa9c-d44c53e3a8b7/phpNZkpJp)
![Language
Function Description
Complete the function minimum Division in the editor below.
C++
minimum Division has the follow](https://media.cheggcdn.com/media/b9c/b9cfeb19-e8f6-4ce8-9e91-d4053ecd9100/php4skBlR)

------

[Tekion | SSE | Rejected](https://leetcode.com/discuss/interview-question/2907614/Tekion-or-SSE-or-Rejected)

1.  Give a set of n numbers and integer K  
    a) subset of length k such that diff between min and max should be minimum  
    b) subarray of length k such that diff between min and max should be minimum

----

[Walmart | Onsite | grumpy-bookstore-owner](https://leetcode.com/discuss/interview-question/2997924/Walmart-or-Onsite-or-grumpy-bookstore-owner)

For DSA round of walmart was asked the following question  
Grumpy Bookstore Owner

There is a bookstore owner that has a store open for n minutes. Every minute, some number of customers enter the store. You are given an integer array customers of length n where customers[i] is the number of the customer that enters the store at the start of the ith minute and all those customers leave after the end of that minute.

On some minutes, the bookstore owner is grumpy. You are given a binary array grumpy where grumpy[i] is 1 if the bookstore owner is grumpy during the ith minute, and is 0 otherwise.

When the bookstore owner is grumpy, the customers of that minute are not satisfied, otherwise, they are satisfied.

The bookstore owner knows a secret technique to keep themselves not grumpy for minutes consecutive minutes, but can only use it once.

Return the maximum number of customers that can be satisfied throughout the day.

----



        
    
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTU5MzEwMDIxMSwtNzIxMjM2MDQ0LDg2ND
cyNzA2MSwtNDkxMzUyMjAzLDQ4MDA5NTU0MSwxNDkxNDc5Mzk5
LDU5NTEyMjgwMywxMjYzMTk0MjA0LDMyMDQyMzgwOCwtMTEzMj
I1OTAxLDczMDk5ODExNl19
-->