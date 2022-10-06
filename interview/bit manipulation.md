[Google Online Assessment Question](https://leetcode.com/discuss/interview-question/2324457/Google-Online-Assessment-Question)

You are given a matrix A having N rows and M columns. The rows are numbered from 1 to N from top to bottom and columns are numbered from 1 to M from left to right. You are allowed to move right and down only, that is if you are at cell (i, j), then you can move to (i+1, j) and (i, j+1). You are not allowed to move outside the matrix.

Your task is to find the number of  **good path**  starting from (1,1) to (N,M).  
**Good Path**: If the sum of all the elements that lie in the path is divisble by K, then the path is considered as good.

**Constraints**  
1 <= N, M <= 16  
1 <= Ai, K <= 10^18

**Sample Input**  
3  
3  
23  
1 2 3  
4 5 6  
7 8 9

**Sample Output**  
1

**Explanation**  
N = 3, M = 3, K = 23  
1->2->5->6->9, Sum is 23 which is divisble by 23 and there is only one good path in the above sample matrix, So the output is 1.

答案: 
This can be done using  _meet-in-the-middle_  technique. The length of the path is n+m-1. Hence we first recurse from starting position till half the length of path and then recurse from ending position for the rest of the path length and add in the answer.  
Code:

```
[#include](https://leetcode.com/problems/minimum-interval-to-include-each-query) <bits/stdc++.h>
#define int long long
using namespace std;
int n,m,k,half,ans;
unordered_map<int,int> arr[21][21];
vector<vector<int>> a;
void recurse(int x, int y, int pathSum, int length){
    pathSum += a[x][y];
    pathSum%=k;
    if (length==half) {
        arr[x][y][pathSum]+=1;
        return;
    }
    if (x+1<n) recurse(x+1,y,pathSum,length+1);
    if (y+1<m) recurse(x,y+1,pathSum,length+1);
}
void recurseBack(int x, int y, int pathSum, int length){
    if (length==n+m-2-half) {
        if (pathSum==0)
            ans += arr[x][y][pathSum];
        else 
            ans += arr[x][y][k - pathSum];
        return;
    }
    pathSum += a[x][y];
    pathSum%=k;
    if (x-1>=0) recurseBack(x-1,y,pathSum,length+1);
    if (y-1>=0) recurseBack(x,y-1,pathSum,length+1);
}
signed main(){
    cin>>n>>m>>k;
    half = (n+m-2)/2;
    ans = 0;
    for (int i=0;i<n;i++){
        vector<int> temp(m,0);
        for (int j=0;j<m;j++) cin>>temp[j];
        a.push_back(temp);
    }
    recurse(0,0,0,0);
    recurseBack(n-1,m-1,0,0);
    cout<<ans<<endl;
}
```

时间复杂度应该是 2^24 或者 C(24,8)

--------------


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE1NTc2NjExNjJdfQ==
-->