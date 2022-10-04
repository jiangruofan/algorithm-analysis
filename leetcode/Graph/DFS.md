#### [1377. Frog Position After T Seconds](https://leetcode.cn/problems/frog-position-after-t-seconds/)
注意青蛙如果t秒了跳到一个节点 但是它还能继续跳 那它会继续跳不会停在那里

#### [827. Making A Large Island](https://leetcode.cn/problems/making-a-large-island/)
对于所有的岛屿求出大小 并且对每个岛屿里面的元素进行标记 然后再遍历所有的0 如果附近4个方向存在岛屿那么就连接起来 注意4个方向的岛屿可能存在重复 用set去重一下

#### [124. Binary Tree Maximum Path Sum](https://leetcode.cn/problems/binary-tree-maximum-path-sum/)
把每个节点看作是根节点 然后求以当前节点能够构成的最长路径是多少 取最大值即可

#### [2246. Longest Path With Different Adjacent Characters](https://leetcode.cn/problems/longest-path-with-different-adjacent-characters/)
其实就是求以每个节点为根节点能够形成的最长路径是多少 类似124

#### [987. Vertical Order Traversal of a Binary Tree](https://leetcode.cn/problems/vertical-order-traversal-of-a-binary-tree/)
用hashmap记录 最后排序即可

#### [968. Binary Tree Cameras](https://leetcode.cn/problems/binary-tree-cameras/)
对于一个节点 定义三个状态 0看不到 1看得到 2安装了摄像头
对于一个节点 如果两个子节点有一个为0 那么就安装摄像头 如果两个子节点有一个是2 那么当前节点就是1 如果两个子节点都为1 那么当前节点为0 注意一下根节点的处理

#### [425. Word Squares](https://leetcode.cn/problems/word-squares/)
用哈希表保存每个单词每个前缀 然后dfs进行匹配

#### [2065. Maximum Path Quality of a Graph](https://leetcode.cn/problems/maximum-path-quality-of-a-graph/)
注意这里的去重

#### [1766. Tree of Coprimes](https://leetcode.cn/problems/tree-of-coprimes/)
题目要求每个节点最近的祖先节点并且这个祖先节点满足和当前节点互质 由于节点的值很小 所以可以预处理 把所有值的可能的互质数都保存起来 然后dfs遍历 

#### [996. Number of Squareful Arrays](https://leetcode.cn/problems/number-of-squareful-arrays/)
本质就是求所有的排列 并且每个排列两两元素和必须是一个平方数
求全排列的去重 如果前面一个元素没有访问过 那么当前元素跳过

#### [1373. Maximum Sum BST in Binary Tree](https://leetcode.cn/problems/maximum-sum-bst-in-binary-tree/)
dfs保存4个参数 1.当前树是不是BST 2.最左边的叶子节点的值 3.最右边的叶子节点的值 4.当前树所有节点的sum

#### [1088. Confusing Number II](https://leetcode.cn/problems/confusing-number-ii/)
因为合法数字很少 所以可以求出所有的组合 然后只要判断对称位置的数是否存在不是1 8 0的数字即可

#### [489. Robot Room Cleaner](https://leetcode.cn/problems/robot-room-cleaner/)
扫地机器人 给一个迷宫 给几个API move turnRight clean 要求打扫整个迷宫 那么就是回溯 注意这里的回溯处理 机器人先对4个方向进行探索 看能不能前进 如果可以的话就前进 最终会回到起始的方向 然后就是要把机器人退回到上一个位置 先右移两下调个头 然后走一步 再右移两步 就回到了正确的位置 这时候再右移动一步探寻下一个方向

#### [631. Design Excel Sum Formula](https://leetcode.cn/problems/design-excel-sum-formula/)
对于每一个单元格 保存这个单元格的val和这个单元格上的sum 
对于get操作 实时计算获取值


#### [2322. Minimum Score After Removals on a Tree](https://leetcode.cn/problems/minimum-score-after-removals-on-a-tree/)
异或操作满足前缀和性质
枚举删除的边 然后计算 注意这里需要判断两个节点的相对位置关系 可以使用时间戳来表示 假设x是y的父亲节点 那么in[x] < in[y] <= out[x]
如果需要具体求两个节点的父节点 那么需要使用树上倍增思想 

#### [1655. Distribute Repeating Integers](https://leetcode.cn/problems/distribute-repeating-integers/)
自己写的和答案最快的一摸一样 除了取前len(quantity)个数的剪枝没想到 为什么只要取前这么多个? 因为个数是从大到小的 并且每个quantity必须是相同的数够成 

#### [1681. Minimum Incompatibility](https://leetcode.cn/problems/minimum-incompatibility/)
这里的dfs会存在重复情况 和1655不同 因为题目是求不用的集合 所以暴力的时候一定存在重复情况 
剪枝技巧: 1. 先排序 2. 如果中途得到的结果已经比res差了 那么直接return 3. 考虑相邻元素如果相同 是否需要剪枝

#### [1307. Verbal Arithmetic Puzzle](https://leetcode.cn/problems/verbal-arithmetic-puzzle/)
注意点: 前导0 必须是单词长度大于1; 如果c=len(res) 需要判断total是不是为0 

#### [761. Special Binary String](https://leetcode.cn/problems/special-binary-string/)
题目意思转换成括号 
参考395 题目要求给定一个字符串 求一个最长的子串并且这个子串里面的字符的频次一定要大于等于k 那么就可以按照那些不满足要求的字符进行分割 

#### [1240. Tiling a Rectangle with the Fewest Squares](https://leetcode.cn/problems/tiling-a-rectangle-with-the-fewest-squares/)
这题数据范围小了 正确解法是暴力dfs因为这是一个np hard问题 不存在多项式解
[http://int-e.eu/~bf3/squares/view.html#16,17](http://int-e.eu/~bf3/squares/view.html#16,17)

#### [2003. Smallest Missing Genetic Value in Each Subtree](https://leetcode.cn/problems/smallest-missing-genetic-value-in-each-subtree/)
注意这里nums是distinct的 所以最多一个1 如果存在这个1 那么就是求这个1到根节点这条链

#### [1516. Move Sub-Tree of N-Ary Tree](https://leetcode.cn/problems/move-sub-tree-of-n-ary-tree/)
这里就是要求把p节点放在q节点下面 分为两种情况
1. q 是 p 的祖先节点 这里的判断是 使用一个函数外的全局变量
2. q 不是 p 的祖先节点 那么看一下q是不是已经是p的父节点了 如果不是的话 那么就把p放到q的children里面去
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTI2ODEzNzg3NF19
-->