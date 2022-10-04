#### [76. Minimum Window Substring](https://leetcode.cn/problems/minimum-window-substring/)
简单明了

#### [992. Subarrays with K Different Integers](https://leetcode.cn/problems/subarrays-with-k-different-integers/)
遍历nums 固定右区间(i) 左边界为2个(l1, l2)  l1表示的是[l1, i]中不同val的有k个 l2表示的是[l2, i]中不同val的有k-1个 答案就是l2-l1

#### [689. Maximum Sum of 3 Non-Overlapping Subarrays](https://leetcode.cn/problems/maximum-sum-of-3-non-overlapping-subarrays/)
先思考如果题目是2个subarray不是3个 那么就是维护2个滑动窗口 保持第一个窗口的最大值和index 如果sum12更小的话 就更新第二个窗口的index 如果是3个subarray 类似方法

#### [1610. Maximum Number of Visible Points](https://leetcode.cn/problems/maximum-number-of-visible-points/)
使用atan 自动处理边界情况 注意因为angle很大所以把值都+360度加在末尾 然后使用双指针

#### [30. Substring with Concatenation of All Words](https://leetcode.cn/problems/substring-with-concatenation-of-all-words/)
这题的关键在于word的长度是固定的所以这个substring的长度是固定的
所以多起点进行滑动窗口 每次滑动一个word的长度

#### [6098. Count Subarrays With Score Less Than K](https://leetcode.cn/problems/count-subarrays-with-score-less-than-k/)
简单明了

#### [2009. Minimum Number of Operations to Make Array Continuous](https://leetcode.cn/problems/minimum-number-of-operations-to-make-array-continuous/)
这里最小值为什么是从nums中的数字开始遍历 而不是遍历每一个数字 贪心思想 模拟面试谷歌面经题也是 

[2398. Maximum Number of Robots Within Budget](https://leetcode.com/problems/maximum-number-of-robots-within-budget/)
可以看成是求最长子字符串
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTUwMzI2MDM1N119
-->