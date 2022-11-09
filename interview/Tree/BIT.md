[Google | 🌳 TreapOnsite](https://leetcode.com/discuss/interview-question/3639451521932/Google-or-Treap)

A binary tree has the binary search tree property (BST property) if, for every node, the keys in its left subtree are smaller than its own key, and the keys in its right subtree are larger than its own key. It has the heap property if, for every node, the keys of its children are all smaller than its own key. You are given a set of binary tree nodes  `(i, j)`  where each node contains an integer  `i`  and an integer  `j`. No two  `i`  values are equal and no two  `j`  values are equal. We must assemble the nodes into a single binary tree where the  `i`  values obey the BST property and the  `j`  values obey the heap property. If you pay attention only to the second key in each node, the tree looks like a heap, and if you pay attention only to the first key in each node, it looks like a binary search tree.

**Example 1:**

```
Input: [(1, 6), (3, 7), (2, 4)]
Output:

		(3, 7)
		/
	 (1, 6)
		\
	  (2, 4)

```

**Example 2:**

```
Input: [(1, 4), (8, 5), (3, 6), (10, -1), (4, 7)]
Output:

		(4, 7)
		/    \
	(3, 6)   (8, 5)
	 /          \
 (1, 4)       (10, -1)

```

You can assume that a solution always exists.

每个节点为(x, y)
先按照x升序排列 然后就是根据y寻找区间的最大值 左边的节点构成左子树 右边的节点够成右子树 然后递归 寻找区间的最大值可以刚开始构建y的树状数组 然后可以在logn内查询

构建树状数组需要nlogn 构建二叉树需要lognlogn 所以总体时间复杂度还是nlognOnsite)

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

---------------

[OA | Can someone please help with this question?](https://leetcode.com/discuss/interview-question/2152237/OA-or-Can-someone-please-help-with-this-question)

Three new health care buildings are to be built in HackerLand. They will be built on land with  
plots numbered consecutively starting from 1. There are two integer arrays starting, ending,  
each offize n, that represent= n intervals where the ith interval is [starting[i], ending[i]].  
Determine the number of ways three non-overlapping intervals can be selected from the n  
intervals.  
Note:  
• An interval is defined as [l, r] where it contains every integer between l to r.  
• Two intervals [l[1[, r[1]] and [l[2], r[2]] overlap if there is an integer that is contained in both of  
them. For example, [2, 5], [3, 8] overlap because 3, 4, 5, are common to both, whereas [1, 5], [8,  
9] do non-overlapping.  
• Interval sets must be distinct. At least one interval must be different for two sets to be  
distinct. For example, interval sets [[1, 2], [3, 4]] and [[3, 4], [1, 21]] share the same intervals in a  
different order, so they are not distinct.  
Example  
n= 5  
starting = [1, 2, 4, 3, 7]  
ending = [3, 4, 6, 5, 8]

Expected output: 1  
There are 5 intervals [1, 3], [2, 4], [4, 6], [3, 5], [7,8]. They are shown as line segments 1 through  
5.  
There is only one way to select three non-overlapping intervals, lines 1, 3, and 5 with ranges  
[1, 3], [4,6], [7, 8]].  
Note that we cannot select lines 1, 4 and 5 with ranges [[1, 3], [3, 5], [7, 8]] because [1, 3] and [3,5] overlap at 3.  
Function Description  
Complete the function: getThreeNonOverlappingIntervals in the editorbelow.  
getThreeNonOverlappingintervals has the following parameter(s):  
int starting[n]: the left endpoints of the intervals  
int ending[n]: the right endpoints of the intervals  
Returns: long : number of ways of selecting three non overlapping intervals

Constraints : 1<n<10^5  
|starting|, |ending| = n  
1<= starting[i], ending[i]< 10^9

Example 2:  
n= 4  
starting = [5,2,3,7]  
ending = [7,2,4,8]  
Output : 2

Example 2:  
n= 4  
starting = [1,2,3,4]  
ending = [1,2,3,4]  
Output : 4

注意这里二分是不对的 因为没法保证r一定小于当前选择中间点的l

-------

[OA question || Need help](https://leetcode.com/discuss/interview-question/2674009/OA-question-oror-Need-help)

_**Given a graph with n nodes having bidirectional edges. Given two array A and B of length n-1 , where [i] and B[i] have an edge between them. The nodes are 1 indexed. Also, 1 is the root node . Every node has an jealousy value attached with it. Jealously value is the number of nodes greater than the parent node in the subtree.  
Find the sum of jealousy value of all nodes.**_

Sample Input:  
A : 1 6 4 2 7 3  
B: 5 1 5 5 4 6

Sample Output:  
8

Explanation:  
Node 1 has jealousy value: 6 (nodes - 2,3,4,5,6,7) ,  
Node 5 has jealously value 1 (node - 7) and  
Node 4 also has jealousy value 1 ( node - 7)

ans = 6+1+1 = 8

答案: 维护一个树状数组即可 dfs一次 求有多少个元素小于当前节点值 加入答案

-----

[Uber On-Site Interview](https://leetcode.com/discuss/interview-question/2730415/Uber-On-Site-Interview)

```
Given an array of people, each person will only go somewhere if there are atleast x other people and at most y other people. Figure out the max number of people that can go in at one time.
Sample input: 5, [[0,1], [1,3], [0,2], [1,4], [3,5]]
Output: 3
Explination:
  person 0 can go alone and with one other person
  person 1 can go if there's atleast 1 other person and at most 3 other people
  person 2 can go alone and at most 2 other people
  person 3 can go if there's atleast 1 other person and at most 4 other people
  person 4 can go if there's atleast 3 other person and at most 5 other people
So the group can be person 1, person 2, and person 3. Can't add more people to this because person 2 won't go with more than 2 people.
```

对x按照从小到大排序 二分答案 给定人数 判断是否可行 人数必须大于最大的x并且小于最小的y 那么把所有符合条件的x的y放入bit 然后判断大于等于人数的y是否多于人数 如果多于那么就满足条件 时间复杂度是 nlogn

-----

[Media.net interview question](https://leetcode.com/discuss/interview-question/1069588/Media.net-interview-question)

Given a permutation of numbers from 1 to n, count the number of quadrapules indices (i,j,k,l) such that i<j<k<l and A[i]<A[k]<A[j]<A[l].

I was not able to improve on the time complexity compared to the brute force solution. How to solve this? Can some precomputation be used? It would also be great if someone can suggest similar problems for practice.

Example:  
[1,3,2,6,5,4]  
first 4 indices satisfy the given condition.

遍历k和j 时间复杂度是O(n^2logn)

---
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEwMDkxMjk0OTEsLTk3MjcwNzgwNSw0MT
kzMDAzNzEsNTUxNTc5MzI1LDE3MjE0OTY3MjBdfQ==
-->