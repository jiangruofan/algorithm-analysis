[Google | Algorithm](https://leetcode.com/discuss/interview-question/810747/Google-or-Algorithm)

Given a very large 2D character matrix of dimensions N x N (Here N is very large - of the order of 100000s)

For example, consider the below matrix:

a b c  
d e f  
g h i

If we print this matrix diagonally, then the output is:  
a b d c e g f h i

We also have a stream of short strings (each of the strings have length S)  
s0, s1, s2,...

say S = 3 and the stream has the following strings:  
abc, abd, gfh

Tell an efficient algorithm to tell which of the strings in this stream of strings occur in this diagonal traversal of this character matrix.

-----------

[UniSwap | OA | DFS Matrix traversal](https://leetcode.com/discuss/interview-question/3011356/UniSwap-or-OA-or-DFS-Matrix-traversal)

Given a rectangular matrix of English lowercase letters board and a string word, your task is to find the number of occurrences of word in the rows(→), columns(↓) and diagonals(↘) of board.

Example

```
For

board = [['s', 'o', 's', 'o'],
         ['s', 'o', 'o', 's'],
         ['s', 's', 's', 's']]

and word = "sos", the output should be solution(board, word) = 3.

There are 2 occurrences of word starting from board[0][0](going → and ↘), and one starting from board[0][2](going ↓).

No other occurrences of word were counted, so the answer is 3.

For

board = [['a', 'a'],
         ['a', 'a']]

and word = "aa", the output should be
solution(board, word) = 5.

There are 2 horizontal, 2, vertical, and 1 diagonal occurrence of word, for a total of 5.
```

-----

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE5Njk3NTk1MDEsLTEwNTc0NTYyNDVdfQ
==
-->