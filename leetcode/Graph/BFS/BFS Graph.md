#### [1036. Escape a Large Maze](https://leetcode.cn/problems/escape-a-large-maze/)
假设有n个block
注意数据范围，我们只需要思考如何把起点或者终点围起来即可，最优的方法围起来就是借助grid自身提供两条边，block组成一条斜边围起来，要突破的步数为 1 + 2 +  .... + (n-1)  = n * (n - 1) / 2

#### [317. Shortest Distance from All Buildings](https://leetcode.cn/problems/shortest-distance-from-all-buildings/)
没啥技巧 暴力遍历 用一个cnt数组记录不同building来的 然后取最小值

#### [2045. Second Minimum Time to Reach Destination](https://leetcode.cn/problems/second-minimum-time-to-reach-destination/)
先求到终点的第二最短距离 然后再计算时间 时间计算通过当前的时间t在不在红灯时间内 看红灯时间可以通过总时间/change 如果是偶数说明绿灯 奇数说明红灯

#### [815. Bus Routes](https://leetcode.cn/problems/bus-routes/)
首先记录在每个车站有多少种公交车可以乘坐 然后进行bfs 从当前车站看可以坐哪些车 坐过的车不坐 然后看车能到哪些车站 到过的车站不用重新到了 因为距离肯定更远

#### [913. Cat and Mouse](https://leetcode.cn/problems/cat-and-mous/)
#### [1728. Cat and Mouse II](https://leetcode.cn/problems/cat-and-mouse-ii/)
从终点状态递推回去 例如当前是猫赢 1.猫的回合 那么说明上一个回合是老鼠 这个时候需要看老鼠上一回合的位置 如果这个位置下老鼠行动一步都是猫赢 那么这个位置也就是猫赢 2. 老鼠的回合 说明上一个回合是猫走 因为当前是猫赢 那么猫必然会选择走到当前位置 所以猫的上一步状态都是猫赢

#### [1293. Shortest Path in a Grid with Obstacles Elimination](https://leetcode.cn/problems/shortest-path-in-a-grid-with-obstacles-elimination/)
每一步状态除了坐标x,y 加一个维度障碍数

#### [847. Shortest Path Visiting All Nodes](https://leetcode.cn/problems/shortest-path-visiting-all-nodes/)
状态压缩 把所有节点都当成起点进行bfs 

#### [2092. Find All People With Secret](https://leetcode.cn/problems/find-all-people-with-secret/)
时刻肯定先排序 然后就是求给定某一时刻和这一个时刻下有多少对人在开会 其中某些人知道秘密 知道秘密的人可以把秘密传播给别人 联想到建图 然后从知道秘密的人开始bfs

#### [1284. Minimum Number of Flips to Convert Binary Matrix to Zero Matrix](https://leetcode.cn/problems/minimum-number-of-flips-to-convert-binary-matrix-to-zero-matrix/)
注意把二维矩阵压缩成一维

#### [864. Shortest Path to Get All Keys](https://leetcode.cn/problems/shortest-path-to-get-all-keys/)
感觉可以不用位运算来记录钥匙

#### [675. Cut Off Trees for Golf Event](https://leetcode.cn/problems/cut-off-trees-for-golf-event/)
题目要求砍树并且树的高度只能是递增的 所以我们可以先把所有树的高度从小到大排序 然后用bfs求解从一个矮的树到一个高的树的距离 最后加起来就是答案

#### [1617. Count Subtrees With Max Distance Between Cities](https://leetcode.cn/problems/count-subtrees-with-max-distance-between-cities/)
先用二进制压缩 然后求树的直径 
树的直径用两次bfs

#### [1956. Minimum Time For K Virus Variants to Spread](https://leetcode.cn/problems/minimum-time-for-k-virus-variants-to-spread/)
标准BFS 可能存在更优解 

#### [1210. Minimum Moves to Reach Target with Rotations](https://leetcode.cn/problems/minimum-moves-to-reach-target-with-rotations/)
一遍写对 简单明了
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE3ODM1OTA0NzddfQ==
-->