#### [132. Palindrome Partitioning II](https://leetcode.cn/problems/palindrome-partitioning-ii/)
两次dp; 第一次先求出所有子区间是否是回文串,  第二次求出最小分割

#### [2188. Minimum Time to Finish the Race](https://leetcode.cn/problems/minimum-time-to-finish-the-race/)
根据换轮胎的限制 每个轮胎最多跑17圈 因为第18圈的时候不如换一个新的轮胎 首先进行预处理求出跑1圈到17圈哪个轮胎的时间最少 然后进行dp 考虑假如当前是最后一个轮胎 那么这个轮胎可以跑1带17圈 所以遍历1-17  需要注意边界情况

#### [629. K Inverse Pairs Array](https://leetcode.cn/problems/k-inverse-pairs-array/)
注意简化 思路清晰

#### [818. Race Car](https://leetcode.cn/problems/race-car/)
路程的前进步数一定是2^k-1 k就是操作次数 
那么如果target正好为2^k-1 那么就操作k次
如果target < 2^k-1 那么有两种选择 一种选择是走到2**k-1然后往回走
还有一种是走到2^(k-1)-1然后往回走一点再往终点走 
时间复杂度是nlogn 

#### [964. Least Operators to Express Number](https://leetcode.cn/problems/least-operators-to-express-number/)
类似818 注意当val为1的时候 需要2个操作 +x/x

#### [1411. Number of Ways to Paint N × 3 Grid](https://leetcode.cn/problems/number-of-ways-to-paint-n-3-grid/)

#### [1931. Painting a Grid With Three Different Colors](https://leetcode.cn/problems/painting-a-grid-with-three-different-colors/)
和1411一样

#### [1691. Maximum Height by Stacking Cuboids](https://leetcode.cn/problems/maximum-height-by-stacking-cuboids/)
堆叠矩形 要求上面的矩阵的长宽高必须小于等于下面的矩形的长宽高 
先对每个矩形的长宽高排序 再对所有的矩形从大到小排序

#### [1340. Jump Game V](https://leetcode.cn/problems/jump-game-v/)
注意这里的映射 有点绕

#### [805. Split Array With Same Average](https://leetcode.cn/problems/split-array-with-same-average/)
定义dp[i]为nums中有多少个数的和为i 如果有1个 那么dp[i]的二进制从右往左数第二位为1 如果有2个 那么dp[i]的二进制从右往左数第三位为1
如果dp[i]为1 那么说明有0个数的和为i 此时i肯定为0 作为初始化条件 
这里需要倒叙遍历 因为这样可以保证当前的更新不会对后续的更新产生影响 

#### [446. Arithmetic Slices II - Subsequence](https://leetcode.cn/problems/arithmetic-slices-ii-subsequence/)
自己想的 直接写对

#### [960. Delete Columns to Make Sorted III](https://leetcode.cn/problems/delete-columns-to-make-sorted-iii/)
就是最长递增子序列 变成多个维度

#### [1639. Number of Ways to Form a Target String Given a Dictionary](https://leetcode.cn/problems/number-of-ways-to-form-a-target-string-given-a-dictionary/)
三元运算符的用法 这里注意边界处理 一遍想对写对

#### [1269. Number of Ways to Stay in the Same Place After Some Steps](https://leetcode.cn/problems/number-of-ways-to-stay-in-the-same-place-after-some-steps/)
因为要回到原点 所以最多只能走到steps//2的位置 

#### [2312. Selling Pieces of Wood](https://leetcode.cn/problems/selling-pieces-of-wood/)
对比1444 切皮萨

#### [1416. Restore The Array](https://leetcode.cn/problems/restore-the-了array/)
简单明了
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTU3MDQyOTk5OCwtNDYxMDk5MjM2XX0=
-->