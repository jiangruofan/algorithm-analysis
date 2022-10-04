#### [1345. Jump Game IV](https://leetcode.cn/problems/jump-game-iv/)
简洁明了

#### [127. Word Ladder](https://leetcode.cn/problems/word-ladder/)
构造虚拟节点连接所有words 然后双向BFS遍历 代码中没必要index1和index2 可以统一成一个

#### [126. Word Ladder II](https://leetcode.cn/problems/word-ladder-ii/)
注意这里去重必须要全部遍历完再去重 不然会漏情况 因为可能2条不同路径到达同一个结点

#### [773. Sliding Puzzle](https://leetcode.cn/problems/sliding-puzzle/)
注意把二维变成一维的转换

#### [527. Word Abbreviation](https://leetcode.cn/problems/word-abbreviation/)
操作类似于BFS 每次将单词前面的字符压缩一个 如果此时这个压缩字符串唯一 那么就放入答案 不然的话继续进行压缩

#### [1298. Maximum Candies You Can Get from Boxes](https://leetcode.cn/problems/maximum-candies-you-can-get-from-boxes/)
没看答案自己想的 一遍写对

#### [854. K-Similar Strings](https://leetcode.cn/problems/k-similar-strings/)
一遍写对 每次都从左到右依次确定一位 

#### [488. Zuma Game](https://leetcode.cn/problems/zuma-game/)
这里的剪枝操作很精髓 假设要插入的是a 那么对于baaa.. 只需要在第一个a前面插入即可 对于a与前后元素都不同 那么分为两种情况 第一种情况前后元素相同 那么a可以插入在中间 比如 bab...b 这是因为这样可以把最左边的b隔开来 第二种情况 前后元素不同 比如 bac 这种情况可以剪枝 因为不如把a放在其他的a的前面 因为bc本来就不同 不会相互影响
RRWWRRBBRR hands = WB, R(B)RWW(W)RRBBRR 
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTIxNDE4NzAyNjVdfQ==
-->