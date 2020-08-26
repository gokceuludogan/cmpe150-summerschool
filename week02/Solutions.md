##  Loops

### Question 1 - Staaaars

```c
#include <stdio.h>

int main() {
	int N;
	scanf("%d", &N);

	int i = 0;

	while(i < N){
		printf("*\n");
		i++;
	}

	return 0;
}
```

<br />

### Question 2 - Numbeeeers

```c
#include <stdio.h>

int main() {
	int N;
	scanf("%d", &N);

	int i = 1;

	while(i <= N){
		printf("%d ", i);
		i++;
	}

	return 0;
}
```

<br />

### Question 3 - Hooping Numbers

```c
#include <stdio.h>

int main() {
	int A, B, t;
	scanf("%d %d %d", &A, &B, &t);

	int i;

    // while version
	i = B;
	while(i >= A){
		printf("%d ", i);
		i -= t;
	}
	
	printf("\n");
    
    // for version
	for(i = B ; i >= A ; i -= t){
		printf("%d ", i);
	}

	return 0;
}
```

<br />

### Question 4 - Even Numbeeeers

```c
#include <stdio.h>

int main() {
	int A, B;
	scanf("%d %d", &A, &B);

	int i = A;
	while(i <= B){
		if(i % 2 == 0){
			printf("%d ", i);
		}
		i++;
	}

	return 0;
}
```

<br />

### Question 5 - Stuck Between Chars

```c
#include <stdio.h>
int main() {
	char ch1, ch2;

	scanf("%c %c", &ch1, &ch2);
	
	for(; ch1 <= ch2; ch1++){
		printf("%c", ch1);
	}
    
	return 0;
}
```

<br />

### Question 6 - Average Team

Write a program that reads a number N, then reads N more numbers. Calculate the average of those N numbers.

```c
#include <stdio.h>

int main() {
	int n, x, i;
	float avg;

	scanf("%d", &n);
	for(i=0; i<n; i++){
	    scanf("%d", &x);
		avg += x;
	}
	printf("%.2f\n", avg/n);
	return 0;
}
```

<br />

### Question 7 - Boom Boom POW

```c
#include <stdio.h>

int main() {
	int a, b;
	scanf("%d %d", &a, &b);
	int result = 1;

	int i;
	for(i = 0 ; i < b ; i++){
		result *= a;
	}

	printf("%d", result);

	return 0;
}

```

<br>

### Question 8 - Fibonacci

```c
#include <stdio.h>

int main() {
	int n, i, prev = 0, curr = 1, next;

	scanf("%d", &n);

	for(i=3; i <= n; i++){
		next = prev + curr;
		prev = curr;
		curr = next;
	}
    
	if(n <= 0){
		printf("Invalid!");
	}
	else if(n == 1){
		printf("%d", prev);
	}else{
		printf("%d", curr);
	}

	return 0;
}
```

<br />

## Until Loops

### Question 1 - Digiiiits

```c
#include <stdio.h>

int main() {
	int x;
	scanf("%d", &x);

	int even_sum = 0;
	int digit_count = 0;
	int son_bas;

	while(x > 0){
		son_bas = x % 10;
		x /= 10;

		if(son_bas % 2 == 0){
			even_sum += son_bas;
		}
		digit_count++;
	}

	// for( ; x > 0 ; x /= 10){
	// 	son_bas = x % 10;

	// 	if(son_bas % 2 == 0){
	// 		even_sum += son_bas;
	// 	}
	// 	digit_count++;
	// }

	printf("%d %d", digit_count, even_sum);

	return 0;
}

```

<br>

### Question 2 - Positive Mental Attitude

```c
#include <stdio.h>

int main() {
	int sum = 0;
	int x;

	scanf("%d", &x);
	while(x >= 0){
		sum += x;
		scanf("%d", &x);
	}

	printf("%d", sum);

	return 0;
}

```
<br>

### Question 3 - NoBig

```c
#include <stdio.h>

int main() {
	int x, y;
	int sum = 0;

	scanf("%d %d", &x, &y);
	sum += x;
	while(y <= x){
		sum += y;
		
		x = y;
		scanf("%d", &y);
	}

	printf("%d", sum);
	return 0;
}
```

<br />

## Nested Loops

### Question 1 - R\*\*\*tangle

#### Question 1a

```c
#include <stdio.h>

int main() {
	int n, m, i, j;

	scanf("%d %d", &n, &m);
	for(i=1; i<=n; i++){
		for(j=1; j <= m; j++){
			printf("*");
		}
		printf("\n");
	}
	return 0;
}
```

#### Question 1b

```c
#include <stdio.h>

int main() {
	int n, m, i, j;

	scanf("%d %d", &n, &m);
	for(i=1; i<=n; i++){
		for(j=1; j <= m; j++){
			if(i == 1 || i == n || j == 1 || j == m){
				printf("*");
			}else{
				printf("-");
			}
		}
		printf("\n");
	}
	return 0;
}
```

<br>

### Question 2 - TriNumber

#### Question 2a
Write a program to display a right angle triangle using the number N, which will repeat the number for that row, like below.

| Input | Output                                  |
| :---: | --------------------------------------- |
|   3   | 1<br />22<br />333                      |
|   5   | 1<br />22<br />333<br />4444<br />55555 |

```c

```


#### Question 2b
Write a program to display a right angle triangle with N number of rows, like below.

| Input | Output                                  |
| :---: | --------------------------------------- |
|   3   | 1<br />12<br />123                      |
|   5   | 1<br />12<br />123<br />1234<br />12345 |

```c

```

#### Question 2c
Write a program which takes two integer as N and x and display a right angle triangle with N number of rows formed by powers of x as follows:

| Input | Output                                |
| :---: | ------------------------------------- |
|  3 4  | 4<br />4 16 <br />4 16 64             |
|  4 3  | 3<br />3 9<br />3 9 27<br />3 9 27 81 |

```c

```

<br>

### Question 3 - TriLetter

Write a program which takes an integer as input and prints an upper triangle of letters as follows:

| Input | Output                                            |
| :---: | ------------------------------------------------- |
|   5   | A B C D E<br />B C D E<br />C D E<br />D E<br />E |
|   3   | A B C<br />B C<br />C                             |

```c

```

<br>

### Question 4 - TriHard

```c
#include <stdio.h>

int main() {
	int N;
	scanf("%d", &N);

	int i, j;

	for(i = 1 ; i <= N ; i++){
		for(j = 0 ; j < N-i ; j++){
			printf("-");
		}
		for(j = 0 ; j < i ; j++){
			printf("*");
		}
		printf("\n");
	}

	return 0;
}

```

<br />


### Question 5 - Sum Facts

```c
#include <stdio.h>

int main()
{
    int num, i, sum=0;
    scanf("%d", &num);
    
    while(num>0){
       int last_digit = num % 10; // here we find the individual integers
                                  // e.g. 24 -> 2 and 4
       int factorial = 1;
       
       for(i=2; i <=last_digit; i++)
            factorial *= i;
            
        sum += factorial;
        
        num = num /10; // e.g 24 becomes  2, 789 becomes 78 and so on..
        
       
    }

    printf("%d", sum);
    return 0;
}
```

<br />

### Question 6 - Prime Example

#### Question 6a

```c
#include <stdio.h>

int main() {
	int x;
	scanf("%d", &x);

	int i;
	int isPrime = 1;

	if(x == 1)
		isPrime = 0;

	for(i = 2 ; i < x ; i++){
		if(x % i == 0){
			isPrime = 0;
			break;
		}
	}
	if(isPrime == 1){
		printf("Prime");
	}
	else
		printf("Prime Not");

	return 0;
}
```

#### Question 6b

```c
#include <stdio.h>

int main() {
	int b;
	scanf("%d", &b);

	int x;
	for(x = 2 ; x <= b ; x++){
		int i;
		int isPrime = 1;
		for(i = 2 ; i < x ; i++){
			if(x % i == 0){
				isPrime = 0;
				break;
			}
		}
		if(isPrime == 1){
			printf("%d ", x);
		}
	}

	return 0;
}
```

#### Question 6c

```c
#include <stdio.h>

int main() {
	int a, b;
	scanf("%d %d", &a, &b);

	int x;
	for(x = a ; x <= b ; x++){
		int i;
		int isPrime = 1;
		for(i = 2 ; i < x ; i++){
			if(x % i == 0){
				isPrime = 0;
				break;
			}
		}
		if(isPrime == 1){
			printf("%d ", x);
		}
	}

	return 0;
}
```
