#### [834. Sum of Distances in Tree](https://leetcode.cn/problems/sum-of-distances-in-tree/)
寻找相邻两个节点之间的关系 预处理出所有节点构成的子树的节点数量 并且可以直接求得根节点到其他所有节点的距离作为dp的起始

#### [2313. Minimum Flips in Binary Tree to Get Result](https://leetcode.cn/problems/minimum-flips-in-binary-tree-to-get-result/)
简单明了

#### [1928. Minimum Cost to Reach Destination in Time](https://leetcode.cn/problems/minimum-cost-to-reach-destination-in-time/)
题目中时间和节点数边数都有 10^3 限制
定义dp[i][j] 恰好经过时间i 从0到n-1所需要的最小代价
因为时间一定是递增的所以可以dp 并且时间放在外层 
仔细思考其实最优解就是答案 最优解一定包含在所有的情况中 即使有些情况是illegal的 比如 终点是target 还有另外一个节点x 从起点到x的最小代价可能经过target 这个时候更新target的某个时间的最小代价时 可能会包括这种情况 变成从起点到targe到x再到target 但是这种情况一定不会是最优解 因为直接从起点到target的代价一定更小 区别就是他们所需要的时间不一样
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTQ5MzA0MDUyNl19
-->