[Google Onsite](https://leetcode.com/discuss/interview-question/1521932/Google-Onsite)

**Coding Round 1:**  
Given 2 images as a 2d matrix of size M_N And K_N. Find maximum overlapping part i. maximum bottom rows of first matrix which matches with the top rows of the second matrix  
Eg. Matrix 1  
[1,2,3,4]  
[3,4,2,5]  
[1,2,4,1]

Matrix 2  
[3,4,2,5]  
[1,2,4,1]  
[1,5,7,8]  
[7,5,7,3]

In above example answer is 2

对于每一列进行求出kmp的next数组 然后对于所有列取最小值
时间复杂度 m*n

------------

[Google | String Matching](https://leetcode.com/discuss/interview-question/399689/Google-or-String-Matching)

Had a phone interview with Google. The question asked was given below. Just asking Leetcode community the good optimal solution for this.

Suppose you have an array of strings 'src' and a string 'key':

```
src = {"minecraftgame", "intelligent", "innercrafttalent", "knife", "scissor", "stonecrafter"}
key = "craft"

```

Now return all the strings from the 'src' array that contains the key as substring in them. For example, for above case, the solution should be:

```
result = {"minecraftgame", innercrafttalent", "stonecrafter"}

```

Because all the result starings have key i.e. "craft" in them as substring

答案: kmp和rolling hash都可以

--------------


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTYzODI1MTU3N119
-->