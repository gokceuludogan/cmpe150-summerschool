##  Data types & Operators

### Q1 - Triple Sum

Write a program that takes 3 integers from the user and then prints the sum of the numbers.

| INPUT  | OUTPUT |
| ------ | ------ |
| 3 4 5  | 12     |
| 2 2 4  | 8      |
| 1 9 15 | 25     |

### Q2 - Rectangle

Write a program that reads two integers as the side lengths of a rectangle. Then outputs the perimeter and the area of the rectangle.

| INPUT | OUTPUT |
| ----- | ------ |
| 3 5   | 16 15  |

### Q3 - Circle

Write a program that reads a float as the radius of a circle. Then outputs the circumference and the area of the circle. (pi = 3.14)

| INPUT | OUTPUT        |
| ----- | ------------- |
| 4.5   | 28.260 63.585 |

### Q4 - Average

Write a program that reads three integers from the user. Then outputs the average of these three numbers. (Hint: Type Casting)

| INPUT | OUTPUT |
| ----- | ------ |
| 2 3 5 | 3.33   |

### Q5 - Odd Enough

Write a program that takes 3 integer from the user and then prints the sum of odd numbers.

| INPUT  | OUTPUT |
| ------ | ------ |
| 3 4 5  | 8      |
| 2 2 4  | 0      |
| 1 9 15 | 25     |

### Q6 - Time Flies

Write a program to convert a given integer (in seconds) to hours, minutes and seconds.

| INPUT | OUTPUT |
| ----- | ------ |
| 25300 | 7 1 40 |
| 18000 | 5 0 0  |
| 155   | 0 2 35 |

## Characters

### Q1 - Number the Letter

Write a program which reads an upper-case char (character) from the user, then prints its rank in the alphabet.

| INPUT | OUTPUT |
| ----- | ------ |
| D     | 4      |
| G     | 7      |

### Q2 - What's Next?

Write a program which reads a character from the user. Print the 3rd character that comes after the input character.

| INPUT | OUTPUT |
| ----- | ------ |
| c     | f      |
| M     | P      |
| !     | $      |

### Q3 - Bigger is Better

Write a program which reads a lower-case char (character) from the user, then prints its upper-case version on the screen.

*Hint: Note that in the ASCII table, the distance between a lower-case letter and its corresponding upper-case version is the same for all letters.*

| INPUT | OUTPUT |
| ----- | ------ |
| d     | D      |
| t     | T      |

### Q4 - Characteristic Numbers

Write a program that reads two numeric **characters** and prints their multiplication.

| INPUT | OUTPUT |
| ----- | ------ |
| 9 8   | 72     |
| 1 3   | 3      |

```c
#include <stdio.h>

int main(){
    
    char ch1, ch2;
    scanf("%c %c", &ch1, &ch2);
    
    /*
    *  YOUR SOLUTION HERE
    *
    */

    return 0;
}
```

### Q5 - Is Digit?

Write a program that reads one character as input and print the digit itself if it is a digit else 0. 

| INPUT | OUTPUT |
| ----- | ------ |
| 7     | 7      |
| a     | 0      |

## Conditional Statements

### Question 1 - Positivity

#### Question 1a

Write a program that reads an integer. If the integer is positive then print "positive", if it is not then print "not positive".

| INPUT | OUTPUT       |
| ----- | ------------ |
| 4     | positive     |
| -5    | not positive |
| 0     | not positive |

#### Question 1b

Write a program that reads an integer. If the integer is positive then print "positive", if it is negative then print "negative", if it is zero then print "zero".

| INPUT | OUTPUT   |
| ----- | -------- |
| 4     | positive |
| -5    | negative |
| 0     | zero     |

#### Question 1c

Write a program that reads an integer. If the integer is positive then check if the number is odd or even and then print "odd" or "even", if it is negative then print the absolute value of the number, if it is zero then print "zero".

| INPUT | OUTPUT |
| ----- | ------ |
| 4     | even   |
| -5    | 5      |
| 0     | zero   |

### Question 2 - Divisible 

Write a program that will take 2 numbers from the user and if the first number is divisible by the second number, your code should print "it is divisible", if it is not divisible, then print "it is not divisible". If any of your numbers are nonpositive, print "Incorrect Input"

| INPUT  | OUTPUT              |
| ------ | ------------------- |
| 45 5   | it is divisible     |
| 45 6   | it is not divisible |
| -34 17 | Incorrect Input     |

### Question 3 - What am I to You

Write a program that will take 1 char from the user. If the char is a letter print "Lettuce", if the char is a digit (number) print "Durian", otherwise print "Nani!?"

| INPUT | OUTPUT  |
| ----- | ------- |
| 2     | Durian  |
| b     | Lettuce |
| !     | Nani!?  |

### Question 4 - Calculator

Write a basic calculator program (+, -, *, /). The program takes three inputs: float, char, float, then prints the result.

| INPUT  | OUTPUT |
| ------ | ------ |
| 1 + 45 | 46.00  |
| 1 - 45 | -44.00 |
| 1 * 45 | 45.00  |
| 1 / 45 | 0.02   |

### Question 5 - Leap Year

Write a program that takes year as input and prints whether a given year is a leap year or not.

| INPUT | OUTPUT          |
| ----- | --------------- |
| 2018  | Not a leap year |
| 2020  | a leap year     |

### Question 6 - Coordinate System

Write a program to accept a coordinate point in a XY coordinate system and determine in which quadrant the coordinate point lies.

| INPUT | OUTPUT                                         |
| ----- | ---------------------------------------------- |
| 5 7   | The point (5, 7) lies in the first quadrant.   |
| -2 -5 | The point (-2, -5) lies in the third quadrant. |

### Question 7 - Largest

Write a program that takes three integers and find the largest one.

| INPUT  | OUTPUT |
| ------ | ------ |
| 4 1 -3 | 4      |
| 5 19 2 | 19     |

### Question 8 - Chars from Hell

Write a program that reads a character. Prints upper-case version of the entered letter if it is a lower-case letter and vice versa. If it is a numeric character, then prints 2 times of the entered number as an integer. If not a letter or number then prints "asdfasdf".

| INPUT | OUTPUT   |
| ----- | -------- |
| d     | D        |
| B     | b        |
| 7     | 14       |
| .     | asdfasdf |