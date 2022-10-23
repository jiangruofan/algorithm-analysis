[Google | Onsite | Interview Questions](https://leetcode.com/discuss/interview-question/1570979/Google-or-Onsite-or-Interview-Questions)

Given a number and intervals, find all intervals having that number effectively. Imagine the method is being called thousands of times.  
Let's say we want to create a simplified version of Google Search. Here, we have many fixed intervals and we want to be able to quickly find all intervals containing a number.  
Follow up: What if new intervals can be added over the time.

区间修改 单体查找 使用lazy tag

---------

[Google Onsite](https://leetcode.com/discuss/interview-question/1521932/Google-Onsite)

**Coding Round 2:**  
It was similar to merge intervals  [https://leetcode.com/problems/merge-intervals/](https://leetcode.com/problems/merge-intervals/)  but with a bit modification.  
Given Starting intervals we'll get 2 type of queries

1.  Add intervals
2.  Search for a particular number

eg:  
Given initial intervals as : [[1,3],[2,6],[8,10],[15,18]]  
Q queries  
[1 4 5] => 1 represent query of type 1 and 4-5 is interval  
[2 2] => 2 represent query of type 2 search for element 2

类似 [https://leetcode.com/problems/count-integers-in-intervals/](https://leetcode.com/problems/count-integers-in-intervals/)

-----

[Google Interview Question](https://leetcode.com/discuss/interview-question/1143056/Google-Interview-Question)

This was the Google Interview Questions asked to me. Can someone please provide me solution for it.

Find the max stars fit in the given rectangle in the Galaxy

func maxStarFitInRect(stars:[Star], width: Float, height: Float) -> Int {

}

Struct Star {  
let x: Float  
let y: Float  
}

[https://www.cnblogs.com/tsw123/p/4470115.html](https://www.cnblogs.com/tsw123/p/4470115.html)

--------------

[Google | Phone | Data Structure for Storing Ranges](https://leetcode.com/discuss/interview-question/884712/Google-or-Phone-or-Data-Structure-for-Storing-Ranges)

Position: L3  
Location: Bangalore, India

Design a data structure with two operations 1. addRange(int start, int end) and 2. isPresent(int point)  
Here range means an interval, so the data structure contains information of all ranges added uptil that point. contains(int point) returns true if the point is contained in any of the ranges or false otherwise.  
How to do both operations with O(logn) complexity or better ?

区间覆盖问题

-------------

[Google | Onsite | Range](https://leetcode.com/discuss/interview-question/2615499/Google-or-Onsite-or-Range)

Implement the  **Range**  class:

**void insert(int start, int end)**  insert a new range , start and end are positive numbers

**bool check(int number)**  check the number if exists in the whole range and if exists return true otherwise return false

The functions check and insert must each run in O(log(n)) time complexity and for space complexity must be o(n) where n is the number of ranges

Example:  
Input:  
Insert 1,5  
check 5  
insert 1,1000  
check 100  
check 1001

Output:  
True  
True  
False

---------------

[Microsoft - Sr Software Engineer - player ranking update](https://leetcode.com/discuss/interview-question/2459463/Microsoft-Sr-Software-Engineer-player-ranking-update)

This is similar to this post [https://leetcode.com/discuss/interview-question/1491917/appropriate-data-structure-to-store-data](https://leetcode.com/discuss/interview-question/1491917/appropriate-data-structure-to-store-data)  
So, we have between 1 to 250K gamers, each have their own score. Their score can change anytime and we're asked to output player X's rank at any given time. score can range between 0 to 1 million. we can just use player index as player id, so player id will range from 0 to 249,999.  
Input will consist of (there will be less than 200K lines of input) :  
3 -> first line indicates how many players there are, this will be followed by 3 lines of initial score  
150 -> player 0's initial score  
20 -> player 1's initial score  
2100 -> player 2's score, next lines will be commands, starting with either G or U. G for querying player X's current rank, U for updating player X's score, affecting the whole player ranking  
G 1 -> player 1's rank is dead last with measly score 20, so, output 3  
G 0 -> player 0's score is currently 150, rank is 2, so, output is 2  
U 1 200 -> player 1's score is now 200, changing his rank to 2  
G 1 -> player 1's rank is now 2, output 2  
G 0 -> player 0's is now dead last with score 150, output 3  
and so on...

答案: 线段树的节点表示分数区间内的人数

---------

[Microsoft | SDE2](https://leetcode.com/discuss/interview-question/2256409/Microsoft-or-SDE2)

Basically design a data structure that supports interval insertion and querying to check if an int lies withing any of the interval

Ex  
Insert (1,5)  
Insert (8,9)

IsPresent(4) -> True  
IsPresent(8) -> Treu  
IsPresent(0) -> False

-------------

[Microsoft | SDE 1 | USA](https://leetcode.com/discuss/interview-question/2095242/Microsoft-or-SDE-1-or-USA)

A working day consists of hours 8am - 5pm with one hour lunch break from 12-1pm.

Given the meetings : [[9,10], [4,5]]

1.  Can the person attend all meetings in the day?
2.  Return the total hrs he is working (no meetings)?

如果数据范围不是只有9h的话 就需要线段树了

---------

[Please help with this question -> intervals.](https://leetcode.com/discuss/interview-question/2679436/Please-help-with-this-question-greater-intervals.)

Given an array containing ranges, determine in how many ranges a point given in the points array lies  
ranges = [[1,4],[4,5],[6,10],[8,20],[1,6]]  
points = [1,4,5,7,8,19,20]  
I need to output an array of length same as len(points) where output[i] represents the total ranges in which a point at ith index in points lies.  
I could not think of an optimal solution to solve this.

区间修改 使用lazy tag 单体查询

-----

[Trilogy OA Question](https://leetcode.com/discuss/interview-question/2656082/Trilogy-OA-Question)

![image](https://assets.leetcode.com/users/images/6008be3a-fe7d-4b77-8a21-92b1d006908a_1664811498.278922.png)

这里的第二种操作可以是任意长度的区间

线段🌲节点维护 1.是否翻转 2.不翻转的值 3.翻转的值
对于翻转操作 更改1
对于乘值操作 如果当前是不翻转 那么就加到2中 如果当前是翻转 那么就加到3中
对于push down操作 1是否翻转直接操作就行 对于23操作需要看下一层的1 如果下一层的1是翻转 那么当前层的2就加到下一层的3 当前层的3就加到下一层的2

--------

[UBER OA Question GOOD Question](https://leetcode.com/discuss/interview-question/2706260/UBER-OA-Question-GOOD-Question)

Given a integer K, and string S. Now we have can pick some indexes from the given string in such a way that for every K size substring there should be at least one index from our Picked Indexes.  
Now using the indexes we picked form a lexicographically smallest string from the given string.

Iam stuck in implementing this. can someone help me>?

Example :  
K = 4  
S = aacaa  
output = a

K=2  
S = abcab  
output = aab (after reordering)

线段🌲 区间覆盖 字母从小到大开始覆盖 直到区间被全部覆盖即可

-----

[Zomato OA, pls help](https://leetcode.com/discuss/interview-question/2731592/Zomato-OA-pls-help)

For a number N we have N! unique permutations. A permutation is a sequence of integers from 1 to N of length N containing each number exactly once.  
For a positive integer X, X! = 1 * 2 * 3  _..._  X-1 * X  
Your task is to find the Kth smallest permutation when all possible permutations of size N are arranged in sorted order.  
Input  
Input contains only two integers, the value of N and K.

# Constraints:-

1 <= N <= 10000  
1 <= K <= min(N!,100000000)

Output

Print the Kth permutation in form of a string. i. e don't print spaces between two numbers.

Example

Sample Input:-  
3 5

Sample Output:-  
312

Explanation:-

All permutations of length 3 are:-  
123  
132  
213  
231  
312  
321

Sample Input:-

11 2

Sample Output:-

1234567891110

------



<!--stackedit_data:
eyJoaXN0b3J5IjpbMjk2Mjc0ODQ2LC01MTU5MTQ4NDMsMTI1NT
Q0MDkyNCwtMTMwMTYwNjQ0NSwyMDQxNjMxNTM4LDcxMDUxMDM2
OCwtMTc3NjA2Mjk3MV19
-->