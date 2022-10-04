#### [895. Maximum Frequency Stack](https://leetcode.cn/problems/maximum-frequency-stack/)
使用2个字典 一个字典保存频率 还有一个字典保存每个频率有哪些val 
这里频率存在递增性 如果最大频率没有元素了 那么最大频率减一即可

#### [460. LFU Cache](https://leetcode.cn/problems/lfu-cache/)
哈希表＋链表 
题目的意思是 可以插入key val 如果存在那就变成更新 还可以获取key对应的val值 但是对于key的数量存在限制 如果超过了数量 那么就需要删除使用频率最低的那个元素 如果存在多个相同使用频率最低的元素 那么就删除最久没有使用过的那个 
使用2个哈希表 
一个哈希表保存key和它对应的node  另一个哈希表保存某个频率下有哪些node(使用双向链表) 对于插入node 插在链表最右边 这样最左边的元素就是最久没有使用的元素
对于获取操作和更新操作 需要将某个元素的频率增加1 
对于插入操作 如果当前元素没超过数量限制 那就在频率为1的链表最右边插入元素 如果当前元素超过数量限制 那么就需要删除最低使用频率的链表的最右边的元素


#### [1206. Design Skiplist](https://leetcode.cn/problems/design-skiplist/)
简单明了 random.randint(both included)


#### [710. Random Pick with Blacklist](https://leetcode.cn/problems/random-pick-with-blacklist/)
把黑名单里面的元素都映射到最后面

#### [2025. Maximum Number of Ways to Partition an Array](https://leetcode.cn/problems/maximum-number-of-ways-to-partition-an-array/)
枚举遍历

#### [381. Insert Delete GetRandom O(1) - Duplicates allowed](https://leetcode.cn/problems/insert-delete-getrandom-o1-duplicates-allowed/)
删除一个元素可以把这个元素换到末尾然后删除末尾元素 这样就是O(1) 配合哈希表定位 

#### [1224. Maximum Equal Frequency](https://leetcode.cn/problems/maximum-equal-frequency/)
两个哈希表 注意这里是一定要删除一个元素
那么可以分为2种大情况 每个大情况又可以分成2种小情况 
1.(1)  1 2 3 4 5 6 7
1.(2)  1 1 1 1 1 1 1 1 
2.(1) 3 3 3 2 2 2 7
2.(2) 3 3 3 2 2 2 2 

#### [6159. Maximum Segment Sum After Removals](https://leetcode.cn/problems/maximum-segment-sum-after-removals/)
倒叙遍历 思想类似时空倒流 有两道并查集的题目也是时空倒流
这题不用并查集
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTc4OTYzODcwXX0=
-->