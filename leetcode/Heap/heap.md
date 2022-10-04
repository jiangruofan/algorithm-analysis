#### [2163. Minimum Difference in Sums After Removal of Elements](https://leetcode.cn/problems/minimum-difference-in-sums-after-removal-of-elements/)
将数组分成左右两部分 每部分长度为n 要使suml - sumr最小 那么就要suml越小 sumr越大 我们可以枚举两部分的中间分界点 等价于求左边的n个数的和最小 右边的n个数的和最大 维持长度为n的heap 

#### [23. Merge k Sorted Lists](https://leetcode.cn/problems/merge-k-sorted-lists/)
维持一个heap 每次取出最小值

#### [632. Smallest Range Covering Elements from K Lists](https://leetcode.cn/problems/smallest-range-covering-elements-from-k-lists/)
维护一个heap保持最小值 然后再维护一个最大值 每次取出最小值推进一个 

#### [295. Find Median from Data Stream](https://leetcode.cn/problems/find-median-from-data-stream/)
维护一个大根堆 一个小根堆 维护他们的长度差不大于1

#### [407. Trapping Rain Water II](https://leetcode.cn/problems/trapping-rain-water-ii/)
木桶原理

#### [2242. Maximum Score of a Node Sequence](https://leetcode.cn/problems/maximum-score-of-a-node-sequence/)
题目要求连续3条边连接的4个点的最大值是多少 那么可以固定中间那条边 然后让另外两条边值最大 在预处理每个节点的连接的节点的最大值时 只需要保存3个节点 因为与x 相邻的点中，由于只需要与 y 和 b 不一样，我们仅需要保留分数最大的三个点，a 必定在这三个点中。
类似粉刷房子

#### [358. Rearrange String k Distance Apart](https://leetcode.cn/problems/rearrange-string-k-distance-apart/)
先用cnt计数 每次取数量最多的k个数加入答案 如果数目不足k 那么所有元素只能有1个 

#### [1606. Find Servers That Handled Most Number of Requests](https://leetcode.cn/problems/find-servers-that-handled-most-number-of-requests/)
使用2个heap 一个heap保存busy服务器结束的时间 还有一个heap保存空间服务器的id  遍历arrival 每当取出一个busy服务器时 加入空闲服务器 加入的时候加入一个比当前i大且和服务器id同余的数 这样可以保证在i前面的服务器的id一定是排在在i后面的服务器的id后面

#### [1354. Construct Target Array With Multiple Sums](https://leetcode.cn/problems/construct-target-array-with-multiple-sums/)
思想和780一样 

#### [2102. Sequentially Ordinal Rank Tracker](https://leetcode.cn/problems/sequentially-ordinal-rank-tracker/)
这里需要使用自定义比较器 因为字符串的大小比较不能像数字一样前面加一个负号解决 

#### [1388. Pizza With 3n Slices](https://leetcode.cn/problems/pizza-with-3n-slices/)
标准做法是dp 类似打家劫舍
题目的意思可以转换成 选取n个不相邻的数字使得和最大 
自然而然想到贪心思想 每次选取最大的数字 但是可能出现一种特殊情况是选择当前最大数字的左右两个数字 所以我们需要设置一个反悔机制

#### [6170. Meeting Rooms III](https://leetcode.cn/problems/meeting-rooms-iii/)
简单模拟 
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTQ2MTQ1MzAyMl19
-->