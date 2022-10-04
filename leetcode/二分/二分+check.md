#### [644. Maximum Average Subarray II](https://leetcode.cn/problems/maximum-average-subarray-ii/)
1.二分答案
2.数组每个数减去平均值，转换为 是否存在一个长度不小于k的子数组的和>=0. 两种做法 1. 维持一个数组sum大于等于0的数组 当长度等于k 说明存在 如果这个数组sum小于0， 那么从下一个数重新开始一个新的子数组 2. 保存每一段前缀和，维持i-k的最小前缀和(prefix)，当当前i的前缀和-prefix大于0，则存在

#### [719. Find K-th Smallest Pair Distance](https://leetcode.cn/problems/find-k-th-smallest-pair-distance/)
求第k小的距离 先对数组排个序 如果给定一个距离dist 可以在n时间内判断出有多少对元素的距离小于等于dist 如果元素的个数小于k 说明需要增大dist 如果元素的个数大于k 说明需要减小dist

#### [410. Split Array Largest Sum](https://leetcode.cn/problems/split-array-largest-sum/)
求把数组分成m个子数组 要使子数组的最大值最小
假设给定一个子数组的最大值为k 看能分成多少个子数组 如果子数组的数量大于m 那就让子数组的最大值变大点 反之变小点 

#### [1231. Divide Chocolate](https://leetcode.cn/problems/divide-chocolate/)
求把数组分成k个子区间 要求子区间的最小值最大 
给定一个最小值的最大值 看能把区间分成多少份 如果份数大于k 说明最小值的最大值可以再大点 反之小点

#### [2258. Escape the Spreading Fire](https://leetcode.cn/problems/escape-the-spreading-fire/)
注意这里的火每次都是使用传播出去的火进行拓展 减少时间复杂度

#### [1439. Find the Kth Smallest Sum of a Matrix With Sorted Rows](https://leetcode.cn/problems/find-the-kth-smallest-sum-of-a-matrix-with-sorted-rows/)
这里的dfs有点特殊多看
要求第k小的和是多少 假设给定一个和 看有多少个组合符合条件 如果大于k 那么就让和小一点 如果小于k 那么就让和大一点 

#### [2071. Maximum Number of Tasks You Can Assign](https://leetcode.cn/problems/maximum-number-of-tasks-you-can-assign/)
单调队列优化 对于n个工作和n个工人 先进行从小到大排序 要让这n个工人做n个工作 那么让第一个工人最第一个工作 如果可以 那么ok 如果不行 那么就让这个工人吃药 然后看能做的工作最大是多少 维护一个单调递增队列 因为工人吃药后能做的工作一定是递增的

#### [2040. Kth Smallest Product of Two Sorted Arrays](https://leetcode.cn/problems/kth-smallest-product-of-two-sorted-arrays/)
假如给定了一个 limit 求有多少个元素小于等于limit 
nums[i] * nums[j] <= limit 遍历i 二分找到j
1. nums[i] > 0  那么 nums[j] <= limit / nums[i]
2. nums[i] = 0 那么 如果limit >= 0 所有的j都可以
3. nums[i] < 0 那么 nums[j] >= limit / nums[i]
时间复杂度是O(n logn logn)

#### [1723. Find Minimum Time to Finish All Jobs](https://leetcode.cn/problems/find-minimum-time-to-finish-all-jobs/)
一遍写对 简洁明了

#### [774. Minimize Max Distance to Gas Station](https://leetcode.cn/problems/minimize-max-distance-to-gas-station/)
简单明了

#### [668. Kth Smallest Number in Multiplication Table](https://leetcode.cn/problems/kth-smallest-number-in-multiplication-table/)
这里很神奇的是如果等号去掉 二分那里换另一种写法 就过不了 

[2398. Maximum Number of Robots Within Budget](https://leetcode.com/problems/maximum-number-of-robots-within-budget/)
不是最优解 最优解是滑动窗口


-----------------------------------------------------------

#### [302. Smallest Rectangle Enclosing Black Pixels](https://leetcode.cn/problems/smallest-rectangle-enclosing-black-pixels/)

由于题目给了一个黑色的点(x, y) 所以用这个点进行二分 例如我们确定left和right 可以对 x的左边和右边进行二分 top和bottom一样 最终时间复杂度应该是 mlogn + nlogm

#### [4. Median of Two Sorted Arrays](https://leetcode.cn/problems/median-of-two-sorted-arrays/)
考虑好边界
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTk4ODUyODA3OSw3MzA5OTgxMTZdfQ==
-->