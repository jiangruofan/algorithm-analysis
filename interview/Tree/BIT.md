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




<!--stackedit_data:
eyJoaXN0b3J5IjpbMTcyMTQ5NjcyMF19
-->