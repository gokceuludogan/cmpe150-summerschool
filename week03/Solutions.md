## Functions

## Call by Value

### Question 1 - Number Pyramid

```c
#include <stdio.h>

void pyramid(int num_of_rows){
	int i, j;
	int counter = 1;

	for(i = 1 ; i <= num_of_rows ; i++){
		for(j = 0 ; j < num_of_rows-i ; j++)
			printf(" ");
		for(j = 0 ; j < i ; j++)
			printf("%d ", counter++); // increase counter after printing

		printf("\n");
	}
}

int main() {
	int x;
	scanf("%d", &x);

	pyramid(x);

	return 0;
}
```

### Question 2 - Clock

```c
#include <stdio.h>

void printAsTime(int hours, int minutes, int seconds){ // A void function

	if(hours < 10){
		printf("0");
	}
	printf("%d:", hours);
	if(minutes < 10){
		printf("0");
	}
	printf("%d:", minutes);
	if(seconds < 10){
		printf("0");
	}
	printf("%d", seconds);

}

int main()
{
	int hours, minutes, seconds;

	scanf("%d %d %d", &hours, &minutes, &seconds);

	printAsTime(hours, minutes, seconds);

	return 0;
}
```

### Question 3 - Minimum

```c
#include <stdio.h>

int find_min(int x, int y, int z){
	int minimum;

	if(x <= y && x <= z)
		minimum = x;
	else if(y <= x && y <= z)
		minimum = y;
	else
		minimum = z;

	return minimum;
}

int main() {
	int x, y, z;

	scanf("%d %d %d", &x, &y, &z);

	printf("%d", find_min(x, y, z));

	return 0;
}
```

### Question 4 - Word Up

```c
#include <stdio.h>

char to_upper(char c){
	if(c >= 'a' && c <= 'z')
		return c + ('A'-'a');
	return c;
}

int main() {
	char c;

	scanf("%c", &c);

	while(c != '\n'){
		printf("%c", to_upper(c));
		scanf("%c", &c);
	}

	return 0;
}
```

### Question 5 - Reverse

```c
#include <stdio.h>

int reverse(int x){
	int reverse_x = 0;

	while(x > 0){
		reverse_x = 10*reverse_x + (x%10);
		x /= 10;
	}

	return reverse_x;
}

int main() {
	int x;

	scanf("%d", &x);

	printf("%d", reverse(x));

	return 0;
}
```

### Question 6 - The Perfect Question

```c
#include <stdio.h>

int is_perfect(int x){
	int i;
	int sum = 0;

	for(i = 1 ; i < x ; i++){
		if(x % i == 0){
			sum += i;
			printf("%d ", i);
		}
	}
	printf("\n");

	if(sum == x)
		return 1;
	else
		return 0;
}

int main() {
	int x;

	scanf("%d", &x);

	printf("%d", is_perfect(x));

	return 0;
}
```

### Question 7 - Am I a Prime to You

```c
#include <stdio.h>

int is_prime(int x){
	int i;
	int isPrime = 1;

	if(x < 2)
		isPrime = 0;

	for(i = 2 ; i < x ; i++){
		if(x % i == 0){
			isPrime = 0;
			break;
		}
	}

	return isPrime;
}

int main() {
	int x;

	scanf("%d", &x);

	printf("%d", is_prime(x));

	return 0;
}
```

### Question 8 - Am I TWO Prime to You

```c
#include <stdio.h>

int is_prime(int x){
	int i;
	int isPrime = 1;

	if(x < 2)
		isPrime = 0;

	for(i = 2 ; i < x ; i++){
		if(x % i == 0){
			isPrime = 0;
			break;
		}
	}

	return isPrime;
}

void prime_sum(int x){
	int i;

	for(i = 2 ; i <= x/2 ; i++){
		if(is_prime(i) && is_prime(x-i)){
			printf("%d %d\n", i, x-i);
		}
	}
}

int main() {
	int x;

	scanf("%d", &x);

	prime_sum(x);

	return 0;
}
```

### Question 9 - Binary

```c
#include <stdio.h>

// long int has 8 byte length while int has 4 byte
// we use long int because we are trying to represent a binary number in decimal format
// and they are too long to fit in normal int variables.
long int to_binary(int x){
	int mult = 1;
	long int binary_x = 0;

	while(x > 0){
		binary_x += mult*(x%2);
		mult *= 10;
		x /= 2;
	}

	return binary_x;
}

int main() {
	int x;

	scanf("%d", &x);

	printf("%ld", to_binary(x));

	return 0;
}
```

### Question 10 - Fibonacci

```c
#include <stdio.h>

int fibonacci(int x){
	int i;
	int f1 = 0, f2 = 1;

	if(x == 1)
		return 0;
	else if(x == 2)
		return 1;

	for(i = 2 ; i < x ; i++){
		int fsum = f1+f2;
		f1 = f2;
		f2 = fsum;
	}

	return f2;
}

int main() {
	int x;

	scanf("%d", &x);

	printf("%d", fibonacci(x));

	return 0;
}
```

### Question 11 - Permutation

```c
#include <stdio.h>

int factorial(int n){
	int i, result = 1;
	for(i = 1; i <= n; i++){
		result *= i;
	}
	return result;
}

int permutation(int n, int k){
	return factorial(n) / factorial(n - k);
}

int main()
{
	int n, k;

	scanf("%d %d", &n, &k);

	printf("%d", permutation(n, k) );

	return 0;
}
```

### Question 12 - Fetch Digit

```c
#include <stdio.h>

// Function should return mod10{ number/(10^(n-1)) }
int fetchDigit(int number, int n){
	int i, power_of_ten = 1;
	for(i = 1; i < n; i++){
		power_of_ten *= 10;
	}

	if(number < power_of_ten){
		return -1;
	}

	number = number / power_of_ten;
	return (number % 10);
}

int main()
{
	int a_big_number, n, digit;

	scanf("%d %d", &a_big_number, &n);

	digit = fetchDigit(a_big_number, n);

	if(digit == -1){
		printf("Incorrect input");
	}
	else{
		printf("%d", digit);
	}

	return 0;
}
```

## Call by Reference

### Question 1 - Understanding Pointers

```c
#include <stdio.h>
#include <stdlib.h>

int main(void) {

	int a = 5;
	char b = 'e';
	float c = 9.68;

	int *a_ptr = &a;
	char *b_ptr = &b;
	float *c_ptr = &c;

	// print the addresses of the variables
	printf("The address of int: %p \n", &a);
	printf("The address of char: %p \n", &b);
	printf("The address of float: %p \n", &c);

	// print the addresses of the pointers
	printf("The address of int*: %p \n", &a_ptr);
	printf("The address of char*: %p \n", &b_ptr);
	printf("The address of float*: %p \n", &c_ptr);

	// print the values of the variables
	printf("The value of int: %d \n", a);
	printf("The value of char: %c \n", b);
	printf("The value of float: %f \n", c);

	// print the values of the pointers
	printf("The value of int*: %p \n", a_ptr);
	printf("The value of char*: %p \n", b_ptr);
	printf("The value of float*: %p \n", c_ptr);

	// print the size of the variables
	printf("The size of int: %lu \n", sizeof(a));
	printf("The size of char: %lu \n", sizeof(b));
	printf("The size of float: %lu \n", sizeof(c));

	// print the size of the pointers
	printf("The size of int*: %lu \n", sizeof(a_ptr));
	printf("The size of char*: %lu \n", sizeof(b_ptr));
	printf("The size of float*: %lu \n", sizeof(c_ptr));

	return 0;
}
```

### Question 2 - Increment/Decrement

```c
#include <stdio.h>
#include <stdlib.h>

void increment(int a){
	printf("Address: %p\n", &a);
	a++;
}
void decrement(int *ptr){
	printf("Address: %p\n", &(*ptr));
	(*ptr)++;
}
int main() {
	int number;
	scanf("%d", &number);
	printf("Before %p\n", &number);
	increment(number);
	printf("%d\n", number);
	decrement(&number);
	printf("%d\n", number);
	return 0;
}
```

### Question 3 - Number Alteration

```c
#include <stdio.h>

// DO_NOT_EDIT_ANYTHING_ABOVE_THIS_LINE
void alter(int *x, char c){
	if(c == 'i'){
		(*x)++;
	}
	else if(c == 'd'){
		(*x)--;
	}
	else if(c == 's'){
		*x = *x * *x;
	}
}
// DO_NOT_EDIT_ANYTHING_BELOW_THIS_LINE

int main()
{
    int x;
    char c;

    scanf("%d %c", &x, &c);

    alter(
    // DO_NOT_EDIT_ANYTHING_ABOVE_THIS_LINE
    	&x, c
    // DO_NOT_EDIT_ANYTHING_BELOW_THIS_LINE
        );

    printf("%d", x);
    return 0;
}
```

### Question 4 - Divide and Remain Still

```c
#include <stdio.h>

// DO NOT EDIT ANYTHING ABOVE
void divideWithRemainder(int num, int div, int *result, int *remainder){
    *result = num/div;
    *remainder = num%div;
}
// DO NOT EDIT ANYTHING BELOW

int main()
{
    int n, d, res, rem;

    scanf("%d %d", &n, &d);

    divideWithRemainder(
    // DO NOT EDIT ANYTHING ABOVE
            n, d, &res, &rem
    // DO NOT EDIT ANYTHING BELOW
        );

    printf("%d %d", res, rem);
    return 0;
}
```

### Question 5 - Powered Sums

```c
#include <stdio.h>

// DO_NOT_EDIT_ANYTHING_ABOVE_THIS_LINE

void sums(int a, int b,int *sum){
	*sum = a + b;
}

void powered(int sum, int a, int b, int *p1, int *p2){
	*p1 = 1;
	*p2 = 1;

	int i;
	for(i = 0 ; i < a ; i++){
		*p1 *= sum;
	}
	for(i = 0 ; i < b ; i++){
		*p2 *= sum;
	}
}

// DO_NOT_EDIT_ANYTHING_BELOW_THIS_LINE
int main(){
	int a, b;
	scanf("%d %d", &a, &b);

	int sum;

	sums(
		// DO_NOT_EDIT_ANYTHING_ABOVE_THIS_LINE
		a, b, &sum
		// DO_NOT_EDIT_ANYTHING_BELOW_THIS_LINE
	);
	printf("%d\n", sum);

	int sum_p1, sum_p2;
	powered(
		// DO_NOT_EDIT_ANYTHING_ABOVE_THIS_LINE
		sum, a, b, &sum_p1, &sum_p2
		// DO_NOT_EDIT_ANYTHING_BELOW_THIS_LINE
	);

	printf("%d %d", sum_p1, sum_p2);

    return 0;
}
```

### Question 6 - Complex Powers (Old Midterm Question)

```c
#include <stdio.h>

// a regular power function with pointer for you to compare it with the complex_power finction
void poww(int a, int p, int *res){
    // *poww = a^p

    *res = a;

    int i;
    for(i = 1 ; i < p ; i++){
        *res = *res * a;
    }
}

void complex_power(float a, float b, int p, float *re, float *im){
    *re = a;
    *im = b;

    int i;
    for(i = 1 ; i < p ; i++){
        float temp_re, temp_im;
        temp_re = a * *re - b * *im;
        temp_im = a * *im + b * *re;

        *re = temp_re;
        *im = temp_im;
    }
}


int main(){
    float a, b;
    int p;
    scanf("%f %f %d", &a, &b, &p);

    float re, im;
    complex_power(
        // DO_NOT_EDIT_ANYTHING_ABOVE_THIS_LINE
            a, b, p, &re, &im
        // DO_NOT_EDIT_ANYTHING_BELOW_THIS_LINE
    );
    printf("%.2f %.2f", re, im);

    return 0;
}
```

