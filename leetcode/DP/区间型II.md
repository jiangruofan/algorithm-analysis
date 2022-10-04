#### [312. Burst Balloons](https://leetcode.cn/problems/burst-balloons/)
对于一个区间[i, j] 假设第k个是最后一个戳破的气球，考虑状态转移方程

#### [1547. Minimum Cost to Cut a Stick](https://leetcode.cn/problems/minimum-cost-to-cut-a-stick/)
类似312

#### [664. Strange Printer](https://leetcode.cn/problems/strange-printer/)
考虑区间[i, j] 如果s[i] = s[j] 那么就是 dp[i][j] = dp[i][j-1]因为打印i的时候可以把j也顺带打印了 如果s[i] != s[j]  那就只能遍历所有子区间取最小值

#### [730. Count Different Palindromic Subsequences](https://leetcode.cn/problems/count-different-palindromic-subsequences/)
因为固定了字母只有A,B,C,D四个 所以对于任何一个回文串 最外层只能是这4个pair 对于一个区间 找到l和r的右边和左边第一个A或者B或者C或者D 然后形成回文串
油管评论面试不给过

#### [1563. Stone Game V](https://leetcode.cn/problems/stone-game-v/)
本题就是求给定一个区间 将区间分成左区间和右区间 取sum小的一个区间进行下一步 那么对于区间一定存在一个中间点 使得在中间点左边分割区间 左区间的和一定比右区间小 所以如果知道以分割点为中间点的左部分构成的所有区间的最大值和右部分构成的所有区间的最大值 取2个的大的一个就可以 对于中间点可以实时更新 因为中间点一定是向右边移动的 对于更新区间的最大值也是实时更新的 比如当前遍历长度为L的区间 那么更新的区间就是长度为L的 

#### [471. Encode String with Shortest Length](https://leetcode.cn/problems/encode-string-with-shortest-length/)
对于一个区间 给区间编码并且使得编码后的区间最短 那么可以两种情况 1.给区间直接编码 2. 枚举分割点利用小区间进行编码

#### [1312. Minimum Insertion Steps to Make a String Palindrome](https://leetcode.cn/problems/minimum-insertion-steps-to-make-a-string-palindrome/)
dp[i][j]考虑s[i]和s[j]是否相同

#### [546. Remove Boxes](https://leetcode.cn/problems/remove-boxes/)
有一点明确的是 连接在一起的相同元素一定是整体计算不能拆分 因为拆分了一定比看成整体得到的分数小
对于一个区间[l, r] 考虑最左边的元素 假设值为val 对于这个区间可以得到的最大分数 可以看成val之间的相连来得到 [val ...... val...... val...... val]
可以看成把val之间的间隔里面的元素先删掉 再删除val 
需要额外维护一个变量表示val的个数



<!--stackedit_data:
eyJoaXN0b3J5IjpbMTAwNzEyODY5MV19
-->