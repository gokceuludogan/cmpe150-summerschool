## Data types & Operators

### Q1

```c
#include <stdio.h>

int main() {
	int a, b, c;
	scanf("%d%d%d", &a, &b, &c);
	//int sum = a + b + c;
	printf("%d", a + b + c);
	return 0;
}
```

### Q2

```c
#include <stdio.h>

int main() {
	int x, y;
	scanf("%d%d", &x, &y);
	//int area = x * y;
	//int perimeter = 2 * (x + y);
	printf("%d %d", 2 * (x + y), x * y);
	return 0;
}
```

### Q3

```c
#include <stdio.h>

int main() {
	float r;
	scanf("%f", &r);
	float circ = 2 * 3.14 * r;
	float area = 3.14 * r * r;
	printf("%.3f %.3f", circ, area);
	return 0;
}
```

### Q4

```c
#include <stdio.h>

int main() {
	int a, b, c;
	scanf("%d%d%d", &a, &b, &c);

	float avg = (float)(a + b + c) / 3; // or 1.0 * (a + b + c) / 3
	printf("%.2f", avg);
	return 0;
}
```

### Q5

```c
#include <stdio.h>
int main() {
	int a, b, c;
	scanf("%d%d%d", &a, &b, &c);
	/*printf("%d %d\n", a % 2, a * (a % 2));
	printf("%d %d\n", b % 2, b * (b % 2));
	printf("%d %d\n", c % 2, c * (c % 2));*/
	int sum = a * (a % 2) + b * (b % 2) + c * (c % 2);
	printf("%d", sum);
	return 0;
}
```

### Q6

```c
#include <stdio.h>
// total seconds = 3600 * hours + 60 * minutes + seconds
int main() {
	int total_seconds;
	scanf("%d", &total_seconds);
	int hours = total_seconds / 3600;
	int remaining_seconds = total_seconds % 3600;
	// printf("remaining %d\n", remaining_seconds);
	int minutes = remaining_seconds / 60;
	int seconds = remaining_seconds % 60;
	printf("%d %d %d", hours, minutes, seconds);
	return 0;
}

```

## Characters

### Q1

```c
#include <stdio.h>

int main() {
	char ch;
	scanf("%c", &ch);
	int rank = ch - 'A' + 1;
	printf("%d", rank);
	return 0;
}
```

### Q2

```c
#include <stdio.h>

int main() {
	char mychar;
	scanf("%c", &mychar);
	printf("%c", mychar + 3);
	return 0;
}
```

### Q3

```c
#include <stdio.h>

int main() {
	char mychar;
	scanf("%c", &mychar);
	char upper = mychar - 'a' + 'A';
	printf("%c", upper);
	return 0;
}
```

### Q4

```c
#include <stdio.h>

int main() {
	char ch1, ch2;
	scanf("%c%c", &ch1, &ch2);
	//printf("%d %d", ch1, ch2);
	printf("%d", (ch1 - '0') * (ch2 - '0'));	
	return 0;
}
```

### Q5

```c
#include <stdio.h>

int main() {
	char ch;
	scanf("%c", &ch);
	int is_digit = ch >= '0' && ch <= '9';
	printf("%d %d", is_digit, is_digit * (ch - '0'));
	return 0;
}
```

## Conditional Statements

### Q1

```c

#include <stdio.h>

int main() {
	int num;
	scanf("%d", &num);
	if(num > 0){
		//printf("positive");
		//printf("%s", num % 2 == 0 ? "even" : "odd");
		if(num % 2 != 0){
			printf("odd");
		}else{
			prtf("even");
		}
	}else if(num < 0){
		//printf("negative");
		printf("%d", -num);
	}
	else{
		printf("zero");
	}
	return 0;
}

```

### Q2

```c

#include <stdio.h>

int main() {
	int a, b;
	scanf("%d%d", &a, &b);
	if(a <= 0 || b <= 0){
		printf("Incorrect Input");
	}else{
		if(a % b == 0){
			printf("It is divisible");
		}else{
			printf("It is not divisible");
		}
	}
	return 0;
}

```

### Q3

```c

#include <stdio.h>
#include <stdlib.h>

int main() {
	char ch;
	scanf("%c", &ch);
	if((ch >= 'a' && ch <= 'z') || (ch >= 'A' && ch <= 'Z')){
		printf("Lettuce\n");
	}else if(ch >= '0' && ch <= '9'){
		printf("Durian\n");
	}else{
		printf("Nani?!!");
	}
	return 0;
}
```

### Q4

```c
#include <stdio.h>

int main() {
	float a, b;
	char op;
	scanf("%f%c%f", &a, &op, &b);
	if(op == '+'){
		printf("%.2f", a + b);
	}else if(op == '-'){
		printf("%.2f", a - b);
	}else if(op == '*'){
		printf("%.2f", a * b);
	}else{
		printf("%.2f", a / b);
	}
	

	return 0;
}
```

#### switch 

````c
#include <stdio.h>

int main() {
	float a, b;
	char op;
	scanf("%f%c%f", &a, &op, &b);
	switch(op){
		case '+': printf("%.2f", a + b); break;
		case '-': printf("%.2f", a - b); break;
		case '*': printf("%.2f", a * b); break;
		case '/': printf("%.2f", a / b); break;
	}

	return 0;
}
````

### Q5

```c
#include <stdio.h>

int main() {
	int year;
	scanf("%d", &year);

	if(year % 4 == 0){
		printf("leap year");
	}else{
		printf("not a leap year");
	}
}

```

#### Alternative

```c
#include <stdio.h>

int main() {
	int year;
	scanf("%d", &year);
	if(year % 4){
		printf("not a leap year");
	}else{
		printf("leap year");
	}
	return 0;
}
```

### Q6

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
	int x, y;
	scanf("%d%d", &x, &y);
	if(x == 0 && y == 0){
		printf("origin");
	}else if(x > 0 && y >0){
		printf("The point (%d,%d) lies in the first quadrant", x, y);
	}else if(x < 0 && y > 0){
		printf("The point (%d,%d) lies in the second quadrant", x, y);
	}else if(x < 0 && y < 0){
		printf("The point (%d,%d) lies in the third quadrant", x, y);
	}else if(x > 0 && y < 0){
		printf("The point (%d,%d) lies in the forth quadrant", x, y);
	}

	return 0;
}
```

### Q7

```c
#include <stdio.h>

int main() {
	int a, b, c;
	scanf("%d%d%d", &a, &b, &c);
	int max = a > b ? a : b;
	max = max > c ? max : c;
    printf("%d", max);
    return 0;
}
```

#### Alternative I

```c
#include <stdio.h>

int main(void) {
	int a, b, c;
	scanf("%d%d%d", &a, &b, &c);
	if(a > b){
		if(a > c){
			printf("%d", a);
		}else{
			printf("%d", c);
		}
	}else{
		if(b > c){
			printf("%d", b);
		}else{
			printf("%d", c);
		}
	}
	return 0;
}
```

#### Alternative II

```c
#include <stdio.h>

int main(void) {
	int a, b, c;
	scanf("%d%d%d", &a, &b, &c);
	int max;
	if(a > b){
		max = a;
	}else{
		max = b;
	}
	if(c > max){
		max = c;
	}
	printf("%d", max);
	return 0;
}
```

### Q8

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
	char ch;
	scanf("%c", &ch);
	if(ch >= 'a' && ch <= 'z'){
		printf("%c", ch - 'a' + 'A');
	}else if(ch >= 'A' && ch <= 'Z'){
		printf("%c", ch - 'A' + 'a');
	}else if(ch >= '0' && ch <= '9'){
		printf("%d", (ch - '0') * 2);
	}else{
		printf("asdasd");
	}
	return EXIT_SUCCESS;
}
```



