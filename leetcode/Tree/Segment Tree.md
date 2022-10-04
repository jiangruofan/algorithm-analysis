线段树区间修改需要用lazy tag 单体修改不需要
---------
#### [2213. Longest Substring of One Repeating Character](https://leetcode.cn/problems/longest-substring-of-one-repeating-character/)
题目意思是 对于一个字符串 我们每次修改一个其中的元素 并且要求最长的子串只能有一个重复的字符 维护一个线段树 线段树的节点 保存左右字符和相同的左右字符的长度prefix和suffix 再保存一个最长的只包含一个重复字符的字符串的长度

#### [2286. Booking Concert Tickets in Groups](https://leetcode.cn/problems/booking-concert-tickets-in-groups/)
这题的线段树需要维护2个属性 区间最大值和区间和 
我们需要求第一个大于等于k的行和是否存在前i行的sum大于等于k
对于找最大值 如果node.l.max1大于等于最大值 那么答案肯定在左叶子节点 不然就在右叶子节点 注意这里存在边界限定
对于找prefix sum 如果左叶子节点的sum小于等于k 那么左叶子节点的sum和max都置为0 但是这里需要注意不能直接置0 需要根据返回值是否为true再来重置 

#### [732. My Calendar III](https://leetcode.cn/problems/my-calendar-iii/)
本质就是维护一个数组 需要给一个区间加1 并且要求这个数组的最大值 
官方答案很好 使用了lazy tag但是却没有传播 因为题目只要求原始区间的最大值不要求子区间的最大值 所以本质上如果求任何一个子区间的最大值 这个子区间在某个lazy tag节点下 那么子区间的最大值就不对 因为没有进行惰性传播

#### [1157. Online Majority Element In Subarray](https://leetcode.cn/problems/online-majority-element-in-subarray/)
摩尔投票的思想
对于给定的一个区间 我们要求区间中频率最大的元素并且这个元素一定频率过半 线段树的每一个区间保存可能的频率最大的元素的candidate
还有频率最大的元素的幸存数 就是candidate的频率减去别的元素的频率 我们最终可以获取一个区间可能的candidate 然后再通过二分确定这个candidate到底是不是答案

#### [699. Falling Squares](https://leetcode.cn/problems/falling-squares/)
先进性离散化 也可以不进行离散化 直接选择10^9作为右边界
题目就是需要进行两个操作 1.查询 求出给定区间的最大值 2.update 将给定区间的最大值赋值为新的数 

#### [6206. Longest Increasing Subsequence II](https://leetcode.cn/problems/longest-increasing-subsequence-ii/)
单体修改 区间查询

-------------------------
区间覆盖
#### [2276. Count Integers in Intervals](https://leetcode.cn/problems/count-integers-in-intervals/)
给定一个区间 对某个子区间进行覆盖 求这个区间有多少元素被覆盖 

#### [2158. Amount of New Area Painted Each Day](https://leetcode.cn/problems/amount-of-new-area-painted-each-day/)
类似2276

#### [715. Range Module](https://leetcode.cn/problems/range-module/)
题目可以变相理解为 给定一个区间 给某个子区间赋予两种颜色中的一种 (add为1 delete为2) 求给定一个区间 这个区间的颜色是不是都是1 那么对于每个节点的值 1和2就是表示两种颜色 0就是表示没有颜色或者存在多种颜色的重叠 
对于多种颜色的区间覆盖问题 都不需要lazy tag 因为lazy tag的值和节点的值是一样的 虽然省略了lazy tag 但是不能忘记还是需要向下传播的


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE1ODg3Nzk1NjddfQ==
-->