### Warm Up Question - Rook and Pawns
Write a program which reads a chessboard as an 8x8 matrix from the user. In the chessboard, there will be one rook (kale) represented by integer: 8, and multiple pawns (piyonlar) represented by integer: 1. The rest will be empty: 0.

The rook will capture the closest possible pawn. Your program should print the chessboard to the screen after the capture. 

```
Input               Output
0 0 0 0 0 0 0 1     0 0 0 0 0 0 0 1
0 0 0 0 1 0 0 0     0 0 0 0 1 0 0 0
0 0 8 0 0 0 0 1     0 0 0 0 0 0 0 1
0 1 0 0 0 0 0 0     0 1 0 0 0 0 0 0
0 0 1 0 0 0 0 0     0 0 8 0 0 0 0 0
0 0 0 0 0 0 0 0     0 0 0 0 0 0 0 0
0 0 0 0 0 0 0 0     0 0 0 0 0 0 0 0
0 0 0 0 0 0 0 0     0 0 0 0 0 0 0 0
```

## Strings

### Question 1 - Length 

* Write a function that computes the length of a given string.

|  INPUT  |  OUTPUT |
|-------|-------|
| hello world | 12 |

Hint: Try using strlen function from string.h library.

### Question 2 - Copy

Write a function that copies a source string to the destination string. You can assume that (you should ensure that) destination string is large enough.

*Try using `strcpy` function from `string.h` library.*

### Question 3 - Compare

Write a function that takes two strings as argument and compares them. The function should perform what `strcmp` function from `string.h` library. Validate your function by using `strcmp` along with your function.

```
input: abz abc 
output: 23
```

### Question 4 - Count Words

Write a program to count the total number of words in a string.

```
input: count the total number of words in a string
output: 9
```

### Question 5 - nth Word

**a.** Write a program which takes a string and an integer n as parameters and print the nth word in the string. 

```
input: count the total number of words in a string 3
output: total
```

**b.** Write a program which takes a string and an integer n as parameters and deletes the nth word in the string. 

```
input: count the total number of words in a string. 3
output: count the number of words in a string.
```

<details><summary>Figure</summary><img src="q4_1.png"/></details>

### Question 6 - Frequentt

**a.** Write a program to find maximum occurring character in a string assume all characters in lowercase.

```
input: she borrowed the book
output: o
```

**b.** Update your program so that it would work with all characters not only lowercase ones.

*Hint: What's the size of ASCII table?*

### Question 7 - Exclude

Write a program which reads a sentence as a string, and a word as a string. Then the program should exclude this word from the sentence if the sentence contains the word, then print the new version to the screen. Assume no punctuation will occur, and every letter is lower case.

```
input: merhaba dunyali nasilsin dunyali
output: merhaba nasilsin
```

![](q6.png)

### Question 8 - Sort

Write a program which takes a string as parameter and sorts words of this string and prints the resulting string. Assume initial string has maximum 100 characters and the length of each word is at most 10. 

```
input: the lake is a long way from here
output: a from here is lake long the way
```

<details><summary>Words</summary><img src='1576784076412.png'/></details>

### Extra: String to Lowercase

* Write a program to take a string from the user, and convert it into lowercase. 

|  INPUT  |  OUTPUT |
|-------|-------|
| All the Single Ladies!! | all the single ladies!! |