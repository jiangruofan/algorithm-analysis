割点判定法则:
若u 不是搜索树的根节点，若u节点是割点，那么当且仅当搜索树上存在u的一个儿子节点v，满足: low[v] >= level[u] ; 若u是根节点, 那么u至少有2个儿子节点
割边判定法则: 若u节点是割点，那么当且仅当搜索树上存在u的一个儿子节点v，满足: low[v] > level[u]
-----------
#### [1568. Minimum Number of Days to Disconnect Island](https://leetcode.cn/problems/minimum-number-of-days-to-disconnect-island/)
如果陆地已经分离 return 0
如果只有一块陆地，陆地不存在割点 return 2 存在割点 return 1

#### [1192. Critical Connections in a Network](https://leetcode.cn/problems/critical-connections-in-a-network/)
简单求割边
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE2MDQyNzY5MDddfQ==
-->