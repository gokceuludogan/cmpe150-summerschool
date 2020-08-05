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



