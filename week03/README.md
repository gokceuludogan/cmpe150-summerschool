##  Functions

## Call by Value

### Question 1 - Number Pyramid

Write a function named **pyramid** which takes an integer as input: **num_of_rows**, then prints the pyramid of numbers increased by 1 shown below. This function shouldn't return anything.

```
Input:
4

Output:
   1
  2 3
 4 5 6
7 8 9 10


Input:
3

Output:
  1
 2 3
4 5 6
```

<br>

### Question 2 - Clock 

* Write a function named **printAsTime** which reads hours, minutes, and seconds as three integers, then prints it to the screen as shown in the examples. This function shouldn't return anything. 
* Assume no invalid input will be given (like 92 minutes or -2 hours). 

|  INPUT  |  OUTPUT |
|:-------:|:-------:|
| 5 12 3 | 05:12:03 |
| 3 0 22 |  03:00:22  |

### Question 3 - Minimum

Write a function **find_min** which takes three integers as parameters and returns **minimum** among them. Then, call this function in main() with the following inputs and print corresponding outputs.

| Input   | Output |
| ------- | ------ |
| 5 3 8   | 3      |
| 14 -1 9 | -1     |

<br>

### Question 4 - Word Up 

Write a function named **to_upper** which takes a char as input, and returns the upper case version of the character if it is a lower case letter. Otherwise it should return the same character.

Then write a program which reads a word from the user, and prints it with upper case characters. Assume valid words will be given. 


|  INPUT  |  OUTPUT |
|:-------:|:-------:|
| bogazici | BOGAZICI |
| CmpE | CMPE |

<br>

### Question 5 - Reverse

Write a function named **reverse** that will take an integer number and return its reverse version as another integer. Then fill/write main() appropriately to see the result.		

| Input | Output |
| ----- | ------ |
| 1234  | 4321   |
| 68436 | 63486  |

<br>

### Question 6 - The Perfect Question

Write a function **is_perfect()** that checks whether the given number is perfect. Perfect number is a positive integer that is equal to the sum of its positive divisors excluding the number itself. The function prints the positive divisors (excluding itself) and returns 1 if the number is perfect and returns 0 otherwise. 

* (These 0 (false) or 1 (true) returning functions are also known as "boolean functions")

| Input | Output     | Return |
| ----- | ---------- | ------ |
| 5     | 1          | 0      |
| 6     | 1 2 3      | 1      |
| 28    | 1 2 4 7 14 | 1      |
| 12    | 1 2 3 4 6  | 0      |

<br>

### Question 7 - Am I a Prime to You 

Write a function named **is_prime** that takes an integer as a parameter and returns 1 if the number is prime, otherwise returns 0.

Then write main appropriately to see the result.  

|  INPUT  |  OUTPUT |
|:-------:|:-------:|
| 17 | 1 |
| 345 | 0 |
| 1 | 0 |

<br>


### Question 8 - Am I TWO Prime to You

Write a function named **prime_sum** that takes an integer to check if this integer can be expressed as the sum of two prime numbers of all possible combinations and prints them.

* NOTE: You can use **is_prime** function you wrote previously.

|  INPUT  |  OUTPUT |
|:-------:|:-------:|
| 34 | 3 31<br>5 29<br>11 23<br>17 17 |


<br>


### Question 9 - Binary

Write a function that will take an integer as a parameter. Then calculates and returns its binary version as another integer. Then write main appropriately to see the result.	

| Input | Output     |
| ----- | ---------- |
| 25    | 11001      |
| 532   | 1000010100 |
| 5     | 101        |

<br>

### Question 10 - Fibonacci

Write a function that will take a positive integer n, and returns the nth Fibonacci number. Then write main appropriately to see the result.

| Input | Output |
| ----- | ------ |
| 1     | 0      |
| 2     | 1      |
| 3     | 1      |
| 4     | 2      |
| 5     | 3      |
| 10    | 34     |
| 15    | 377    |

### Question 11 - Permutation

* Write a factorial function, that takes an integer n as input, and returns n!. 

* Afterwards, write a permutation function, that takes two integers n, k as input, and returns P(n,k)=n!/(n-k)!. You should use your factorial function inside the permutation function. 

* Then organize the main function, to take two integers from the user, and prints the permutation. 

|  INPUT  |  OUTPUT |
|:-------:|:-------:|
| 5 3 | 60 |
| 10 2 |  90 |
| 5 5 |  120 |
| 7 0 |  1 |

### Question 12 - Fetch Digit

* Write a function named **fetchDigit** which takes two integers as input: number and n. Function should return the nth digit (from the right) of the number as an integer. If the number is less than n digits, Function should return -1.

* Then write a program which reads a positive integer z and another integer x, then print out the xth digit of z. If the input is incorrect (z doesn't have x digits), program should print "Incorrect input". Assume negative integers will not be given.

|  INPUT  |  OUTPUT |
|:-------:|:-------:|
| 23423 3 | 4 |
| 204602 5 | 0 |
| 52 9 | Incorrect input |

## Call by Reference

### Question 1 - Understanding Pointers

Write a C program that declares and initializes (to any value you like) a float, an int, and a char. Next declare and initialize a pointer to each of the three variables. Your program should then print the address of, and value stored in, and the memory size (in bytes) of each of the six variables.
Use the **"%p"** formatting specifier to print addresses in hexadecimal. You should see addresses that look something like this: "0xbfe55918". The initial characters **"0x"** tell you that hexadecimal notation is being used; the remainder of the digits give the address itself.
Use **"%f"** to print a floating value. Use the **sizeof** operator to determine the memory size allocated for each variable (**"%lu"** for printing sizes). 

**Sample Output:**

*The addresses will be different when you run your program.*   

<img src="figures/1587302715055.png" style="zoom:50%;" />

<details><summary>Layout</summary><table>
<thead>
<tr>
<th></th>
<th>Address</th>
<th>Value</th>
<th>Size</th>
</tr>
</thead>
<tbody>
<tr>
<td>char a;</td>
<td>0x5fca9c</td>
<td>&#39;F&#39;</td>
<td>1</td>
</tr>
<tr>
<td>int b;</td>
<td>0x5fca98</td>
<td>6</td>
<td>4</td>
</tr>
<tr>
<td>float c;</td>
<td>0x5fca94</td>
<td>3.500000</td>
<td>4</td>
</tr>
<tr>
<td>char *ptr_a;</td>
<td>0x5fca88</td>
<td>0x5fca9c</td>
<td>8</td>
</tr>
<tr>
<td>int *ptr_b;</td>
<td>0x5fca80</td>
<td>0x5fca98</td>
<td>8</td>
</tr>
<tr>
<td>float *ptr_c;</td>
<td>0x5fca78</td>
<td>0x5fca94</td>
<td>8</td>
</tr>
</tbody>
</table>
</details>

### Question 2 - Increment/Decrement

Write a function named **increment** which takes an integer as a parameter and increase the value of that integer and returns nothing. 

Write a function named **decrement** which takes an integer pointer (address of an integer) and decrease the value of the integer addressed by this pointer and returns nothing.

In the main program, read an integer from the user. Then call **increment** with this integer and print the value of this integer. Then call **decrement** with this integer and print the value of this integer again. Notice the difference. 

<details><summary>Steps</summary><img src='figures/Week8-Q2.png'/></details>

### Question 3 - Number Alteration

In the main function, one integer number and a char are read from the user into the variables x and c respectively. Complete the program by writing the function **alter**.

**alter** function takes one integer pointer (address of an integer) and one char variable as parameters. Function does the following operations:
* If char parameter is 'i', then increase the integer pointer parameter by one.
* If char parameter is 'd', then decrease the integer pointer parameter by one.
* If char parameter is 's', then assign the square of the integer pointer parameter to itself.
* Otherwise, do not change anything.

In the main function send variables x and c to the **alter** function and then print x in the main function.

|  INPUT  |  OUTPUT |
|:-------:|:-------:|
| 22 i | 23 |
| -4 d | -5 |
| 20 s | 400 |
| 20 j | 20 |

<br>

```c
#include <stdio.h>

// DO_NOT_EDIT_ANYTHING_ABOVE_THIS_LINE

// DO_NOT_EDIT_ANYTHING_BELOW_THIS_LINE

int main()
{
    int x;
    char c;
    
    scanf("%d %c", &x, &c);
    
    alter(
    // DO_NOT_EDIT_ANYTHING_ABOVE_THIS_LINE

    // DO_NOT_EDIT_ANYTHING_BELOW_THIS_LINE
        );
        
    printf("%d", x);
    return 0;
}
```

<br>

### Question 4 - Divide and Remain Still

Write a function named **divideWithRemainder** which takes two integer (number, divisor) and two integer pointer variables (\*result, \*remainder) as parameters:

This function should divide the **number** by **divisor**, then store the result in the parameter **\*result**, and store the remainder in the parameter **\*remainder**.

|  INPUT  |  OUTPUT |
|:-------:|:-------:|
| 8 3 | 2 2 |
| 27 4 | 6 3 |
| 10 2 | 5 0 |

<br>

```c
#include <stdio.h>

// DO_NOT_EDIT_ANYTHING_ABOVE_THIS_LINE

// DO_NOT_EDIT_ANYTHING_BELOW_THIS_LINE

int main()
{
    int n, d, res, rem;
    
    scanf("%d %d", &n, &d);
    
    divideWithRemainder(
    // DO_NOT_EDIT_ANYTHING_ABOVE_THIS_LINE

    // DO_NOT_EDIT_ANYTHING_BELOW_THIS_LINE
        );
        
    printf("%d %d", res, rem);
    return 0;
}
```

<br>

### Question 5 - Powered Sums

In the main function, two integer numbers are read from the user into the variables a and b respectively. Complete the program by writing two functions named **sums** and **powered**.

**sums** takes two integers (a and b) and an integer pointer (\*sum). The function should store the sum of these two integers in \*sum pointer.

**powered** takes three integers (sum, a and b) and two integer pointers (\*sum_p1 and \*sum_p2). The function should store the $a^{th}$ power of the sum in \*sum_p1 and $b^{th}$ power of the sum in \*sum_p2. 

Output:

First Line: Sum of two numbers

Second Line: $a^{th}$ power of the a+b and  $b^{th}$ power of the a+b

|  INPUT  |  OUTPUT |
|:-------:|:-------|
| 6 1 | 7<br>117649 7 |
| 4 4 | 8<br>4096 4096 |
| 5 0 | 5<br>3125 1 |

<br>

```c
#include <stdio.h>

// DO_NOT_EDIT_ANYTHING_ABOVE_THIS_LINE

// DO_NOT_EDIT_ANYTHING_BELOW_THIS_LINE

int main(){
	int a, b;
	scanf("%d %d",&a,&b);

	int sum;
	sums(
		// DO_NOT_EDIT_ANYTHING_ABOVE_THIS_LINE

		// DO_NOT_EDIT_ANYTHING_BELOW_THIS_LINE
	);
	printf("%d\n",sum);

	int sum_p1,sum_p2;
	powered(
		// DO_NOT_EDIT_ANYTHING_ABOVE_THIS_LINE

		// DO_NOT_EDIT_ANYTHING_BELOW_THIS_LINE);
	);
	printf("%d %d", sum_p1, sum_p2);

	TC_END;
    return 0;
}

```

<br>

### Question 6 - Complex Powers (Old Midterm Question)

* Think about how we write the regular power.

![Complex Powers](figures/q_complex.png)

