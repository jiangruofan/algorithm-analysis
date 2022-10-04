

#### [1220. Count Vowels Permutation](https://leetcode.cn/problems/count-vowels-permutation/)
#### [123. Best Time to Buy and Sell Stock III](https://leetcode.cn/problems/best-time-to-buy-and-sell-stock-iii/)
#### [188. Best Time to Buy and Sell Stock IV](https://leetcode.cn/problems/best-time-to-buy-and-sell-stock-iv/)
直接明了


#### [174. Dungeon Game](https://leetcode.cn/problems/dungeon-game/)
考虑dp[i][j]由dp[i+1][j]和dp[i][j+1]转移而来, 取二者中小的那一个然后减去[i][j]的值, 但是注意生命值最少为1, 如果当前是能量增强药剂的话可能出现负数, 注意初始化最后一个公主的位置要么是1要么是1-val, 并且增加一个维度的边界初始化为float('inf)

#### [639. Decode Ways II](https://leetcode.cn/problems/decode-ways-ii/)
注意不同情况的讨论

#### [1235. Maximum Profit in Job Scheduling](https://leetcode.cn/problems/maximum-profit-in-job-scheduling/)
对比435
对于这种non-overlapping区间题目 先对endpoint进行排序
对于本题 思考第i个区间 选还是不选 然后用二分定位 时间复杂度应该是nlogn

#### [1751. Maximum Number of Events That Can Be Attended II](https://leetcode.cn/problems/maximum-number-of-events-that-can-be-attended-ii/)
和1235一样

#### [1216. Valid Palindrome III](https://leetcode.cn/problems/valid-palindrome-iii/)
可以转化为求把s变成回文串的最少删除操作 然后和k进行比较

#### [801. Minimum Swaps To Make Sequences Increasing](https://leetcode.cn/problems/minimum-swaps-to-make-sequences-increasing/)
注意这里的交换只能是相同index的val交换	

#### [1531. String Compression II](https://leetcode.cn/problems/string-compression-ii/)
这个题目参考国服第一的解法 很简洁 
定义dp[i][j]表示前i个字符最多删除j个字符后的压缩字符串的最短长度
题目的意思就是给定一个字符串s 要求最多删除k个字符 然后压缩字符串使得字符串最短
考虑第i个字符 如果删除那么就是 dp[i][j] = dp[i-1][j-1]
如果不删除 那么就需要找i后面和第i个字符相同的字符个数和需要删除个数 从前面的推出后面的

#### [552. Student Attendance Record II](https://leetcode.cn/problems/student-attendance-record-ii/)
dp[n][i][j]  n表示第几个 i表示最后有几个L   j表示缺席的次数
很类似股票

#### [1866. Number of Ways to Rearrange Sticks With K Sticks Visible](https://leetcode.cn/problems/number-of-ways-to-rearrange-sticks-with-k-sticks-visible/)
给定n个长度为1-n的棍子 要求有多少种排列只能看到k个棍子
可以想象成一个棍子维护一个区间 棍子后面区间里的棍子都比第一个棍子矮 那么对于dp[i][j] 可以分两种情况 第一种情况就是第j个棍子自己维护一个区间 那么对应的就是dp[i-1][j-1] 第二种情况就是第j个棍子加入前面已经形成的j个区间 那么对应的就是dp[i-1][j] * (i-1) 为什么棍子可以插入任何一个地方? 对于棍子插入的区间 首先把这个区间挪到最后 然后把这个区间里面在棍子前面的棍子挪到后面去 这样就可以保证所有情况都是unique的

#### [1420. Build Array Where You Can Find The Maximum Exactly K Comparisons](https://leetcode.cn/problems/build-array-where-you-can-find-the-maximum-exactly-k-comparisons/)
和1866不同 1866的要求是1-n固定数目的 但是本题不是 这很关键
这里的dp定义是 dp[i][j][k] 数组的前i位的最大值为j并且cost为k时的情况有多少种 考虑第i位是否为j 


#### [1359. Count All Valid Pickup and Delivery Options](https://leetcode.cn/problems/count-all-valid-pickup-and-delivery-options/)
等比数列求和

#### [1092. Shortest Common Supersequence](https://leetcode.cn/problems/shortest-common-supersequence/)
记录路径

#### [1363. Largest Multiple of Three](https://leetcode.cn/problems/largest-multiple-of-three/)
3的倍数的数的各个位上的和一定是3的倍数
记录路径不要想着可以跳掉某一个位置 必须每一个位置都逆推 如果当前位置不符合 就用特殊数字或者字符标记 逆推的时候跳过即可

#### [265. Paint House II](https://leetcode.cn/problems/paint-house-ii/)
给定n个房子和k种颜色 要求给房子都涂上颜色 并且相邻的房子颜色不能相同 求最少的cost 那么对于第i个房子 假设第i-1个房子涂x颜色的cost最小 那么第i个房子除了x颜色 涂其他的颜色都是选择dp[i-1][x] 对于第i个房子涂x颜色 就只要找到前一个房子涂x以外的颜色的最小cost就行

#### [1473. Paint House III](https://leetcode.cn/problems/paint-house-iii/)
设状态转移方程为dp[i][j][k] 表示第从第一个到第i个房子构成j个街坊并且最后一个房子的颜色为k的最小值
对于第i个房子 看是否已经有颜色 如果已经有颜色 就是看前面一个房子的颜色是不是和它相等或者不等 遍历一遍即可
如果没有颜色 需要遍历当前的房子图n种颜色 并且前面一个房子也有n种颜色的情况 这样时间复杂度是n^2 但是可以简化 假如当前的房子颜色和前一个房子的颜色相同 那么就是dp[i-1][j][k] 如果颜色不相同 那么就是前面一个房子所有颜色和当前房子颜色不相同的颜色中最小的一个值 所以只要知道前一个房子构成的值的最小的两个值和相对应的颜色即可 

#### [1289. Minimum Falling Path Sum II](https://leetcode.cn/problems/minimum-falling-path-sum-ii/)
求最大值和次小值 类似粉刷房子

#### [2272. Substring With Largest Variance](https://leetcode.cn/problems/substring-with-largest-variance/)
题目要求一个区间中两个元素的频率的差的最大值 因为只有26个英文字母 所以可以遍历 两层遍历 假设给定两个字母 x和y 那么就是求一个区间使得x的频率减去y的频率最大 经过所有的遍历 最终的最大值就是答案 
可以把x看成1 y看成-1 那么就是求一个子区间和最大 但是注意这个区间一定要包含-1 所以dp的状态可以有2个 状态1表示不包含-1 状态2表示包含至少1个-1 所有状态2的最大值就是答案

#### [1692. Count Ways to Distribute Candies](https://leetcode.cn/problems/count-ways-to-distribute-candies/)
把n个物品放入k个背包 对于第i个物品 可以单独放一个背包 也可以放在有物品的背包里

#### [1977. Number of Ways to Separate Numbers](https://leetcode.cn/problems/number-of-ways-to-separate-numbers/)
dp[i][leng] = sum( dp[i-leng][k] for k in range(1, leng) ) 
重新定义dp
这里还需要求给定2个子字符串 判断大小关系 可以求最长公共前缀 

#### [1883. Minimum Skips to Arrive at Meeting On Time](https://leetcode.cn/problems/minimum-skips-to-arrive-at-meeting-on-time/)
定义dp状态为 dp[i][j]表示走过前i条路并且跳过j次所需要的最少时间
那么答案就是dp[-1][k] 最小的k使得dp[-1][k] 小于等于hoursbefore

#### [1872. Stone Game VIII](https://leetcode.cn/problems/stone-game-viii/)
题目的最大最小值的意思是对于alice和bob都希望自己的分数最大 
找规律
dp[1] = 0
dp[2] = max presum(n) - dp[1]
dp[3] = max presum(n) - dp[1], presum(n-1) - dp[2]
dp[4] = max presum(n) - dp[1], presum(n-1) - dp[2], presum(n-2) - dp[3]

#### [6107. Number of Distinct Roll Sequences](https://leetcode.cn/problems/number-of-distinct-roll-sequences/)
dp定义为 当前序列的长度为n 最后一个数字是x 倒数第二个是y 
矩阵快速幂没看 
1411. 给 N x 3 网格图涂色的方案数
1412. 用三种不同颜色为网格涂色
1413. Number of Ways to Build Sturdy Brick Wall
上面三题感觉也符合矩阵快速幂

#### [940. Distinct Subsequences II](https://leetcode.cn/problems/distinct-subsequences-ii/)
定义dp[i]为 从字符串开头到i总共有多少个不同的子序列 
那么对于dp[i+1] 分为两种情况 不考虑s[i+1]这个字符 那么就是dp[i]种 考虑s[i+1]这个字符 那么就是把s[i+1]这个字符加到dp[i]这么多种不同子序列的后面 得到的结果也一定是不同的子序列 但是注意可能存在重复情况 这个时候找到从i+1往前数的第一个和s[i+1]相同的字符 假设这个字符位于j 那么答案再减去dp[j-1]即可 

#### [1987. Number of Unique Good Subsequences](https://leetcode.cn/problems/number-of-unique-good-subsequences/)
从后往前考虑 定义dp[i][0]为字符串从i开始一直到最后有多少个以0为开头的不同的子序列 dp[i][1]为字符串从i开始一直到最后有多少个以1为开头的不同的子序列 
那么对于第i-1个字符 如果为0的话 那么dp[i][1]不变 
dp[i][0] 分为三种情况考虑 1. 把0加到 dp[i][0]和dp[i][1] 这些不同的子序列前面 2. 0单独作为一个元素 3. dp[i][0]这些元素本身就符合 但是这些元素和第一种情况重复了 不考虑 

#### [2088. Count Fertile Pyramids in a Land](https://leetcode.cn/problems/count-fertile-pyramids-in-a-land/)
图的dp dp[i][j]表示以当前位置为金字塔的顶端能够够成的金字塔有多少个 官方解答的图片很好 

#### [1301. Number of Paths with Max Score](https://leetcode.cn/problems/number-of-paths-with-max-score/)
和2088都是二维矩阵dp

#### [403. Frog Jump](https://leetcode.cn/problems/frog-jump/)
用dict来存储很精髓

#### [2143. Choose Numbers From Two Arrays in Range](https://leetcode.cn/problems/choose-numbers-from-two-arrays-in-range/)
也是用dict存储 时间复杂度是O(10^6)

#### [956. Tallest Billboard](https://leetcode.cn/problems/tallest-billboard/)
题目意思可以转换为 给定一个数组 对每一个元素可以取正或者取负或者不取 求对每一个元素进行操作后所有元素的和为0的正数和的最大值
这里可以通过折半降低时间复杂度 时间复杂度为 O(10^5)

#### [903. Valid Permutations for DI Sequence](https://leetcode.cn/problems/valid-permutations-for-di-sequence/)
increase  
2 1 0 [1] -> 3 2 0 [1]  
decrease  
1 0 2 [1] -> 2 0 3 [1]  
0 2 1 [1] -> 0 3 2 [1]
注意时间复杂度的优化

#### [1187. Make Array Strictly Increasing](https://leetcode.cn/problems/make-array-strictly-increasing/)
这里注意如果不替换需要单独拿出来考虑 时间复杂度优化

#### [2321. Maximum Score Of Spliced Array](https://leetcode.cn/problems/maximum-score-of-spliced-array/)
本质就是最大字序和

#### [514. Freedom Trail](https://leetcode.cn/problems/freedom-trail/)
注意顺时针和逆时针都要考虑 

#### [1955. Count Number of Special Subsequences](https://leetcode.cn/problems/count-number-of-special-subsequences/)
简单明了 类似2167

#### [1787. Make the XOR of All Segments Equal to Zero](https://leetcode.cn/problems/make-the-xor-of-all-segments-equal-to-zero/)
评论 困难中的困难
首先dp[i][j]表示以i结尾并且异或为j的最少操作次数 
注意初始化dp[0][0]为0
时间复杂度为O(k×1024×n/k)

#### [2361. Minimum Costs Using the Train Line](https://leetcode.cn/problems/minimum-costs-using-the-train-line/)
太简单了 水题

#### [879. Profitable Schemes](https://leetcode.cn/problems/profitable-schemes/)
dp定义为从前i个项目选取,并且人数最多为j个人,利润至少为k的方案数

#### [1449. Form Largest Integer With Digits That Add up to Target](https://leetcode.cn/problems/form-largest-integer-with-digits-that-add-up-to-target/)
允许重复的背包

#### [920. Number of Music Playlists](https://leetcode.cn/problems/number-of-music-playlists/)
dp[i][j]表示听前i首歌并且有j首不同的歌的方案数
如果当前听的歌是新歌 那么就是dp[i-1][j-1] * (总歌曲数-j+1)
如果当前听的歌是旧歌 那么就是dp[i-1][j] * (j - k) 因为总共有j首歌可以选择 但是连续的k首歌是不能相同的 

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEwNTY4NDA5MzRdfQ==
-->