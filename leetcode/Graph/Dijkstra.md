#### [2203. Minimum Weighted Subgraph With the Required Paths](https://leetcode.cn/problems/minimum-weighted-subgraph-with-the-required-paths/)
枚举中心点 需要用一个反图求中心点到终点的最短距离

#### [778. Swim in Rising Water](https://leetcode.cn/problems/swim-in-rising-water/)
不是标准dijkstra 但是也可以变成dijkstra 类似1631
题目转换成 求一条从起点到终点的路径并且这条路径上的最大值点最小
可以用一个heap 每次取出最小值 直到终点 记录这个过程中的最大值就是答案

#### [1631. Path With Minimum Effort](https://leetcode.cn/problems/path-with-minimum-effort/)
题目转换成 求一条从起点到终点的路径并且这条路径上的两两元素之差的绝对值的最大值最小
这里起点到另一个点的距离就是 这条路径上两两元素差值的绝对值的最大值

#### [499. The Maze III](https://leetcode.cn/problems/the-maze-iii/)
注意这里的距离需要自己求

#### [882. Reachable Nodes In Subdivided Graph](https://leetcode.cn/problems/reachable-nodes-in-subdivided-graph/)
先求出到每个节点的最短路径是多少 然后遍历一遍edges 求出每条edge中间有多少个节点可以访问到
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE1ODMzMjk1NDhdfQ==
-->