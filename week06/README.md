## Structures

### Question 1 - Distance

Define a **struct** representing a point (x, y). 

* write a function **distance** which takes two points and finds Euclidean distance between these points.  Use *pow()* and *sqrt()* functions from math library *`include <math.h>`*
* write a function which takes two points and returns the point closest to the origin. *Use the distance function.*

In main function, take two points from user and prints the coordinates of the point that is closer to the origin. 

| Input          | Output |
| -------------- | ------ |
| 3 0<br />0 4   | 3.00 0.00    |
| 11 7 <br />6 8 | 6.00 8.00    |

<br>

### Question 2 - Extreme Points

Write a program which takes an integer N and reads N points (given by their x and y coordinates) and determines the pair that is the farthest apart. 

*Use the point definition and distance function from the first question*


| Input                                        | Output        |
| -------------------------------------------- | ------------- |
| 3<br/>3 0<br/>0 0<br/>0 4                    | 3.00 0.00<br/>0.00 4.00   |
| 5 <br/>10 5<br/>4 8<br/>0 8<br/>4 5<br/>-1 2 | 10.00 5.00<br/>-1.00 2.00 |

<br>

### Question 3 - Moving Rectangle

Define a **struct** representing a rectangle that are parallel to the axes in a Cartesian coordinate system. Represent a rectangle by its lower left and upper right endpoints using the Point you defined. 

Write a function **move** which takes a rectangle pointer and two integers **moveX** and **moveY** representing the movement in the x and y axes respectively and moves the rectangle. 

**Example**:

* Rectangle:
  * lower left point: (2, 0)
  * upper right point: (8,  4)
* moveX: -5
* moveY: 2
* Resulting Rectangle:
  * lower left point: (-3, 2)
  * upper right point: (3,  6)

<br>

### Question 4 - Letter Grades

Define a **struct** representing a student having **student_id (integer), mt_grade (integer), final_grade (integer) and letter_grade (char)**. The given program takes the grades of students and creates structs for students. You are supposed to calculate and set the letter grades of students using **set_grade() function**. The grade weights are 40%, 60% respectively and letter grades are as follows:

* 100-75: A
* 74-50: B
* 49-25: C
* 24-0: F 

|  INPUT  |  OUTPUT |
|-------|-------|
| 2<br>100 40<br>40 100| 1000 B<br>1001 A |
| 3<br>45 25<br>100 100<br>0 90  | 1000 C<br>1001 A<br>1002 B |

```c
#include <stdio.h>

// Fill the definition of the struct.
typedef struct{
  
} Student;

void set_grade(Student *p){

}

int main(void){
    int N;
    scanf("%d", &N);
    Student cmpe[N];
    int i;
    for(i = 0; i < N; i++){
      scanf("%d %d", &cmpe[i].mt_grade, &cmpe[i].final_grade);
      cmpe[i].student_id = 1000 + i;
      // Call set grade function
    }

    for(i = 0; i < N; i++)
        printf("%d %c\n", cmpe[i].student_id, cmpe[i].letter_grade);

    return 0;
}
```

<br>

### Question 5 - Flights

Define a struct representing a flight which has following fields:

* Flight number (int)
* Originating airport code (three characters)
* Destination airport code (three characters)
* Starting time (int)
* Arrival time (int)

Write a function which reads a flight from user. 

Write a program that takes an integer N and then reads N flights. Then reads originating and destination airport code from user and lists all the planes that leave from the originating airport and arrive at the destination airport.

| Input                                                        | Output                                     |
| ------------------------------------------------------------ | ------------------------------------------ |
| 5<br/>3540 SAW ADB 14 15<br/>3440 IST ESB 13 15<br/>4041 ANT STL 13 21<br/>4045 GTG KPG 17 18<br/>ANT STL | 4041 ANT STL 13 21                         |
| 4<br/>3540 SAW ADB 14 15<br/>3543 SAW ADB 21 22<br/>3440 IST ESB 13 15<br/>4045 JFK IST 9 19<br/>SAW ADB | 3540 SAW ADB 14 15<br />3543 SAW ADB 21 22 |

*Hint: Write a function which reads a flight from user.*

<br>

### Question 6 - Sorted Flights

Write a program which takes an integer N and then reads N flights. Then sorts the flights according to their starting time and the originating airport code. 

*Use the definition and functions from the previous question* 

| Input                                                        | Output                                                       |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| 4<br />3540 SAW ADB 14 15<br/>3440 IST ESB 13 15<br/>4041 ANT STL 13 21<br/>4045 GTG KPG 17 18 | 4041 ANT STL 13 21<br/>3440 IST ESB 13 15<br/>3540 SAW ADB 14 15<br/>4045 GTG KPG 17 18 |

*Hint: Write a function for comparing two flights. It first checks the starting times and if they are equal then compares the originating airport codes. Funtion can return 1 if the first flight is greater, 0 if equal, -1 otherwise*

<br>

### Question 7 - Book Prices
Define a struct named: Book. Each book should have a name with exactly 3 letters (abbreviation). Each book should also have a page count (integer), and a price (integer).

Write a program which reads an integer n first, then read page counts, the names and prices of n books.

Write a function which takes an array of books, and sorts them according to their prices.

Using that function, your program should print the names and page counts of each book with the order of their prices. Like:

1. LOT: 528 pages (15 gold)
2. THG: 727 pages (32 gold)
3. MSB: 340 pages (120 gold)
4. etc..

Reading and printing format is up to you.

|  INPUT  |  OUTPUT |
|-------|-------|
| 3<br>727 THG 32<br>528 LOT 15<br>340 MSB 120| LOT: 528 pages (15 gold)<br>THG: 727 pages (32 gold)<br>MSB: 340 pages (120 gold) |

<br>

### Question 8 - Smaller Better Faster Stronger (2018 Fall Final Q4)
Mossy Land's department of science and technology started a competition to find the rectangle with the smallest area. All the participants submitted their rectangles. Then a group of scientists calculated edge lengths of each rectangle and send them to you. Your task is to find the rectangle with the smallest area.

You will write a function (min_rectangle_area) that takes two parameters (a Rectangle array and an integer) then returns a Rectangle.

**Input:**
* The first line of the input contains: N (1 <= N <= 100) the number of rectangles.
* The next N lines contains 2 numbers that describes the edge lengths of each rectangle: edge_1 edge_2. (0 < edge_1, edge_2 < 100000)

**Output:**
* The area of the rectangle that has the smallest area.


|  INPUT  |  OUTPUT |
|-------|-------|
| 2<br>2 5<br>3 4| 10.00 |
| 3<br>4.2 2.1<br>1.8 5.3<br>2 8.2  | 8.82 |
| 8<br>12 684<br>485 684<br>48 542<br>158 48<br>564 12<br>21 188<br>126 441<br>1200 1450 | 3948.00 |
| 4<br>1.1 2.2<br>2.2 3.3<br>1.1 3.3<br>1.1 2.2 | 2.42 |


```c
#include <stdio.h>

typedef struct rectangle{
    float edge1;
    float edge2;
}Rectangle;

// DO_NOT_EDIT_ANYTHING_ABOVE_THIS_LINE

// DO_NOT_EDIT_ANYTHING_BELOW_THIS_LINE

int main(){
    Rectangle r_min;
    int i;
    int N;
    Rectangle r[100];
    
    scanf("%d", &N);

    // Reads Rectangles
    for(i = 0 ; i < N ; i++)
        scanf("%f %f", &r[i].edge1, &r[i].edge2);
    
    r_min = min_rectangle_area(
    // DO_NOT_EDIT_ANYTHING_ABOVE_THIS_LINE

    // DO_NOT_EDIT_ANYTHING_BELOW_THIS_LINE
    );
    
    // Prints the area of the rectangle that has the smallest area
    printf("%.2f\n", r_min.edge1*r_min.edge2);
        
    return 0;
}
```

<br>

### Question 9 - Family

Define a struct named: Person which has an age, and a salary. Define a struct named: Family which has up to 9 persons and personCount (integer).

Write a program which takes 3 families, and returns the age of the person who earns the most in the family with the least total salary. (age of the richest person in the poorest family)

|  INPUT  |  OUTPUT |
|-------|-------|
| 3<br>10 0 33 5000 34 5500<br>5<br>10 10 30 1100 45 500 67 1000 5 0<br>2<br>48 4800 50 5000 | Richest person in the poorest family is 30 years old. |