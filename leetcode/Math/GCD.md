#### [2183. Count Array Pairs Divisible by K](https://leetcode.cn/problems/count-array-pairs-divisible-by-k/)
a = 35,  k = 15 最大公约数为 5
两个数(a, b)相乘能够被k整除 我们先求出gcd(a, k) 然后寻找b b只要满足b是 k/gcd(a, k) 的倍数就可以

#### [2197. Replace Non-Coprime Numbers in Array](https://leetcode.cn/problems/replace-non-coprime-numbers-in-array/)
两个正整数的**最小公倍数**等于这两个**数**的积除以这两个**数**的**最大公约数**。

#### [878. Nth Magical Number](https://leetcode.cn/problems/nth-magical-number/)
这里先求出最小公倍数 以最小公倍数为一个区间 计算出一个区间内有多少个合法的数字 然后对于剩下的数字 进行暴力计算即可 

#### [1250. Check If It Is a Good Array](https://leetcode.cn/problems/check-if-it-is-a-good-array/)
裴蜀定理(重要推论) : a,b互质的充分必要条件是存在整数x,y使ax+by=1.

#### [6122. Minimum Deletions to Make Array Divisible](https://leetcode.cn/problems/minimum-deletions-to-make-array-divisible/)
这里质因数分解 是求出所有可以被num整除的数

#### [1819. Number of Different Subsequences GCDs](https://leetcode.cn/problems/number-of-different-subsequences-gcds/)
这里时间复杂度是nlogn 调和级数 
这里的核心是 给定一个x的倍数的序列 问能否找出一个子序列使得它的最大公约数是x 那么只需要对这个序列的所有元素求gcd 如果最后的gcd是x 那么就一定存在一个子序列 实际代码可以提前结束 只要gcd等于x 

#### [1735. Count Ways to Make Array With Product](https://leetcode.cn/problems/count-ways-to-make-array-with-product/)
质因数分解 对于x个相同的小球放入n个不同的盒子并且盒子可以为空 求有多少种方案 插板法
python math包 comb求组合 perm求排列

#### [2338. Count the Number of Ideal Arrays](https://leetcode.cn/problems/count-the-number-of-ideal-arrays/)
和1735一样
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTk3MzcwODExM119
-->