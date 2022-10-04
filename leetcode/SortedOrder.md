#### [1825. Finding MK Average](https://leetcode.cn/problems/finding-mk-average/)
使用三个有序容器 一个维持最大的k个元素 一个维持最小的k个元素 还有一个维持剩余的元素也就是需要求平均值的元素

#### [352. Data Stream as Disjoint Intervals](https://leetcode.cn/problems/data-stream-as-disjoint-intervals/)
715也可以用这个做

#### [1675. Minimize Deviation in Array](https://leetcode.cn/problems/minimize-deviation-in-array/)
先给奇数乘2这样所有的数字都是偶数 维护一个有序数组 如果最大值是偶数 那就除以2 直到最大值为奇数 
本质就是 632?

#### [363. Max Sum of Rectangle No Larger Than K](https://leetcode.cn/problems/max-sum-of-rectangle-no-larger-than-k/)
枚举上下边界 将二维矩阵压缩成一维向量 这样就转换成 对于每一个j求一个小于j的i 使得 presum[j] - presum[i] 最接近k 
时间复杂度是O(m×m×n×logn)
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTg1MjMzNTc5XX0=
-->