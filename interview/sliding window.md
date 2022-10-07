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
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTc0MDY4MDgwNSwtMTEzMjI1OTAxLDczMD
k5ODExNl19
-->