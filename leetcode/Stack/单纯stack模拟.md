#### [726. Number of Atoms](https://leetcode.cn/problems/number-of-atoms/)
简单模拟 对于括号里的需要重新开一个dict来记录然后结束的时候加入到前一个dict中

#### [759. Employee Free Time](https://leetcode.cn/problems/employee-free-time/)
按照工作时间排序 然后遍历 如果存在间隔 把间隔加入答案

#### [2296. Design a Text Editor](https://leetcode.cn/problems/design-a-text-editor/)
使用2个stack模拟 光标位置就是两个栈的中间位置  
可以使用链表 对于需要在O(1) 时间复杂度进行插入删除的考虑链表

#### [1096. Brace Expansion II](https://leetcode.cn/problems/brace-expansion-ii/)
题目的意思就是 对于逗号隔开的左右元素 需要把左右两边合并起来 对于没有逗号连接的左右两个元素 需要做product操作 
那么遇到 { 就放入两个set 第一个set表示所有已经处理好的元素 第二个set表示当前正在处理的元素 遇到 } 就把第二个set融入到第一个set 这个时候第一个set就表示这个{} 括号对的处理结果 然后再把第一个set和上一个set进行product操作 遇到逗号 说明当前的元素处理完了 把最后一个set融入到倒数第二个set 遇到字符 那么就直接把字符和最后一个set进行product操作
 {a, b{c}d} 

#### [1106. Parsing A Boolean Expression](https://leetcode.cn/problems/parsing-a-boolean-expression/)
简单明了 类似726
<!--stackedit_data:
eyJoaXN0b3J5IjpbOTA4NDQ2Nzc0XX0=
-->