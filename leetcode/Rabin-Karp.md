
p = 131, mod = 2 ** 64 或者 10**9+7
编码倒着编码 正着编码没法求出指定区间值

-----------------
#### [1044. Longest Duplicate Substring](https://leetcode.cn/problems/longest-duplicate-substring/)
求最长的子串 可以用二分+check 对字符串进行先预处理并且保存各个p次方的值 这样可以在O(1)时间内求出字符串的哈希值 然后对于给定长度的子串遍历字符串 看哈希值之前是否出现过 如果之前出现过说明至少有2个子串 返回true

#### [214. Shortest Palindrome](https://leetcode.cn/problems/shortest-palindrome/)
在最前面加入字符使得s变成回文串 那么前面加入的字符一定和s的最后面的字符形成回文串 要求最短的回文串 那么我们可以求s中从起点开始的最长的回文串是多少 这可以用字符串哈希 对字符串进行正反哈希 如果哈希值一样说明组成了回文串 
也可以用kmp和z-array

#### [6097. Match Substring After Replacement](https://leetcode.cn/problems/match-substring-after-replacement/)
暴力和字符串哈希的时间复杂度应该是一样的

#### [2223. Sum of Scores of Built Strings](https://leetcode.cn/problems/sum-of-scores-of-built-strings/)
求最大公共前缀可以使用二分

#### [1923. Longest Common Subpath](https://leetcode.cn/problems/longest-common-subpath/)
二分+check 

#### [1316. Distinct Echo Substrings](https://leetcode.cn/problems/distinct-echo-substrings/)
求有多少个substring 可以写成 s+s 的形式 枚举s 即可

#### [1392. Longest Happy Prefix](https://leetcode.cn/problems/longest-happy-prefix/)
简单明了
可以用kmp

#### [1147. Longest Chunked Palindrome Decomposition](https://leetcode.cn/problems/longest-chunked-palindrome-decomposition/)
注意l==r时候的特殊处理 对于减法之后也需要取模
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE4MDQ4NTIyMTddfQ==
-->