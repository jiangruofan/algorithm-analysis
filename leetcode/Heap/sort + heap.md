#### [502. IPO](https://leetcode.cn/problems/ipo/)
简洁明了

#### [630. Course Schedule III](https://leetcode.cn/problems/course-schedule-iii/)
首先肯定的是 截止日期早结束的先完成 所以先排序 对于当前这门课程 如果能完成 那么res+1 如果不能完成 那我们就把之前(包括当前)所有课程中耗时最长的那门课踢掉 总课程数目不变

#### [871. Minimum Number of Refueling Stops](https://leetcode.cn/problems/minimum-number-of-refueling-stops/)
已经sort好了 我们看当前的油能够开的最远是多少 如果最远不能到达终点 那就选择可以加油的加油站里面油最多的加

#### [857. Minimum Cost to Hire K Workers](https://leetcode.cn/problems/minimum-cost-to-hire-k-workers/)
根据给定的要求 我们可以得出:
earned[i] / quality[i] = unit for i in range(k)
earned[i] >= wage[i] -> unit >= wage[i] / quality[i] for i in range(k)
所以我们对wage[i] / quality[i]从小到大排序 然后对于第i个人 需要从前面找k-1个人 那么找的这k-1个人的quality最小就是最优解

#### [1383. Maximum Performance of a Team](https://leetcode.cn/problems/maximum-performance-of-a-team/)
倒叙遍历 确定了一个efficiency后 求k个最大的speed的和 
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTc1NDc2NzE1OV19
-->