[Google | Onsite | London](https://leetcode.com/discuss/interview-question/2304772/Google-or-Onsite-or-London)

given a string s which contains only curly braces and questions was what is the minimum number of operations to become it valid expression and return corrected string. There are three operations:  
_insert_  { or } in any position  
_delete_  { or } in any position  
_flip_  any position so { change by } or vice versa.  
I solved it using a stack in linear time and space complexity and the follow-up question was if I could solve it without extra space. my answer was NO**

given N, K and array A length of N and contains non-negative integers. for example N = 5, K = 2, A = [4, 8, 1, 10, 2]. K is initial work capability which means that you can work K days, when you work i-th day your capability decreases by 1 and you get reward A[i], when you skip day your current capability increases by 1. you start at 0 and the question was what is the maximum total reward you can get.  
In this example, the answer is 22 because you work 0 and 1 day, after that your capability will become 0. After that you skipp day 2 and capability becomes 1 and you work day 3 and you will get 10 reward, in total 4+8+10=22 reward and it's the maximum you can achieve.**

------------------------------------------------------------------------------------

[find k pairs having lowest abs sum. | OA](https://leetcode.com/discuss/interview-question/2405122/find-k-pairs-having-lowest-abs-sum.-or-OA)

Given an array, return K pairs having lowest abs difference.

```
arr = [ 3, 1, 5, 3]
k=3

Output = [0, 2, 2]  # output should be sorted

|3-1|=2
|3-3|=0
|3-5|=2
|1-3|=2
|1-5|=4
|3-5|=2

```

Constrains  
n = size of array  
2 <= n <= 10^5  
1<= arr[i]<= 10^8  
1<=k<= min ( 2 * 10^5, n*(n-1)/2 )

两种解法 1. heap 2.二分
#### (Solution 1) Heap [from @leetcode_dafu]

**Pro:**  Short & Sweet to implement.  
**Con:**  Just a tiny bit slower and use a bit more memory than Solution 2.

```
    static int[] solve2(int[] A, int k){
        Arrays.sort(A);
        int n = A.length;
        var minheap = new PriorityQueue<int[]>(Comparator.comparingInt(o -> o[0]));
        for (int i = 1; i < A.length; i++){
            minheap.offer(new int[]{A[i]-A[i-1],i-1,i});
        }
        int[] ans = new int[k];
        while(k > 0){
            int[] top = minheap.poll();
            int val = top[0], L = top[1], R = top[2];
            ans[--k]=val;
            if (R < A.length -1){
                minheap.offer(new int[]{A[R+1]-A[L], L, R+1});
            }
        }
        Arrays.sort(ans);
        return ans;
    }
```

#### (Solution 2) Binary Search & Sliding Window

`Time O(max(nlogn, nlogA[i], k))`  
`Space O(n) / O(1)`  [depending on whether the return array counts]

#### Idea

1.  The element ordering does not matter. First thing we do is sort.
2.  We apply binary search to find the max bound such that the number of pairs no less than it wouldn't go over  `k`. To count efficiently, use sliding window.
3.  We fill our answer array.

I tested it with the bruteforce solution to ensure its correctness.

#### Java

```
    static int[] solve(int[] A, int k){
        Arrays.sort(A);
        int lo = 0, hi = (int)1e8;
        while(lo < hi){ // find max bound 
            int mid = (lo+hi+1)>>1;
            long cnt = 0;
            for (int i = 0, j = 0; i < A.length; i++){
                while(A[i] - A[j] > mid){
                    ++j;
                }
                cnt += i - j;
            }
            if (cnt <= k){
                lo=mid;
            }else{
                hi=mid-1;
            }
        }
        int[] ans = new int[k];
        for (int i = 0, j = 0; i < A.length && k > 0; i++){ // fill it.
            while(A[i]-A[j]>lo){
                ++j;
            }
            for (int s = j; s < i && k > 0; s++){
                ans[--k]=A[i]-A[s];
            }
        }
        while(k>0){ // fill the remaining with lo+1.
            ans[--k]=lo+1;
        }
        Arrays.sort(ans); // sort before return the answer.
        return ans;
    }
```

---------

[Google | Phone Screen](https://leetcode.com/discuss/interview-question/2023628/Google-or-Phone-Screen)

Calculate the total wait time for a customer  `C`  to speak to an agent given  `N`  agents,  `M`  customers, and  `T[]`  time for an agent to serve a customer.  `T[i]`  represents the amount of time it takes for an agent  `i`  to serve one customer. One agent can serve one customer at a time. All  `N`  agents can serve concurrently. The customer chooses the agent with the lowest wait time.

Examples:

```
N = 2
M = 2
T = [4, 5]
First customer chooses agent 1. Second customer chooses agent 2.
Customer C will wait 4 minutes.

```

```
N = 2
M = 4
T = [4, 5]
First customer chooses agent 1. Second customer chooses agent 2.
Third customer chooses agent 1. Forth customer chooses agent 2.
Customer C will wait 8 minutes.
```

follow up questions:

1.  what if client number is far greater than agent number?
2.  what if there's a constraint on time[i] that 1 <= time[i] <= 10, how would you use this to your advantage?

如果client number少 那么可以用heap 如果client number大 那么可以用二分+check    
time限制可以压缩数组成一个长度为10的 加快计算

My solution using 2 approaches (priority queue and binary search) - read the comments for better understanding

1.  Using priority queue

```
int totalWaitTime(int n, int m, vector<int>& times) {
    // there are more number of agents than customers
    if (n > m) {
        return 0;
    }

    priority_queue<pair<int,int>, vector<pair<int, int>>, greater<pair<int, int>>> pq;
    for (int i = 0; i < times.size(); i++) { // O(nlogn)
        pq.push({0, i});
    }

    for (int i = 1; i <= m; i++) { // m * log(n)
        pair<int, int> curr = pq.top(); pq.pop();
        int endTime = curr.first;
        int index = curr.second;
        // if two agents become free at the same time then one of them will be picked randomly - since we are only interested in the wait time 
        // for the customer but not how early they finish. Finishing early can be made the second priority when end times are equal by pushing
        // {endTime, times[i], i} -> priority order => endTime > times[i] > i (if one is equal the least of others will be picked)
        pq.push({endTime + times[index], index});
    }

    // we can also return pq.top().second for the agent to which this customer is assigned
    return pq.top().first;
}
// Time complexity - O((n + m) logn)
// Space complexity - O(n) for priority_queue

```

2.  Using binary search

```
int totalWaitTime(int n, int m, vector<int>& times) {
    // there are more number of agents than customers
    if (n > m) {
        return 0;
    }

    int min_time = 0, max_time = *max_element(times.begin(), times.end());

    // wait time will be in this range because in the worst case there will be only one agent with max_time and the 
    // customer needs to wait for them
    int low = min_time, high = m * max_time;
    while (low <= high) {
        int mid = low + (high - low) / 2;
        int sum = 0;
        // if the agent times are in the range [1, 10] then we can store the frequencies in a map and use them to compute the sum
        // in constant time since in the worst case we will only look at 10 different times - sum += mp[time] * (mid / time) for all
        // times in the map
        for (int time: times) {
            sum += (mid / time);
        }

        if (sum == m) {
            return mid;
        }

        if (sum > m) {
            high = mid - 1;
        } else if (sum < m) {
            low = mid + 1;
        }
    }

    return -1;
}
// Time complexity - n * log(m * logm) - this can be used when the number of customers are far larger than the number of agents
// Space complexity - O(1)
```

---------------------

[Google Onsite L4](https://leetcode.com/discuss/interview-question/1533097/Google-Onsite-L4)

I received this question below in one of my onsite interviews at Google. Although was able to solve it, however the time complexity of the solution came out to be O(N^2).  
I'm looking for alternate solutions with time complexity less than O(N^2).

Problem :

```
A long running webserver is writing to a log file, one request summary per line. 
Here is an example file: 

# timestamp(millis), URL, status, processing time
1000001, /index.html, 200, 150 
1000002, /article/1234.html, 500, 1 
1000005, /index.html, 200, 50 
1001000, /article/4321.html, 200, 10

Return all the input timestamp but associated with the number of requests being processed at the time of the timestamp.

Output :
1000001 --> 1
1000002 --> 2  (since the first process is still running, timestamp 1000002 would have two processes running)
1000005 --> 2  (since the first process is still running, timestamp 1000005 would have two processes running)
1001000 --> 1
```
-----------------

[Google OA For FTE](https://leetcode.com/discuss/interview-question/1402524/Google-OA-For-FTE)

Given a tree and values(B[i]) for each node in the tree, find for every node, the least non-negative integer that **does not** occur in its subtree. N<=10^5, B[i] <= 10^9.

刚开始肯定是1 然后慢慢增加 如果新增加的在子树中那么继续增加 这里用heap来维护一个最小值 每次合并的时候都是把左右子树中节点数少的合并到大的中 这个显而易见 因为都是合并 所以肯定少的合并到大的划算 时间复杂度是nlogn 假设树是平衡的 那么每次合并的节点数是 1 3 7
2n+1 合并次数是logn次 所以根据 等差数列求和公式 计算出是nlogn

A simple yet powerful (and quite clever honestly) trick: instead of creating a new set for a node, use the larger of the 2 children sets (left and right) and copy over elements from the smaller set and the node's value to the larger set. This ensures that the instances when a node gets copied over from one set to another during processing nodes in its ancestral path is only if other subtree's size was larger. For any node, this could happen atmost O(log n) times in a tree of size n. This way, our worst case input becomes a complete tree and the worst case time complexity becomes O(n log n). This trick is similar in spirit to [quicksort trick of reducing space to O(log n)](https://en.wikipedia.org/wiki/Quicksort#Space_complexity).

---------

[Google Phone Screen rejected](https://leetcode.com/discuss/interview-question/1400286/Google-Phone-Screen-rejected)

I recently gave a phone screen interview at Google. The question was:

You have a set of logs from users (something like commit logs from users)

```
Message type <username> Message

e.g. Preamble <bob> code check in
	 Commit 2 <alice> change variables
	   ......

```

The goal is to find the top user by word count on the message. The structure is fixed: the name is encapsulated within brackets and then the messgae starts. A word is defined by a sequence of alphanumeric characters. Since it is picking the top user, I proposed a map based approach and parsing the message line using 2 pointers to get the user and word count. I did not feel heap would help since it is maximum. What is a good way to solve this apart from dictionary storage?

答案:
For just maximum word count, you might calculate by greedy i guess,  
If follow up might change top N users PriorityQueue would be elegant.

Yeah in that case I think my implementation might have been slow or something else as negative signal (there was no follow up time left although I did menion heaps when discussing but felt unnecessary since we are doing 1 retrieval of max) since I followed the greedy approach and finished the coding within 30 mins.

--------------

[Google Questions](https://leetcode.com/discuss/interview-question/1371222/Google-Questions)

You are given an array A representing heights of students. All the students are asked to stand in rows. The students arrive by one, sequentially (as their heights appear in A). For the i-th student, if there is a row in which all the students are taller than A[i], the student will stand in one of such rows. If there is no such row, the student will create a new row. Your task is to find the minimum number of rows created.

Write a function that, given a non-empty array A containing N integers, denoting the heights of the students, returns the minimum number of rows created.

For example, given A = [5, 4, 3, 6, 1], the function should return 2.

Students will arrive in sequential order from A[0] to A[N−1]. So, the first student will have height = 5, the second student will have height = 4, and so on.

For the first student, there is no row, so the student will create a new row.

Row1 = [5]

For the second student, all the students in Row1 have height greater than 4. So, the student will stand in Row1.

Row1 = [5, 4]

Similarly, for the third student, all the students in Row1 have height greater than 3. So, the student will stand in Row1.

Row1 = [5, 4, 3]

For the fourth student, there is no row in which all the students have height greater than 6. So, the student will create a new row.

Row1 = [5, 4, 3]

Row2 = [6]

For the fifth student, all the students in Row1 and Row2 have height greater than 1. So, the student can stand in either of the two rows.

Row1 = [5, 4, 3, 1]

Row2 = [6]

Since two rows are created, the function should return 2.

Assume that:

N is an integer within the range [1..1,000]

each element of array A is an integer within the range [1..10,000]

In your solution, focus on correctness. The performance of your solution will not be the focus of the assessment

------------------

[google interview Experience](https://leetcode.com/discuss/interview-question/1161158/google-interview-Experience)

Question related to min heap.  
Print Top k chatty persons in a chat, log file.  
how to identify the top chatty person:  
by count of number of words  
chat format :  
< Jake >Hello!!There  
< Andrew >How Are!! You?  
.... so on

No of words  
Jake - > 2  
Andrew - > 3

You cannnot split by a space  and word count not length of string count should be computed

维护一个长度为k的heap

------------

[Microsoft OA questions](https://leetcode.com/discuss/interview-question/2237562/Microsoft-OA-questions)

https://leetcode.com/discuss/interview-question/1768686/Microsoft-OA-Codility

Given an array with revenue and expenses of a company (revenues are positive items in array, expenses are negative items) you can relocate expenses to the end of the array to make sure that in each point in time, the sum does not become negative. Return min number of relocations needed

每次当出现负数时 就把之前的最小的负数放到最后面

---

[How to solve this problem?](https://leetcode.com/discuss/interview-question/2788638/How-to-solve-this-problem)

![image](https://assets.leetcode.com/users/images/7c8f3c55-bb7c-43a0-87a9-bb23ca989a5d_1667819981.70409.png)
![image](https://assets.leetcode.com/users/images/68a67e43-3a8c-4370-8b27-eaea5bd98003_1667819981.4122598.png)

思想类似上题

-----

[Amazon | OA | Maximum Quality](https://leetcode.com/discuss/interview-question/1641829/Amazon-or-OA-or-Maximum-Quality)

You are given a list of packets of varying sizes and there are  `n`  channels.

-   Each of the  `n`  channel must have a single packet
-   Each packet can only be on a single channel

The quality of a channel is described as the  `median`  of the packet sizes on that channel. The total quality is defined as sum of the quality of all channels (round to integer in case of float). Given the  `packets []int32`  and  `channels int32`  find the maximum quality.

Sort the packets array and added packet size to the answer till the last channel.  
For the last channel, calculated the median of the remaining packets and added to the answer.
证明看notes
如果是inline的话 也可以做 维护一个长度为n-1的小根堆代表n-1个pocket 最后一个pocket则需要使用两个heap来维护中位数(295) 当一个新的元素来的时候 加入heap 然后弹出最小的元素 放去最后一个pocket

-------

[Tiktok OA](https://leetcode.com/discuss/interview-question/2646621/Tiktok-OA)

![image](https://assets.leetcode.com/users/images/b49463ea-ab4a-4344-80ce-c818a7bf797a_1664640163.799659.png)
类似于k个升序链表

--------

[Google Interview Question 2022](https://leetcode.com/discuss/interview-question/2774418/Google-Interview-Question-2022)

You are given an array of 5 shards. Each shard is on a server (server1, server2, etc.). The shards array contains information on which server each shard is on. For example:  
shards = [server2, server1, server1, server2, server0]  
This means that shard 0 and 3 are on server2, shard 1 and 2 are on server1, and shard 4 is on server0.

Sometimes, servers go down, and shards need to be reassigned in a load balanced way. For example, if server1 goes down, the shards array should change to look like this:  
shards = [server2, server2, server0, server2, server0]. (The order of which shards are reassigned to which server doesn't matter, but there should be minimal shard movement between servers (no moving shards between server2 and server0, and the shards per server should be approximately balanced)  
Given this shards[] array, design an algorithm that modifies shards[] when a server goes down.

-----

[TikTok OA](https://leetcode.com/discuss/interview-question/2776384/TikTok-OA)

![image](https://assets.leetcode.com/users/images/f5aa9f4a-bc79-4df5-bd0a-7a9c2efa2c7c_1667541431.8956788.png)

先使用扫描线 对起点和终点进行排序 然后记录每一个区间有多少tasks在里面 然后按照tasks的数量放入大根堆 每次取出一个元素 把元素尽量放入当前的区间 如果当前task没有时间了 那么直接把task删除 如果当前区间没有task了 那么不继续放入大根堆

----

[McKinsey CGI Intern OA (Explanations appreciated)](https://leetcode.com/discuss/interview-question/2837828/McKinsey-CGI-Intern-OA-%28Explanations-appreciated%29)

![image](https://assets.leetcode.com/users/images/cd3c0c6b-a9e9-4691-9f1e-aace792c5309_1669087294.1371548.jpeg)
![image](https://assets.leetcode.com/users/images/50bea937-b7f4-4674-ba57-8772963ba103_1669087325.0939631.jpeg)

简单heap

----

[GOLDMAN SACHS/OA HARD/ ON CAMPUS](https://leetcode.com/discuss/interview-question/2865178/GOLDMAN-SACHSOA-HARD-ON-CAMPUS)

![image](https://assets.leetcode.com/users/images/3714b198-1c16-4edb-a942-65c466b407b2_1669874754.7859695.png)
![image](https://assets.leetcode.com/users/images/e7d6b1e1-b85d-42ac-8d46-d298c6391ff6_1669874762.2140949.png)
![image](https://assets.leetcode.com/users/images/44f4dce0-36f6-4b6d-8c38-709c76ac5bf2_1669874768.2077923.png)
![image](https://assets.leetcode.com/users/images/6149a5c8-6f23-48a4-8af0-fe5b8ee12154_1669874774.9237168.png)

-----

[Uber | SDE 2 | Onsite](https://leetcode.com/discuss/interview-question/2992102/Uber-or-SDE-2-or-Onsite)


<!--stackedit_data:
eyJoaXN0b3J5IjpbNzA5NjE5MDE3LC0xMzg2MzY3OTk1LDExNz
YxNDkxNzEsMjE0MjQ3MTg1LDk2ODExODk5NiwtNzE2MjU1NTEy
LDEwNzYxNzE2MDYsMTAzNDg4MzUwM119
-->