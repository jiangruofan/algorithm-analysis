#### [1687. Delivering Boxes from Storage to Ports](https://leetcode.cn/problems/delivering-boxes-from-storage-to-ports/)
贪心 因为货物是必须按照顺序送 所有每次带上最多的货物 然后出去送 最后回来 但是存在一个问题 就是如果当前能送的货物为 i ...... j 但是 j+1和j是送去同一个码头 那么这个时候可以考虑这次不送j货物 把j货物留着下次送 可能可以节省一次旅途 这个时候需要注意j-1 j-2 是不是也和j是同一个码头 如果也是的话 需要一直向前找找到第一个和j不一样的码头的物品 
 i .....x...... j-2  j-1  j  j+1
假设 x+1 到 j+1的码头相同 本次最大可装载的货物为i到j 
这个时候只有两种情况 1. i到j货物全装了 2. 只装i到x 
为什么不装i 到 x+1 或者 i 到 j-1 因为装这些x和j中间的这些都不是最优解 都不如直接装到j  对于x-1 x-2同理都不如直接装到x
              
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE5MTAxNTYyODVdfQ==
-->