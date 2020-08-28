## Q1

```c
#include <stdio.h>
int main() {
	int N, i;
	scanf("%d", &N);
	int arr[N];

	for(i = 0 ; i < N ; i++)
		scanf("%d", &arr[i]);

	float sum = 0, avg;
	
	for(i = 0 ; i < N ; i++)
		sum += arr[i];

	avg = sum / N;

	for(i = 0; i < N; i++){
		if(arr[i] > avg){
			printf("%d ", arr[i]);
		}
	}

	return 0;
}
```

## Q2

```c
#include <stdio.h>
int main(){
	char arr[51];
	int s_len = 0, i;
	char c;
	// read sentence
	scanf("%c", &c);
	while(c != '\n'){
		arr[s_len] = c;
		s_len++;
		scanf("%c", &c);
	}

	// encryption
	for(i = 0 ; i < s_len ; i++)
		arr[i] = arr[i]+1;

	for(i = 0 ; i < s_len ; i++){
		printf("%c", arr[i]);
	}

	// decryption
	for(i = 0 ; i < s_len ; i++)
		arr[i] = arr[i]-1;

	for(i = 0 ; i < s_len ; i++){
		printf("%c", arr[i]);
	}
    return 0;
}
```

## Q3

```c
#include <stdio.h>
int main(){
	int i, N;
	scanf("%d", &N);
	int arr[N];

	for(i = 0 ; i < N ; i++)
		scanf("%d", &arr[i]);

	// part a
	for(i = N-1 ; i >= 0 ; i--)
		printf("%d ", arr[i]);
	printf("\n");

	// part b
	for(i = 0 ; i < N/2 ; i++){
		int temp = arr[i];
		arr[i] = arr[N-i-1];
		arr[N-i-1] = temp;
	}

	for(i = 0 ; i < N ; i++)
		printf("%d ", arr[i]);

    return 0;
}
```

## Q4

```c
#include <stdio.h>

int main()
{
	int i, N;
	scanf("%d", &N);
	int arr[N];
	int counter[101] = {0};

	for(i = 0 ; i < N ; i++)
		scanf("%d", &arr[i]);
	
	for(i = 0 ; i < N ; i++)
		counter[arr[i]]++;
	
	for(i = 0 ; i < 101 ; i++){
		if(counter[i] > 0){
			printf("%d --> %d", i, counter[i]);
		}
	}
	
	// Example
	// 5 10 2 5 50 5 10 1 2 2  -> arr[N]
		
	// 0 1 2 3 4 5 6 7 8 9 10 11 12 ... 50 ... 100 -> counter[101]
	// 0 1 3 0 0 3 0 0 0 0 2  0  0      1      0	

    return 0;
}
```

## Q5

```c
#include <stdio.h>

int main()
{
	int i, j;

	int N, M;
	scanf("%d %d", &N, &M);
	int arr1[N], arr2[M];

	for(i = 0 ; i < N ; i++)
		scanf("%d", &arr1[i]);

	for(i = 0 ; i < M ; i++)
		scanf("%d", &arr2[i]);

	for(j = 0 ; j < M - N ; j++){
		for(i = 0 ; i < N ; i++){
			if(arr1[i] != arr2[j+i])
				break;
		}
		
		// i will be equal to N if and only if the above loop terminates without entering the if statement
		// So if i is equal to N, it means that we found the same sub array to arr1.
		if(i == N){
			printf("%d", j);
			break;
		}
	}

    return 0;
}
```

## Q6

```c
#include <stdio.h>

int main() {
	int N, X, i, j;

	scanf("%d %d", &N, &X);
	
	int arr[N];

	for(i = 0 ; i < N ; i++)
		scanf("%d", &arr[i]);

	for(i = 0 ; i < N-1 ; i++){
		for(j = i+1 ; j < N ; j++){
			if(arr[i] + arr[j] == X){
				printf("(%d, %d)\n", arr[i], arr[j]);
			}
		}
	}

	return 0;
}
```

## Q7

```c
#include <stdio.h>

int main() {
	int N, i, j;

	scanf("%d", &N);

	int arr[N];

	for(i = 0; i < N; i++)
		scanf("%d", &arr[i]);

	for(i = 0; i < N; i++) {
		if(arr[i] == 3) {
			for(j = 0; j < N; j++) {
				if(arr[j] == 4 && arr[j-1] != 3) {
					int temp = arr[i+1];
					arr[i+1] = arr[j];
					arr[j] = temp;
				}
			}
		}
	}
	
	for(i = 0; i < N; i++)
		printf("%d ", arr[i]);

	return 0;
}
```

## Q8

```c
#include <stdio.h>

int main() {
	int N, i, j;

	scanf("%d", &N);

	int arr[N];
	
	for(i = 0 ; i < N ; i++)
		scanf("%d", &arr[i]);

	for(i = 0 ; i < N ; i++){
		for(j = 0; j < N-i-1 ; j++){
			if(arr[j] > arr[j+1]){
				int temp = arr[j];
				arr[j] = arr[j+1];
				arr[j+1] = temp;
			}
		}
	}
	
	for(i = 0; i < N; i++)
		printf("%d ", arr[i]);

	return 0;
}
```

## Q8 - other methods:

You can modify the two for loops (above), and still be able to successfully sort. 

* The array is successfully sorted after N-1 passes. Therefore, you can also modify the outer for loop like below:
```c
for(i = 0 ; i < N - 1 ; i++){
	for(j = 0; j < N-i-1 ; j++){
```

* In the first method, since at each pass, the last i elements are sorted, we wrote: (j < N - i - 1). If you don't care about the performance of the program, you can perform each pass for each element inside the array (j < N-1). This is a less optimal solution, since it does more comparisons unnecessarily. However, it sorts the array successfully too. 

```c
for(i = 0 ; i < N ; i++){
	for(j = 0 ; j < N-1 ; j++){
```

## Multidimensional Arrays

### Q1

```c
#include <stdio.h>

int main(){
	int array_2d[][3] = {{1,2,3}, {4, 5, 6}};
	int r = 2;
	int c = 3;
	int i, j;
	for(j = 0; j < c; j++){
		for(i = 0; i < r; i++){
			printf("%d ", array_2d[i][j]);
		}
		printf("\n");
	}
	return 0;

}
```

### Q2

```c
#include <stdio.h>
void print_2d_array(int m, int n, int arr[m][n]){
	int i, j;
	for(i=0; i<m; i++){
		for(j=0; j<n; j++){
			printf("%d", arr[i][j]);
		}
		printf("\n");
	}
}

void read_2d_array(int m, int n, int arr[m][n]){
	int i, j;
	for(i=0; i<m; i++){
		for(j=0; j<n; j++){
			scanf("%d", &arr[i][j]);
		}
	}
}

int main(){
	int R, C;
	scanf("%d %d", &R, &C);
	int matrix[R][C];
	read_2d_array(R, C, matrix);
	print_2d_array(R, C, matrix);
	return 0;
}

```

### Q3

```c
#include <stdio.h>

void read_2d_array(int m, int n, int arr[m][n]){
	int i, j;
	for(i=0; i<m; i++){
		for(j=0; j<n; j++){
			scanf("%d", &arr[i][j]);
		}
	}
}

int main(){
	int N, M;
	scanf("%d %d", &N, &M);
	int arr1[N][M], arr2[N][M];
	read_2d_array(N, M, arr1);
	read_2d_array(N, M, arr2);
	int i, j;
	for(i = 0; i < N; i++){
		for(j = 0; j < M; j++){
			printf("%d", arr1[i][j] + arr2[i][j]);
		}
	}
	return 0;
}

```

### Q4

```c
#include <stdio.h>
void read_2d_array(int m, int n, int arr[m][n]){
	int i, j;
	for(i=0; i<m; i++){
		for(j=0; j<n; j++){
			scanf("%d", &arr[i][j]);
		}
	}
}

int main(){
	int N;
	scanf("%d", &N);
	int arr[N][N];
	read_2d_array(N, N, arr);
	int i, j, left_sum=0, right_sum=0;

	for(i = 0; i < N; i++){
		for(j = 0; j < N; j++){
			if(i == j){
				left_sum += arr[i][j];
			}
			if(i + j == N - 1){
				right_sum += arr[i][j];
			}
		}
	}
	printf("%d %d", left_sum, right_sum);
	return 0;
}

```

#### Alternative Solution

```c
#include <stdio.h>
void print_2d_array(int m, int n, int arr[m][n]){
	int i, j;
	for(i=0; i<m; i++){
		for(j=0; j<n; j++){
			printf("%d", arr[i][j]);
		}
		printf("\n");
	}
}

void read_2d_array(int m, int n, int arr[m][n]){
	int i, j;
	for(i=0; i<m; i++){
		for(j=0; j<n; j++){
			scanf("%d", &arr[i][j]);
		}
	}
}

int main(){
	int N;
	scanf("%d", &N);
	int arr[N][N];
	read_2d_array(N, N, arr);
	int i, left_sum=0, right_sum=0;
	for(i=0; i < N; i++){
		left_sum += arr[i][i];
		right_sum += arr[i][N-1-i];
	}
	printf("%d %d", left_sum, right_sum);
	return 0;
}

```

### Q5

```c
#include <stdio.h>
void read_2d_array(int m, int n, int arr[m][n]){
	int i, j;
	for(i=0; i<m; i++){
		for(j=0; j<n; j++){
			scanf("%d", &arr[i][j]);
		}
	}
}

int main(){
	int N, M, k;
	scanf("%d%d%d", &N, &M, &k);
	int arr[N][M];
	read_2d_array(N, M, arr);
	int i, j;

	for(i = 0; i < N; i++){
		int sum = 0;
		for(j = 0; j < (i+1)*k && j < M; j++){
			sum+= arr[i][j];
			printf("%d ", arr[i][j]);
		}
		printf("%d\n", sum);
	}

	return 0;
}
```

### Q6

```c
#include <stdio.h>
void print_2d_array(int m, int n, int arr[m][n]){
	int i, j;
	for(i=0; i<m; i++){
		for(j=0; j<n; j++){
			printf("%d", arr[i][j]);
		}
		printf("\n");
	}
}

void read_2d_array(int m, int n, int arr[m][n]){
	int i, j;
	for(i=0; i<m; i++){
		for(j=0; j<n; j++){
			scanf("%d", &arr[i][j]);
		}
	}
}

int main(){
	int N, M, k;
	scanf("%d%d%d", &N, &M, &k);
	int arr[N][M];
	read_2d_array(N, M, arr);
	int i, j;

	for(i = 0; i < N; i++){
		for(j = i*k; j < (i+1)*k; j++){
			printf("%d ", arr[i][j]);
		}
		printf("\n");
	}

	return 0;
}

```

