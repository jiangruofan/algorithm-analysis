[Google | Onsite](https://leetcode.com/discuss/interview-question/1881879/Google-or-Onsite)

Q1. Given a table of rules, write a function to check if it contains conflicting rules. Two rules are conflicting if their conditions match but values do not. Conditions can contain don't cares denoted by '-'. Has to be done in O(n) time.

e.g  
Rule Conditions Value  
R1 C1,C2,C3 40  
R2 BCD1,BC5 40  
R3 BCD1,BC5 80  
Here, R2 and R3 conflict.  
e.g  
R1 C1,C2,C3 40  
R2 BCD1,BC5 50  
R3 BCD1,- 50  
R6 -,-,C3 40  
No conflicts.

简单字典树即可

------

[Google | Onsite | SWE](https://leetcode.com/discuss/interview-question/1394104/Google-or-Onsite-or-SWE)

Given some source code and a set of keyword substitutions, return the source code after performing all the substitutions. In other words, all occurences of a keyword X should be substituted by another keyword Y and multiple such pairs are provided.  
**A1**: This was a straightforward coding question; the interviewer was focused on code correctness and edge case handling and not on algorithmic complexity.

-----------

[Google onsite newgrad India](https://leetcode.com/discuss/interview-question/1403815/Google-onsite-newgrad-India)

Given a string and a list of offensive words, replace every occurence of the offensive word with word "Google".

**String ->**  I am cloud engineer working at Google. The Cloud stores a lot of data.  
**Offensive words ->**  ["cloud", "cloud engineer"]

**Output ->**  I am Google working at Google. The Google stores a lot of data.

**Related Question ->**  [Add Bold Tag in String](https://leetcode.com/problems/add-bold-tag-in-string/)

------------

[Google Phone](https://leetcode.com/discuss/interview-question/1454657/Google-Phone)

_find strings that start with a prefix from a list of strings.  
data: apple, bag, ankle, antelope, bar , art, bat  
“a” -> apple, ankle, art, antelope  
“ap” -> apple_

-------------

[Google Phone Screen](https://leetcode.com/discuss/interview-question/1350418/Google-Phone-Screen)

Given a list of words. Two words w1 and w2 are said to form a chain w1->w2 if w1 is prefix of w2 and len(w2) = len(w1) +1. Eg. abc -> abcd would form a chain. Find the longest chain from the list of words. Print the length as well as the chain.  
Eg. ["den","ben", "dent", "dew", "dents"]  
Here the longest chain is "den" -> "dent" -> "dents"

类似题目 1048. Longest String Chain

------------

[Google Intern question](https://leetcode.com/discuss/interview-question/1001136/Google-Intern-question)

Given a string S (0<S.size()<10^5) and list of strings ls (0<ls[i].size()<10^5 and also given that 0< for all i sum(ls[i].size())<10^5). we have to find number of ways to make S from given list of strings. We can repeat a string from given list any number of times.  
Example -  
S - abab  
ls - [a,b,ab]  
ans = 4  
explanation - [a+b+a+b, a+b+ab, ab+a+b, ab+ab]  
Can anyone tell how to do this with given constraints?

字典树+DP

-----------

[Google | Phone screen | Design a dictionary with at most 1 typo](https://leetcode.com/discuss/interview-question/281470/Google-or-Phone-screen-or-Design-a-dictionary-with-at-most-1-typo)

https://leetcode.com/discuss/interview-question/643158/Google-or-Phone-or-Faulty-Keyboard

Design a vocabulary class that allows for a maximum of one typo. It has one method: given a word, it verifies if the word can be found in the vocabulary with at most one character substitution.

```
Example : Vocalubary : ['apple', 'banana', 'orange']

atMostOneTypo("banana") -> should return true
atMostOneTypo("banena") -> should return true
atMostOneTypo("banan") -> should return false
atMostOneTypo("banxnn") -> should return false
```
类似题目: [676. Implement Magic Dictionary](https://leetcode.cn/problems/implement-magic-dictionary/)

------------

[Google interview question](https://leetcode.com/discuss/interview-question/592856/Google-interview-question)

https://leetcode.com/discuss/interview-question/345065/Google-or-Word-Extensions

Part 1:  
Input string can contain some repeated characters, for example 'helllooo'  
If a string has three or more continuous repeated characters, then that means its has an extension. Return the start and end of all such extensions in a string.  
Example:  
String: 'helllooo'  
Output: I created a class and returned list of that class.

```
class Extension {
  int start;
  int end;
 }

```

so output is: List of Extension class and empty/null if there are no extensions.

Part 2:  
Using the input string, output of the first part and a dictionary of valid words, return if the input word can be converted to one of the valid words by removing some extensions (cannot delete the char).  
Example:  
Input: 'helllooo'  
Dictionary: {'hello', 'car', 'bat' }  
Since we can convert the word: 'helllooo' by removing 1 extension of 'l' and 2 extension of 'o' to 'hello', so return true.

Note: it was given that any valid word will not have 3 or more repeated chars.

下面这道题 是求数量 不用字典树
https://leetcode.com/discuss/interview-question/455534/Google-or-Phone-or-Expressive-Words

Had a phone screen with Google. After formal introduction, the interview started:

The initital problem was that given an original word e.g. "Hello" and an expressive word "Heeeellooo", return the starting and ending index of repeating charcters which are not present in original string. For example, "e" is being repeated three times and "o" is being repeated two times so you have to return [["e", 2, 4], ["o", 8, 9]]

Follow up:  [https://leetcode.com/problems/expressive-words/](https://leetcode.com/problems/expressive-words/)

I got extremely nervous and totally embarrassed myself. Failed the interview.

The interviewer was from Cloud team.

-----------

[Google Ads Phone Interview | File Directory Question](https://leetcode.com/discuss/interview-question/2615209/Google-Ads-Phone-Interview-or-File-Directory-Question)

All files

/a/b.txt  
/a/c.txt  
/p/q/r.txt  
/p/q/s.txt  
/b/c/d.txt  
/s/t  
/t

Selected Files  
/a/b.txt  
/a/c.txt  
/p/q/r.txt  
/b/c/d.txt

Output :

/a  
/p/q/r.txt  
/b/c

Explanation :

Initially , all files are provided thru all files list ( nature of input being list of directory paths in string, i.e, ArrayList). Selected files is another list of string (directory/subdirectory path of a file).

First output is /a because , both in all files and selected list, /a directory has same set of .txt files.

Second output is /p/q/r.txt because , we generally prioritise the selected list, whatever is there , needs to be exactly same in all files list, by any chance , all files has any mismatch or any file more or less , whatever file path in selected list, needs to be printed out in output .

Third output is , /b/c because the remaining paths/files are similar .

答案:
第一步 构造字典树 第二步对selected file进行扫描 打上标记
第三步 对整个字典树进行遍历 如果某一个节点的子节点都存在标记 那么可以进行截断 对于每一个节点 返回两个值 第一个值表示是否所有子节点都存在标记 第二个节点表示所有子节点的路径

------------------

[Uber || SDE Intern || OA](https://leetcode.com/discuss/interview-question/2332185/Uber-oror-SDE-Intern-oror-OA)

[https://www.hackerrank.com/challenges/no-prefix-set/problem](https://www.hackerrank.com/challenges/no-prefix-set/problem)

简单字典树判断

---------

[Media.Net(Directi) OA On campus Questions](https://leetcode.com/discuss/interview-question/2639890/Media.Net%28Directi%29-OA-On-campus-Questions-:%29)

![image](https://assets.leetcode.com/users/images/82a0d721-0f49-4e90-9ad9-0d2d2633ce3d_1664476850.9125116.png)

字典🌲 + 最近公共祖先判断 

---

[HRT Code Signal Question](https://leetcode.com/discuss/interview-question/2846303/HRT-Code-Signal-Question)

I recently got this as my final question with 7 minutes left on my HRT OA, I don't exactly remember the exact details but here goes.

You are given a array of strings,  **arr**  and your task is to return the number of strings which fulfill the given condition

-   0 <=j < i < arr.length
-   arr[j] == arr[i] or arr[i] starts with arr[j] or arr[j] starts with arr[i]

```
arr = ["back", "backdoor", "background", "ground", "yard", "backyard", "groundwater"]
/*
back and backdoor
back and background
back and backyard
ground and groundwater
*/
ans = 4
```

This questions seems familar, but I couldn't seem to find it anywhere, does anyone know which question this was? I want to try to solve it again with more time.

I solved it quickly with O(n^2) for the points, but it TLE for the last 5 hidden testcases, my next approach would be to make a trie, but I haven't touch Trie in Python, I mostly program in Javascript and Java. OA was locked to Python or C++.

The questions given were 1 leetcode easy, 2 mediums, and this question.  
One of the notable medium question was creating a UI screen with given userWidth, screnWidth, and text message, which was time consuming.

[Uber OA | SDE-1 | New Grad | Dec 2022](https://leetcode.com/discuss/interview-question/2904947/Uber-OA-or-SDE-1-or-New-Grad-or-Dec-2022)

```
Q1 : Given an array of strings` words` find the number of, pairs where either the strings are equal or one string starts with another.
In other words, find the number of such pairs i, j (0 <= i < j < words.length ) 'that words[i] is a prefix Of' words [j] ,
or words [j] is a prefix of words[i].

Examples : 
words = { "back", "backdoor", "gammon", "backgammon", "comeback", "come", "door" }
Output : 3

words = {"abc", "a", "a", "b", "ab", "ac"}
Output : 8
```

-----

[Google | SWE - SRE](https://leetcode.com/discuss/interview-question/2910244/Google-or-SWE-SRE)

file operations:  
this was a bit wierd question seems like forcefully made type of question.

Given a list of all files. minimize the output by consolidating the directory if all files of that directory is selected  
example:  
assume-  
a  
- a.txt  
- b  
- a.txt  
- b.txt  
- c  
- z.txt  
- k.txt  
all files would be  
-/a/a.txt  
-/a/b/a.txt  
-/a/b/b.txt  
-/a/c/z.txt  
-/a/c/k.txt

if selected file would be

-   /a/a.txt
-   /a/b/a.txt
-   /a/b/b.txt  
    output  
    -/a/a.txt  
    -/a/b (as all files from a are selected)

It get too complex when there is more nesting.  
I started wit some set type of solution then I realized I was in wrong direction.

I tried implement to tree but unable to get to the solution. any one can help sovling this problem.

-----
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEzNzY5MTgzODgsMzE2ODI2MjczLDE5MD
M5MTA2OTMsLTE0MTQyNjcyNzksLTc1OTI3NjUyN119
-->