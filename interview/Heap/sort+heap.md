[Any idea how to solve this problem? I just bombed it in an interview.](https://leetcode.com/discuss/interview-question/889942/Any-idea-how-to-solve-this-problem-I-just-bombed-it-in-an-interview.)

You have n items, cost is c(i) and delivery cost is d(i). If customer orders more than one item, then they get it for the minimum delivery cost. How do you find the maximum amount of money you can make after delivering m items? I know this is a knapsack problem, but I just can't find a way to solve it. And I want to make sure I am able to solve these problems for future interviews.

For e.g.  
cost and delivery cost respectively (first column being cost, second being delivery cost):  
Item 1: 7, 10  
Item 2: 4, 15  
Item3: 8, 1

m = 2

Input format (java): int n, int m, int[][] arr where n is the total number of items, m is the maximum number of items you can deliver, arr has each row with first element being cost, second being delivery cost.

Output: 31 (You choose the first two items because if you chose the 3rd item, the delivery cost for 2 items would be 1 + 1 (since 1 is the mimimum delivery cost) so you would end up with 23 + 2 = 25.

先排序然后使用heap维护最大的元素

----------------

[Google | Onsite](https://leetcode.com/discuss/interview-question/887451/Google-or-Onsite)
给定一个list 里面的元素是(a, b, c) 可以合并两个元素 合并后对应位置取两个元素大的那一个
现在给定一些query (x, y, z) 问是否可以通过合并list里面的元素得到(x,y,z)

首先对list里面的元素进行处理 dic = defaultdict(lambda: defaultdict(list))
这里的list是heap dic其实就是(a, b, c1c2...) 需要对a和b排序
然后对query进行排序 从小到大
还需要维护两个字典 保存所有处理过得元素的y和z对应的最小的z和最小的y 也是用heap 
然后依次处理query 先判断当前list里面是否存在一个以x开头的元素并且它的y和z小于等于当前query的y和z 如果不存在 那么没法合并成query元素 如果可以 那么就看之前处理过的元素中是否存在一个y等于当前query的y并且z小于等于当前query的z的元素 再看一下z一样 
总体时间复杂度应该是nlogn 

---------

[PayPal Interview Question](https://leetcode.com/discuss/interview-question/2915943/PayPal-Interview-Question)

Given a budget B and an array of n * 2 dimension, where arr[i][0] is value and arr[i][1] is price, find the maximum value that we can obtain with budget B by purchasing at most two items.

双指针不行 因为存在重复选择

----

[Need help with Bytedance OA](https://leetcode.com/discuss/interview-question/2966265/Need-help-with-Bytedance-OA)

![image](https://assets.leetcode.com/users/images/4c003d06-947e-4c41-92c6-dcac23db77ce_1672299704.006492.png)
![image](https://assets.leetcode.com/users/images/735604be-dd8e-4dd7-9da5-8f25487e6c33_1672299704.2958272.png)
![image](https://assets.leetcode.com/users/images/3a4a4c58-c393-49ed-8d10-07a237fc6fac_1672299704.3207173.png)
![image](https://assets.leetcode.com/users/images/ecfe8909-fccb-40d7-9b32-ce9256bd535f_1672299704.4476304.png)
![image](https://assets.leetcode.com/users/images/5075e33b-6227-4b83-9672-cf94b27b9203_1672299704.3939502.png)
![image](https://assets.leetcode.com/users/images/0627c21b-598c-408a-9551-cc1d058e8d07_1672299704.6060402.png)
![image](https://assets.leetcode.com/users/images/c6b29a1c-c6bd-47a1-b135-c83a3bf344d6_1672299704.4349833.png)

和上题类似

----

<!--stackedit_data:
eyJoaXN0b3J5IjpbOTg5MjY3MzY3LC0xNDIwMDMyMjMwLDExMj
UyMTE3NDAsLTg3MTU2NjM1Nl19
-->