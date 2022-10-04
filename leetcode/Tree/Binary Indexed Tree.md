取x最低位的1 : x & (-x)
最后一位不断减1 得到的是小于等于当前val的一个一个区间 
最后一位不断加1 得到的是所有包含当前元素的区间

--------------------
#### [2179. Count Good Triplets in an Array](https://leetcode.cn/problems/count-good-triplets-in-an-array/)
首先进行映射 我们得到nums1中的每个数字在nums2中对应的位置 然后在nums1上遍历y 假设当前位于 i 位置(考虑nums2) 我们需要知道i前面有多少个元素 这些元素就是左半部分的答案 然后需要知道i后面的元素 注意这些元素应该是 n-i-sum(i-n)

#### [1649. Create Sorted Array through Instructions](https://leetcode.cn/problems/create-sorted-array-through-instructions/)
离散化+树状数组

#### [1847. Closest Room](https://leetcode.cn/problems/closest-room/)
在线做法 树状数组维护的不再是前缀和 而是 房间大小大于等于某个值的全部房间id 
假设房间最大大小为30  当前房间大小为10 那么 需要让房间大小为1到10的节点插入当前房间id 对应在树状数组上就是20到30
如果是查询房间大小大于等于10的全部房间id 那么对应树状数组上就是1-21
对于前缀和的树状数组 增加操作是对当前节点后面的节点产生影响 
求区间和操作是求当前节点前面的节点
对于本题的树状数组 增加操作和查询操作和前缀和的树状数组的增加操作和查询操作吻合
自己写的也可以好理解 更好 
查询时间复杂度应该是 log(maxRoomSize) * log(roomNumber)

#### [308. Range Sum Query 2D - Mutable](https://leetcode.cn/problems/range-sum-query-2d-mutable/)
把二维变成一维 

1585的codeforce原题需要使用树状数组
假设树状数组为 [0, y]
要求: 对于一个index为i的值 更新i i+1 .. y 的值为一个最大值 并且可以求得某一个index的值
操作: 对于update操作 使用最后一位+1 对于query操作 使用最后一位减1 看那张图模拟 很清楚
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTk4NjI0MDBdfQ==
-->