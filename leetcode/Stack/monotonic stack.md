
#### [975. Odd Even Jump](https://leetcode.cn/problems/odd-even-jump/)
首先这里的奇数和偶数是指第几次跳的时候的奇偶,  对于奇偶情况其实就求对于每一个val 它右边比它大的最小元素是多少 它右边比它小的最大元素是多少 可以先对数组的index按照val排序 然后转换成寻找右边第一个比index大的元素 然后使用单调栈

#### [321. Create Maximum Number](https://leetcode.cn/problems/create-maximum-number/)
枚举k分配给两个数组 然后求对于每个数组要取出n个数使得这n个数组成的一个数字最大并且这n个数要保持相对顺序 可以用单调栈 考虑需要删除的数 假设为m 保持一个单调递减的栈 并且使得删除数的个数等于m
最后对于取出的2列数配对大的在前面 这里可以使用python的list比较

#### [42. Trapping Rain Water](https://leetcode.cn/problems/trapping-rain-water/)
要想蓄水 需要考虑3个柱子 中间的柱子作为底部 左右两边的柱子中短的那一根就是蓄水池的高度

#### [85. Maximal Rectangle](https://leetcode.cn/problems/maximal-rectangle/)
用单调栈可以求一维的最大矩形面积 那就遍历一个维度 变成一维

#### [84. Largest Rectangle in Histogram](https://leetcode.cn/problems/largest-rectangle-in-histogram/)
对于每个矩形 寻找右边第一个高度比它小的矩形

#### [1944. Number of Visible People in a Queue](https://leetcode.cn/problems/number-of-visible-people-in-a-queue/)
从右往左遍历 如果右边有元素比自己矮 那么就剔除 因为前面的元素一定看不到 符合单调栈的及时删除不是最优解的元素的宗旨 注意如果stack里面还有元素 那么cnt要加1 

#### [1776. Car Fleet II](https://leetcode.cn/problems/car-fleet-ii/)
没自己写

#### [1063. Number of Valid Subarrays](https://leetcode.cn/problems/number-of-valid-subarrays/)
要求有多少个子数组 最左边的元素小于等于其他的元素 维护一个单调递增的栈

#### [2030. Smallest K-Length Subsequence With Occurrences of a Letter](https://leetcode.cn/problems/smallest-k-length-subsequence-with-occurrences-of-a-letter/)
假设字符串长度为n 首先可以计算出总共需要删除n-k个字符 并且对于字符letter的删除个数有限制  先利用单调栈删除字符 可以保证删除字符后的新字符串一定是一个字典序最小的字符串 然后再从后往前继续删除字符 注意如果删除的是letter并且这个letter不能被删除了 那么就跳过

#### [768. Max Chunks To Make Sorted II](https://leetcode.cn/problems/max-chunks-to-make-sorted-ii/)
要求把数组分成若干个部分 然后每个部分排序后变成的新数组是旧数组排序后的样子  可以知道 如果对于一个数字x 它后面如果存在若个连续y都比x小 那么x和这些y必须组成一个chunk  所以维护一个单调递增的栈 

#### [6119. Subarray With Elements Greater Than Varying Threshold](https://leetcode.cn/problems/subarray-with-elements-greater-than-varying-threshold/)
单调栈求左右两边比当前元素小的元素

#### [2355. Maximum Number of Books You Can Take](https://leetcode.cn/problems/maximum-number-of-books-you-can-take/)
计算可以每次递减一到最左边的哪里 想象成下楼梯 这里的求左边第一个小的元素和6119的可能不一样

#### [2289. Steps to Make Array Non-decreasing](https://leetcode.cn/problems/steps-to-make-array-non-decreasing/)
好题 自己想的


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTMzMzE5MjAsNzMwOTk4MTE2XX0=
-->