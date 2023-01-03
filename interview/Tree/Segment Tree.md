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

Constraints:

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

[Sprinklr | OA | Platform Support Engineer | 2022](https://leetcode.com/discuss/interview-question/2743662/Sprinklr-or-OA-or-Platform-Support-Engineer-or-2022)

![image](https://assets.leetcode.com/users/images/7c9cc467-b0c2-4641-b75b-5043df664f1c_1666720741.0871403.png)
![image](https://assets.leetcode.com/users/images/667d5ff9-313f-4c9f-825d-734479335a58_1666720741.0422642.png)
![image](https://assets.leetcode.com/users/images/8f35c9d3-394d-4fe3-b461-f465b37678f4_1666720741.0380628.png)

单体修改 查询的话两种方法 1. 区间查询 + 二分(二分位置然后区间查询判断数量)
2. 直接区间查询计算
这题可以不用离散化

-----

oppo oa

[HiLabs || SDE || OA 2022](https://leetcode.com/discuss/interview-question/2829632/HiLabs-oror-SDE-oror-OA-2022)

![image](https://assets.leetcode.com/users/images/b8daaf21-a7cb-480e-a45d-a1c1ee4331be_1668849091.2575836.png)

given a string，求出每一个prefix的最长子回文串 string的长度为1e5
使用马拉车算法 然后线段🌲更新区间最大值 最后计算每一个prefix的最大值
时间复杂度是 nlogn

---

[Mathworks|EDG intern|Street play in Hakerland](https://leetcode.com/discuss/interview-question/2779541/MathworksorEDG-internorStreet-play-in-Hakerland)

![image](https://assets.leetcode.com/users/images/51619bfb-0536-441f-a455-05ce18a4b169_1667599339.5748856.jpeg)
![image](https://assets.leetcode.com/users/images/39a8b51b-b6ce-40fb-9e67-e55522561538_1667599346.4165883.jpeg)

区间覆盖问题

----

[Media.net Online Test (OT) 2022 for Placement](https://leetcode.com/discuss/interview-question/2714772/Media.net-Online-Test-%28OT%29-2022-for-Placement)

![image](https://assets.leetcode.com/users/images/401b61a7-1d5a-4001-b529-f18e2c47cd3d_1666020311.455571.jpeg)

dp + 线段🌲 区间修改 单体查询

---

[Uber Interview Question](https://leetcode.com/discuss/interview-question/2793077/Uber-Interview-Question)

Recently I interviewed at UBER and it was a Datastructures and algorihtms round.

The question was as follow:

Givent a infinite stream of events and events are like:

user1 city1 BOOKED timestamp1  
user2 city1 CANCELLED timestamp2  
user3 city1 BOOKED timestamp3  
user4 city1 BOOKED timestamp4  
user1 city2 ENDED timestamp5

On these events we have to build a system where query can be anything like

1.  How many cabs are BOOKED between timestamp1 to timestamp4.
2.  How many cabse are BOOKED in city1 and ended in city2 between timestamp1 to timestamp4.

Expectation of this round was to build some generic datastructure that can support query of anytype.

Expectation1- How we are going to ingest these events, since its a DS/ALGO round so a in memory datastructure was expected.  
Expectation2- Support any types of query.

Can anyone help me in understanding what is the expected solution for this problem?

**NOTES: Event may not be in sorted order by timestamp. a event with timestamp ts1 can come at time ts3.**

题目不是很清楚

---

[SNOWFLAKE ONLINE TEST / VERY VERY HARD/](https://leetcode.com/discuss/interview-question/2838177/SNOWFLAKE-ONLINE-TEST-VERY-VERY-HARD)

![image](https://assets.leetcode.com/users/images/55ebba5c-b0dd-4e89-9cf7-c05c17fd615e_1669096089.0370595.png)
![image](https://assets.leetcode.com/users/images/bbdd6d2b-51ca-4f8f-b25c-5dede964066d_1669096102.8905518.png)
![image](https://assets.leetcode.com/users/images/1724b159-f477-44d5-bb10-fda92a2eda7c_1669096129.0778818.png)
![image](https://assets.leetcode.com/users/images/cb4aa11c-5478-4fc1-b505-5a18389dfe2d_1669096149.2286146.png)
![image](https://assets.leetcode.com/users/images/a610905f-35d9-4a40-8590-963bc1f18389_1669096159.5293403.png)

这里的核心是有这个mod 那么使用前缀和即可 
单体修改 区间查询    
。。。。。。。。val。。。。。。。 (val表示ith前缀和)
需要判断k是否小于或者大于val 

----

During my last interview at UBER, I was asked about data structures and algorithms.

I was asked the following question:

If there is an infinite stream of events and the events are as follows:

user1 city1 BOOKED timestamp1
user2 city1 CANCELLED timestamp2
user3 city1 BOOKED timestamp3
user4 city1 BOOKED timestamp4
user1 city2 ENDED timestamp5

On these events we have to build a system where query can be anything like

How many cabs are BOOKED between timestamp1 to timestamp4.
How many cabse are BOOKED in city1 and ended in city2 between timestamp1 to timestamp4.
Expectation of this round was to build some generic datastructure that can support query of anytype.

Expectation1- How we are going to ingest these events, since its a DS/ALGO round so a in memory datastructure was expected.
Expectation2- Support any types of query.

Would anyone be able to help me understand what the expected solution is?

对于第一个问题 可以使用线段🌲
第二个问题 hashmap即可 key用一个四个维度的元组

---

[JIO OA Problem](https://leetcode.com/discuss/interview-question/2961276/JIO-OA-Problem)

**I don't have the exact question screenshot since the test was on SHL and SHL tracks everything, therefore, I did not try to take a screenshot.**  
We were given **N** coordinates of the form **(X, Y)** where X is the x-coordinate and Y is the y-coordinate of the location. There are **Q queries** of three types and their first element represents the type of query.  
For Ex: 1 2 4. means query of type-1.  
**Type1**: Type-1 is of the form: (type, lower_range_of_x, upper_range_of_x). We have to find the output of the minimum distance possible from all the coordinates satisfying the above range criteria.  
**Type2**: Type-2 is of the form: (type, lower_range_of_y, upper_range_of_y). We also have to find the output of the minimum distance possible from all the coordinates lying in the range.  
**Type3**: Type-3 is of the form: (type, lower_range_of_x, upper_range_of_x, lower_range_of_y, upper_range_of_y). We also have to find the output of the minimum distance possible satisfying the above range criteria for both x and y coordinates.  
**We have to return a vector which contains the answers of the queries.**  
**I tried to solve it using segment trees, but I am not sure how to do that. Do we need to create multiple segment trees?  
In JIO's OA, we were given two questions in 45 mintues and another one was medium, however, the problem statements were huge, thus making it difficult to understand quickly.**

type1 type2 可以优化到n^2logn 对于type3 没法处理
对x和y分别排序 然后对于每一个点构造线段🌲 每次查询遍历区间内所有点 然后logn求出这个点到其他点的最小值是多少 最后取所有点的最小值

----
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTg4NTA3Njk2NiwyMDg2NTI5NzI5LDE2MT
EwMjAzNTcsMTI2Njg3NzY2MiwtNzgwODIwNTAxLDExMjQzMjcy
ODksMTkyODI4MDAyOSwxODM0NDIxNTQ3LDIxNDEwNzk5NTcsMT
IxOTYzNjQxMCwtMTkwODQ3OTcwLDEzNTg0MjA5NDQsLTk5OTA1
Mjg5NiwxNjA0MDUyODk3LC04MDAzMzQ2Nyw5MDcwMjUwNjYsMj
k2Mjc0ODQ2LC01MTU5MTQ4NDMsMTI1NTQ0MDkyNCwtMTMwMTYw
NjQ0NV19
-->