#### [588. Design In-Memory File System](https://leetcode.cn/problems/design-in-memory-file-system/)
模拟

#### [472. Concatenated Words](https://leetcode.cn/problems/concatenated-words/)
Trie没法解决大量前缀相似的字符串引入的回溯：如果待判字符串的任意前缀子串几乎都出现过，Trie就退化到和哈希一样，无法及早退出
加入记忆化作为解决方案

#### [140. Word Break II](https://leetcode.cn/problems/word-break-ii/)
简单直接

#### [212. Word Search II](https://leetcode.cn/problems/word-search-ii/)
注意剪枝操作

#### [745. Prefix and Suffix Search](https://leetcode.cn/problems/prefix-and-suffix-search/)
题目要求给定前缀和后缀搜索单词 插入单词的时候 可以遍历后缀+'#'+单词 插入  然后插入单词进字典树的时候当遍历到#后面的单词时都记录下index

#### [642. Design Search Autocomplete System](https://leetcode.cn/problems/design-search-autocomplete-system/)
用的heap 求最热的三个

#### [1803. Count Pairs With XOR in a Range](https://leetcode.cn/problems/count-pairs-with-xor-in-a-range/)
把数字的二进制存入一棵树中 

#### [1032. Stream of Characters](https://leetcode.cn/problems/stream-of-characters/)
简单明了

#### [1707. Maximum XOR With an Element From Array](https://leetcode.cn/problems/maximum-xor-with-an-element-from-array/)
在线算法 每一个节点需要记录一下以当前节点为子树的所有值的最小值 这样在query的时候可以用当前子树的最小值来判断是否符合limit要求
对于每一个节点 都可以是0或者1 具体选择1或者0行不行要看1和0对应的子节点 
python会超时 不过代码正确

#### [2227. Encrypt and Decrypt Strings](https://leetcode.cn/problems/encrypt-and-decrypt-strings/)
字典树不是最优解 最优解是直接全部预处理好
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTk5ODU3NDMyNyw3MzA5OTgxMTZdfQ==
-->