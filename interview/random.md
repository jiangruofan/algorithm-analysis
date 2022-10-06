[Google|Onsite|USA|feb-2022](https://leetcode.com/discuss/interview-question/1776950/GoogleorOnsiteorUSAorfeb-2022)
```
You have a list of cities and population. 
Write a function that returns a random city name by the probability of its sum of population. 
For example, in the following case, NY population is 14, total is 22. 
You should return NY with the probability of 14/22.

[NY, 9]
[SF, 1.5]
[Atlanta, 3]
[NY, 5]
[Boston, 1]
[SF, 3]
```
Q1 is [https://leetcode.com/problems/random-pick-with-weight/](https://leetcode.com/problems/random-pick-with-weight/)

------

[Google | Onsite | Song Shuffler](https://leetcode.com/discuss/interview-question/2337984/Google-or-Onsite-or-Song-Shuffler)

Problem Statement:  
**Given a playlist of songs, you have to design a song shuffler.  
This song shuffler is not like the normal song shuffler that shuffles the complete playlist at the start and returns a shuffled list, but instead when asked for a next song to be played, returns a random song from the list of songs.  
The next random song to be played should satisfy a condition that the song was not played in the last 'k' turns.  
You have to make sure, that at each call, all the eligible (not played during last k turns) songs have equal probability of being played next.**

For example:  
if  **songs = [A, B, C, D], k = 2,**  
then a possible random sequence of songs can be:

```
playNext: [ A , B , C , D ] ->  return C
playNext: [ A , B , _ , D ] ->  return A
playNext: [ _ , B , _ , D ] ->  return B
playNext: [ _ , _ , C , D ] ->  return C (as C was not played in the last two turns, it has an equal probability with D to be played).
```
删除一个元素和最后一个元素交换 力扣381

--------

[Google | Onsite](https://leetcode.com/discuss/interview-question/1971251/Google-or-Onsite)
Design a game 5x5. Given getRandom(start, end) function to generate all random numbers from 1 to 75

[[1, 5, 2, 8, 13] number random from 1 to 15  
[19,17,16,25] number random from 16 to 30  
[35,32,43,41,39] 31 to 45  
[etc...]

Create a void function which generate the game and return 2D array which contains game

no input (void function)  
output will be 2D array

----------------

[Google Onsite](https://leetcode.com/discuss/interview-question/1481051/Google-Onsite)

Given an array, create an array which contains these elements as well as their double and then do a random shuffle of this array. Ensure that in the shuffle  
the probability of occurrence of each permutation of the array is equal.

So, [1,2,3] -> [1,2,3,2,4,6] -> [1,6,3,2,2,4]

----------------


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEzODcyMzg3MzJdfQ==
-->