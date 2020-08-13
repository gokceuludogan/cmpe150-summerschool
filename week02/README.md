##  Loops

### Question 1 - Staaaars

#### Question 1a
Write a program that prints 1 star ('*') to the screen.

#### Question 1b
Write a program that prints 10 stars ('*') next to each other to the screen.

#### Question 1c
Write a program that reads an integer N and prints N stars ('*') next to each other to the screen.

#### Question 1d
Write a program that reads an integer N and prints N stars ('*') vertically to the screen.


<br />

### Question 2 - Numbeeeers

Write a program that reads an integer N and prints numbers from 1 to N to the screen.

|  INPUT  |  OUTPUT |
|:-------:|:-------:|
| 5  | 1 2 3 4 5   |
| 2  | 1 2  |

<br />

### Question 3 - Hooping Numbers

Write a program that reads 3 integers A, B and t from the user. Then prints numbers from B to A with decrement of t.

|  INPUT  |  OUTPUT |
|:-------:|:-------:|
| 7 16 3  | 16 13 10 7 |
| 2 30 6  | 30 24 18 12 6 |

<br />

### Question 4 - Even Numbeeeers

Write a program that reads two integers A and B. Then prints the sum of even numbers between A and B. Assume that B > A.

|  INPUT  |  OUTPUT |
|:-------:|:-------:|
| 3 8  | 10 |
| 2 13 | 40  |
| 3 5 | 4  |

<br />

### Question 5 - Stuck Between Chars

Write a program that takes two characters from user and displays characters between them.

|  INPUT  |  OUTPUT |
|:-------:|:-------:|
| a e  | a b c d e |
| b c | b c  |

<br />

### Question 6 - Average Team

Write a program that reads a number N, then reads N more numbers. Calculate the average of those N numbers.

|  INPUT  |  OUTPUT |
|:-------:|:-------:|
| 4<br>4 9 5 2  | 4.00 |
| 1<br>8 | 8.00  |

<br />

### Question 7 - Boom Boom POW

Write a program that takes 2 integers a and b, then prints the result of a^b (a\*a\*a...\*a\*a). 

|  INPUT  |  OUTPUT |
|:-------:|:-------:|
| 3 4  | 81 |
| 2 10  | 1024 |

<br>

### Question 8 - Fibonacci

Write a program which reads a positive integer number N , and prints the Nth fibonacci number. *0, 1, 1, 2, 3, 5, ...* 

F_0 = 0, F_1 = 1, F_n = F\_(n-2) + F\_(n-1)

|  INPUT  |  OUTPUT |
|:-------:|:-------:|
| 2  | 1 |
| 4  | 2 |
| 7  | 8 |

<br />

## Until Loops

### Question 1 - Digiiiits

Write a program that takes a number and prints its total digit count and also even digit sum.

|  INPUT  |  OUTPUT |
|:-------:|:-------:|
| 542175 | 6 6 |
| 24680 | 5 20 |
| 135 | 3 0 |

<br>

### Question 2 - Positive Mental Attitude

Write a program that will take integers as inputs until the user enters a negative number. Then shows the user the sum of all ODD non-negative numbers that is entered.

|  INPUT  |  OUTPUT |
|:-------:|:-------:|
| 4 7 45 9 2 0 0 5 8 -4  | 66 |
| 1 1 0 1 -1 | 3 |

<br>

### Question 3 - NoBig

Write a program that reads numbers until the entered number is greater than the previous entered number. Then print the average of all entered numbers except the last one. (with two decimal places) (At least two numbers will be entered)

|  INPUT  |  OUTPUT |
|:-------:|:-------:|
| 5 4 3 3 8 | 3.75 |
| 5 4 3 3 8 7 5 9 | 3.75 |
| 1 2 | 1.00 |
| 100 54 46 2 3 50| 50.50 |

<br />

## Nested Loops

### Question 1 - R\*\*\*tangle

#### Question 1a
Write a program which takes two positive integers as N and M then prints a rectangle with size NxM. 

| Input | Output                               |
| :---: | ------------------------------------ |
|  3 4  | \*\*\*\*<br />\*\*\*\*<br />\*\*\*\* |
|  2 6  | \*\*\*\*\*\*<br />*\*\*\*\*\*        |


#### Question 1b
Write a program which takes two positive integers as N and M then prints a rectangle with size NxM which has stars (*) at borders, and lines (-) inside.

| Input | Output                                              |
| :---: | --------------------------------------------------- |
|  3 3  | \*\*\*<br />\*-\*<br />\*\*\*                       |
|  4 5  | \*\*\*\*\*<br />*---\*<br />\*---\*<br />\*\*\*\*\* |


<br>

### Question 2 - TriNumber

#### Question 2a
Write a program to display a right angle triangle using the number N, which will repeat the number for that row, like below.

| Input | Output                                  |
| :---: | --------------------------------------- |
|   3   | 1<br />22<br />333                      |
|   5   | 1<br />22<br />333<br />4444<br />55555 |


#### Question 2b
Write a program to display a right angle triangle with N number of rows, like below.

| Input | Output                                  |
| :---: | --------------------------------------- |
|   3   | 1<br />12<br />123                      |
|   5   | 1<br />12<br />123<br />1234<br />12345 |

<details><summary>Hint</summary> At each row, we iterate from 1 to the row number.</details>

#### Question 2c
Write a program which takes two integer as N and x and display a right angle triangle with N number of rows formed by powers of x as follows:

| Input | Output                                |
| :---: | ------------------------------------- |
|  3 4  | 4<br />4 16 <br />4 16 64             |
|  4 3  | 3<br />3 9<br />3 9 27<br />3 9 27 81 |

<details><summary>Hint</summary> At each row, we take power of input integer from once to the row number times.</details>

<br>

### Question 3 - TriLetter

Write a program which takes an integer as input and prints an upper triangle of letters as follows:

| Input | Output                                            |
| :---: | ------------------------------------------------- |
|   5   | A B C D E<br />B C D E<br />C D E<br />D E<br />E |
|   3   | A B C<br />B C<br />C                             |

<br>

### Question 4 - TriHard

Write a program which takes an integer N as input and prints a right triangle which consists of N many lines.

```
Input:
3

Output:
--*
-**
***

Input:
5

Output:
----*
---**
--***
-****
*****
```

<br />


### Question 5 - Sum Facts

Write a program which takes an integer as input and computes the sum of the factorial of each digit.  For example, assume that the user enters 572 as the input. For each digit of the integer, you will compute the factorial. Then you will compute the sum of these factorials: 5! + 7! + 2! = 120 + 5040 + 2 = 5162.

| Input | Output |
| ----- | ------ |
| 572   | 5162   |
| 27    | 5042   |

<br />

### Question 6 - Prime Example

#### Question 6a
Write a  program that reads a positive integer number and prints "Prime" to the screen if the entered number is a Prime number, otherwise "Prime Not".

#### Question 6b
Write a program which takes an integer as input and prints prime numbers up to that integer.

|  INPUT  |  OUTPUT |
|:-------:|:-------:|
| 11 | 2 3 5 7 |
| 15  | 2 3 5 7 11 13 |

#### Question 6c
Write a  program that reads two positive integer numbers and prints all the prime numbers between (inclusive) them. You may assume that the first entered number will always be smaller than the second number.

|  INPUT  |  OUTPUT |
|:-------:|:-------:|
| 3 22 | 3 5 7 11 13 17 19 |
| 1 3  | 2 3 |
| 32 36 | |


