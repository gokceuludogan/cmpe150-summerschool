## Warm up

```c

#include <stdio.h>

int abs(int x){
	if(x < 0)
		return -x;
	return x;
}

int main() {
	int R=8, C=8;
	int i, j;
	int table[10][10];

	// read the chess table
	for(i = 0 ; i < R ; i++)
		for(j = 0 ; j < C ; j++)
			scanf("%d", &table[i][j]);

	// print the chess table to be sure that you have read it correctly.
	// printf("\n");
	// for(i = 0 ; i < R ; i++){
	// 	for(j = 0 ; j < C ; j++){
	// 		printf("%d ", table[i][j]);
	// 	}
	// 	printf("\n");
	// }

	int rookR, rookC;
	for(i = 0 ; i < R ; i++){
		for(j = 0 ; j < C ; j++){
			if(table[i][j] == 8){
				rookR = i;
				rookC = j;
			}
		}
	}

	int pawnDist = 100, pawnR, pawnC;
	for(i = 0 ; i < R ; i++){
		if(table[i][rookC] == 1 && abs(i-rookR) < pawnDist ){
			pawnDist = abs(i-rookR);
			pawnR = i;
			pawnC = rookC;
		}
	}
	for(j = 0 ; j < C ; j++){
		if(table[rookR][j] == 1 && abs(j-rookC) < pawnDist ){
			pawnDist = abs(j-rookC);
			pawnR = rookR;
			pawnC = j;
		}
	}

	table[rookR][rookC] = 0;
	table[pawnR][pawnC] = 8;

	printf("\n");
	for(i = 0 ; i < R ; i++){
		for(j = 0 ; j < C ; j++){
			printf("%d ", table[i][j]);
		}
		printf("\n");
	}

	return 0;
}

```

## Q1

```c

void normalize_string(char s[]){
	if(s[strlen(s)-2] == '\r' || s[strlen(s)-2] == '\n')
		s[strlen(s)-2] = '\0';
	else if(s[strlen(s)-1] == '\r' || s[strlen(s)-1] == '\n')
		s[strlen(s)-1] = '\0';
}

int string_length(char str[]){
	int i;
	for(i = 0; str[i] != '\0'; i++);
	return i;
}

int main(){
	char str[101];
	fgets(str, 100, stdin);
	normalize_string(str);
	printf("%d %d", string_length(str), strlen(str));
	return 0;
}

```

## Q2

```c

void copy_string(char dest[], char src[]){
	int i;
	for(i = 0; src[i] != '\0'; i++){
		dest[i] = src[i];
	}
	dest[i] = '\0';
}

void normalize_string(char s[]){
	if(s[strlen(s)-2] == '\r' || s[strlen(s)-2] == '\n')
		s[strlen(s)-2] = '\0';
	else if(s[strlen(s)-1] == '\r' || s[strlen(s)-1] == '\n')
		s[strlen(s)-1] = '\0';
}

int main(){
	char str[101];
	fgets(str, 100, stdin);
	normalize_string(str);
	char dest1[101], dest2[101], dest3[101];
	copy_string(dest1, str);
	strcpy(dest2, str);
	strncpy(dest3, str, strlen(str)+1);
	printf("%s, %s, %s", dest1, dest2, dest3);
	return 0;
}
```

## Q3

```c
int compare_strings(char s1[], char s2[]){
	int i;
	for(i = 0 ; i < strlen(s1)+1 && i < strlen(s2)+1 ; i++)
		if(s1[i] - s2[i] != 0)
			return s1[i]-s2[i];

	return 0;
}

void normalize_string(char s[]){
	if(s[strlen(s)-2] == '\r' || s[strlen(s)-2] == '\n')
		s[strlen(s)-2] = '\0';
	else if(s[strlen(s)-1] == '\r' || s[strlen(s)-1] == '\n')
		s[strlen(s)-1] = '\0';
}

int main(){
	char str1[101], str2[101];
	fgets(str1, 100, stdin);
	fgets(str2, 100, stdin);

	normalize_string(str1);
	normalize_string(str2);

	printf("%d, %d", compare_strings(str1, str2), strcmp(str1, str2));
	printf("\n%d", strncmp(str1, str2, 4));
	return 0;
}
```

## Q4

```c

void normalize_string(char s[]){
	if(s[strlen(s)-2] == '\r' || s[strlen(s)-2] == '\n')
		s[strlen(s)-2] = '\0';
	else if(s[strlen(s)-1] == '\r' || s[strlen(s)-1] == '\n')
		s[strlen(s)-1] = '\0';
}

int main(){
	char str[101];
	fgets(str, 100, stdin);

	normalize_string(str);
	int i, counter = 0;
	for(i = 0; str[i] != '\0'; i++){
		if(str[i] == ' '){
			counter++;
		}
	}
	printf("%d", counter);
	return 0;
}

```

## Q5

### a

```c

void normalize_string(char s[]){
	if(s[strlen(s)-2] == '\r' || s[strlen(s)-2] == '\n')
		s[strlen(s)-2] = '\0';
	else if(s[strlen(s)-1] == '\r' || s[strlen(s)-1] == '\n')
		s[strlen(s)-1] = '\0';
}

int main(){
	char str[101];
	fgets(str, 100, stdin);
	int nth_word;
	scanf("%d", &nth_word);
	normalize_string(str);
	int i, counter = 1;
	for(i = 0; str[i] != '\0'; i++){
		if(counter == nth_word){
			printf("%c", str[i]);
		}
		if(str[i] == ' '){
			counter++;
		}
	}
	return 0;
}

```

### Alternative

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
	char input[101], nth_word[101];
	int n;
	fgets(input, 101, stdin);
	scanf("%d", &n);
	int i, counter=1, word_ix=0;
	for(i=0; input[i] != '\0'; i++){
		if(counter == n){
			//printf("%c", input[i]);
           	nth_word[word_ix] = input[i];
            word_ix++;
		}
		if(input[i] == ' '){
			counter++;
		}
	}
    nth_word[word_ix] = '\0';
    printf("%s", nth_word);
	return 0;
}
```

### b

```c

void normalize_string(char s[]){
	if(s[strlen(s)-2] == '\r' || s[strlen(s)-2] == '\n')
		s[strlen(s)-2] = '\0';
	else if(s[strlen(s)-1] == '\r' || s[strlen(s)-1] == '\n')
		s[strlen(s)-1] = '\0';
}

int main(){
	char str[101];
	fgets(str, 100, stdin);
	int nth_word;
	scanf("%d", &nth_word);
	normalize_string(str);
	int i, counter = 1, start_ix = 0, end_ix = strlen(str);
	for(i = 0; str[i] != '\0'; i++){
		if(str[i] == ' '){
			counter++;
			if(counter == nth_word){
				start_ix = i;
			}else if(counter == nth_word + 1){
				end_ix = i;
				break;
			}
		}
	}

	if(start_ix == 0){
		end_ix++;
	}

	for(i = start_ix; str[i] != '\0'; i++){
		str[i] = str[i + end_ix - start_ix];
	}
	str[i+1] = '\0';
	printf("%s", str);
	return 0;
}
```

### Alternative

```c
void normalize_string(char s[]){
	if(s[strlen(s)-2] == '\r' || s[strlen(s)-2] == '\n')
		s[strlen(s)-2] = '\0';
	else if(s[strlen(s)-1] == '\r' || s[strlen(s)-1] == '\n')
		s[strlen(s)-1] = '\0';
}

int main(){
	char str[101];
	fgets(str, 100, stdin);
	int nth_word;
	scanf("%d", &nth_word);
	normalize_string(str);
	int i, counter = 1, start_ix = 0, end_ix = strlen(str);
	for(i = 0; str[i] != '\0'; i++){
		if(str[i] == ' '){
			counter++;
			if(counter == nth_word){
				start_ix = i;
			}else if(counter == nth_word + 1){
				end_ix = i;
				break;
			}
		}
	}

	if(start_ix == 0){
		end_ix++;
	}

	strcpy(str+start_ix, str+end_ix);
	printf("%s", str);
	return 0;
}
```

## Q6

### a

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
	char str[101];
	int n, i;
	fgets(str, 101, stdin);
	int freq[26] = {0};
	for(i=0; str[i] != '\0'; i++){
		freq[str[i] - 'a']++;
	}
	int max=0;
	char max_char;
	for(i=0; i<26; i++){
		if(freq[i] > max){
			max = freq[i];
			max_char = i + 'a';
		}
	}
	printf("%c", max_char);
	return 0;
}
```

### b

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
	char str[101];
	int n, i;
	fgets(str, 101, stdin);
	int freq[256] = {0};
	for(i=0; str[i] != '\0'; i++){
		freq[str[i]]++;
	}
	int max=0;
	char max_char;
	for(i=0; i<256; i++){
		if(freq[i] > max){
			max = freq[i];
			max_char = i;
		}
	}
	printf("%c", max_char);
	return 0;
}
```

## Q7

```c

#include <stdio.h>
#include <stdlib.h>
#include <string.h>

void strip(char str[]){
	int i;
	for(i=0; str[i] != '\0'; i++){
		if(str[i] == '\n' || str[i] == '\r')
			str[i]='\0';
	}
}

int main(){
	int i;
	char s1[100], s2[100];
	fgets(s1, 100, stdin);
	fgets(s2, 100, stdin);

	strip(s1);
	strip(s2);
	//
	// s1: merhaba dunyali nasilsin\0
	// s2: nasilsin\0
	for(i = 0; i < strlen(s1) - strlen(s2) + 1; i++){
		// it works if the condition would be i < strlen(s1), then it will compare the followings with "nasilsin" as well:
		// asilsin, silsin, ilsin, lsin, sin, in, n => redundant.
		if(strncmp(s1+i, s2, strlen(s2)) == 0){
			char temp[100];
			strcpy(temp, s1+i+strlen(s2));
			strcpy(s1+i-1, temp);
			break;
		}
	}
	puts(s1);
	return 0;
}

```

### Alternative

```c

#include <stdio.h>
#include <stdlib.h>
#include <string.h>

void strip(char str[]){
	int i;
	for(i=0; str[i] != '\0'; i++){
		if(str[i] == '\n' || str[i] == '\r')
			str[i]='\0';
	}
}

int main(){
	int i, j;
	char s1[100], s2[100];
	fgets(s1, 100, stdin);
	fgets(s2, 100, stdin);

	strip(s1);
	strip(s2);

	for(i = 0; i < strlen(s1) - strlen(s2) + 1; i++){
		int is_identical = 1;
		for(j = 0; j < strlen(s2); j++){
			if(s1[i+j] != s2[j]){
				is_identical = 0;
				break;
			}
		}
		//printf("%s %d\n", s1+i, is_identical);
		if(is_identical){
			char temp[100];
			strcpy(temp, s1+i+strlen(s2)+1);
			strcpy(s1+i, temp);
			break;
		}
	}
	puts(s1);

	return 0;
}
```

### To exclude all occurrences of the word

```c

#include <stdio.h>
#include <stdlib.h>
#include <string.h>

void strip(char str[]){
	int i;
	for(i=0; str[i] != '\0'; i++){
		if(str[i] == '\n' || str[i] == '\r')
			str[i]='\0';
	}
}

int main(){
	int i, j;
	char s1[100], s2[100];
	fgets(s1, 100, stdin);
	fgets(s2, 100, stdin);

	strip(s1);
	strip(s2);

	for(i = 0; i < strlen(s1) - strlen(s2) + 1; i++){
		int is_identical = 1;
		for(j = 0; j < strlen(s2); j++){
			if(s1[i+j] != s2[j]){
				is_identical = 0;
				break;
			}
		}
		//printf("%s %d\n", s1+i, is_identical);
		if(is_identical){
			char temp[100];
			// merhaba dunyali nasilsin dunyali\0
			// dunyali\0
			// strcpy(temp, s1+i+strlen(s2)+1);
			// temp = "nasilsin\0"
			// strcpy(s1+i, temp);
			strcpy(temp, s1+i+strlen(s2));
			// temp = " nasilsin\0"
			strcpy(s1+i-1, temp);
			i--;
		}
	}
	puts(s1);
	return 0;
}
```



## Q8

```c
#include <stdio.h>
#include <string.h>
void strip(char str[]){
	int i;
	for(i=0; str[i] != '\0'; i++){
		if(str[i] == '\n' || str[i] == '\r')
			str[i]='\0';
	}
}
int main(){
	char str[101];
	fgets(str, 101, stdin);
	int length = strlen(str);
	strip(str);
	int i, j;
	int num_of_words = 0;
	char words[10][10];
	int word_index = 0;
	for(i=0; str[i] != '\0'; i++){
		if(str[i] == ' '){
			words[num_of_words][word_index] = '\0';
			num_of_words++;
			word_index = 0;
		}else{
			words[num_of_words][word_index] = str[i];
			word_index++;
		}
	}
	words[num_of_words][word_index] = '\0';

	// Prints words to make sure we are able to split it to words.
	/*for(i = 0; i <= num_of_words; i++){
		for(j = 0; words[i][j] != '\0'; j++){
			printf("%c", words[i][j]);
		}
		printf("\n");
		// puts(words[i]); // equivalent to for loop and print newline above. 
	}*/


	char temp[10];
    // Bubble sort words of the sentence. 
	for(i = 0; i <= num_of_words; i++){
		for(j = i+1; j <= num_of_words; j++){
			if(strcmp(words[i], words[j]) > 0){
				strcpy(temp, words[i]);
				strcpy(words[i], words[j]);
				strcpy(words[j], temp);
			}
		}
	}

	for(i = 0; i <= num_of_words; i++){
		for(j = 0; words[i][j] != '\0'; j++){
			printf("%c", words[i][j]);
		}
		printf(" ");
	}

	return 0;
}
```

## Q9 

```c

#include <stdio.h>
#include <string.h>
void strip(char str[]){
	int i;
	for(i=0; str[i] != '\0'; i++){
		if(str[i] == '\n' || str[i] == '\r')
			str[i]='\0';
	}
}
int isSubstring(char s1[], char s2[]){
	int i;
	for(i = 0; i < strlen(s1) ; i++){
		if(strncmp(s1+i, s2, strlen(s2)) == 0){
			return 1;
		}
	}
	return 0;
}
int main(){
	char s1[100], s2[100];
	fgets(s1, 100, stdin);
	fgets(s2, 100, stdin);

	strip(s1);
    strip(s2);

	printf("%d", isSubstring(s1,s2));

	return 0;
}

```

### Alternative

```c

int isSubstring(char str[], char search_str[]){
	int len_str = strlen(str);
	int len_search_str = strlen(search_str);
	int substring_flag, i , j;

	// We search for the substring in string, using windows of length: len_search_str
	for(i=0;i<=len_str-len_search_str;i++)
	{
        substring_flag=1;
		for(j=i;j<i+len_search_str;j++)
		{
			if (str[j]!=search_str[j-i])
			{
				substring_flag=0;
			    break;
			}
		}
		if (substring_flag==1)
			break;
	}
	return substring_flag;
}

```

## Q10

```c

#include <stdio.h>
#include <string.h>
#define MAX 100

void strip(char str[]){
	int i;
	for(i=0; str[i] != '\0'; i++){
		if(str[i] == '\n' || str[i] == '\r')
			str[i]='\0';
	}
}

int main(){
	char str[MAX], longest[MAX], smallest[MAX], current[MAX];
	int i, j = 0, longest_length = 0, smallest_length = MAX, current_length;

	fgets(str, MAX, stdin);
	strip(str);
	for(i = 0; i <= strlen(str); i++){
		if(str[i] == ' ' || str[i] == '\0'){
			// We have reached a word, we add null character to its end
			current[j] = '\0';
			current_length = strlen(current);

			// printf("Word: %s, length = %d \n", current, current_length);

			// If current word is longer than the longest word yet seen
			if(current_length > longest_length){
				longest_length = current_length;
				strcpy(longest, current);
			}

			// If current word is smaller than the smallest word yet seen
			if(current_length < smallest_length){
				smallest_length = current_length;
				strcpy(smallest, current);
			}

			j = 0; // we must reset the index of the next word

		}
		else{
			current[j] = str[i];
			j++;
		}
	}
	printf("Largest: %s \n", longest);
	printf("Smallest: %s \n", smallest);

	return 0;
}
```

### Alternative 1 

```c
#include <stdio.h>
#include <string.h>
#define MAX 100
void strip(char str[]){
	int i;
	for(i=0; str[i] != '\0'; i++){
		if(str[i] == '\n' || str[i] == '\r')
			str[i]='\0';
	}
}

int main(){
	char str[MAX];
	fgets(str, MAX, stdin);
	strip(str);
	int i, start_ix=0, end_ix=-1, longest=-1, smallest=MAX;
	int long_start, small_start;
	for(i = 0; i <= strlen(str); i++){
		if(str[i] == ' ' || str[i] == '\0'){
			end_ix = i - 1;
			int word_size = end_ix - start_ix + 1;
			if(word_size > longest){
				longest = word_size;
				long_start = start_ix;
			}
			if(word_size < smallest){
				smallest = word_size;
				small_start = start_ix;
			}
			start_ix = i + 1;
		}
	}
	char long_word[MAX] = "", small_word[MAX] = "";
	strncat(long_word, str + long_start, longest);
	strncat(small_word, str + small_start, smallest);
	// strncat() is used because it appends '\0' at the end of string strncpy() does not.
	puts(long_word);
	puts(small_word);
	return 0;
}


```

### Alternative 2

```c
include <stdio.h>
#include <string.h>
#define MAX 100

void strip(char str[]){
	int i;
	for(i=0; str[i] != '\0'; i++){
		if(str[i] == '\n' || str[i] == '\r')
			str[i]='\0';
	}
}

int main(){
	char str[MAX];
	fgets(str, MAX, stdin);
	strip(str);
	int starts[MAX] = {0};
	int i, counter = 1;
	for(i = 0; i <= strlen(str); i++){
		if(str[i] == ' ' || str[i] == '\0'){
			starts[counter++] = i + 1;
		}
	}
	for(i = 0; i < counter; i++){
		printf("%d,", starts[i]);
	}

	char long_word[MAX] = "", small_word[MAX] = "";
	int longest = -1, smallest = MAX, long_ix, small_ix;
	for(i = 0; i < counter - 1 ; i++){
		int length = starts[i+1] - starts[i] - 1;
		if(length > longest){
			long_ix = i;
			longest = length;
		}
		if(length < smallest){
			small_ix = i;
			smallest = length;
		}
	}
	strncat(long_word, str+starts[long_ix], longest);
	strncat(small_word, str+starts[small_ix], smallest);
	puts(long_word);
	puts(small_word);
	return 0;
}

```

### Alternative 3

```c

#include <stdio.h>
#include <string.h>
#define MAX 100
void strip(char str[]){
	int i;
	for(i=0; str[i] != '\0'; i++){
		if(str[i] == '\n' || str[i] == '\r')
			str[i]='\0';
	}
}
int main(){
	char str[MAX];
	fgets(str, MAX, stdin);
	strip(str);
	int i, start_ix = 0;
	int longest = -1, smallest = MAX, long_ix, small_ix;
	for(i = 0; i <= strlen(str); i++){
		if(str[i] == ' ' || str[i] == '\0'){
			int len = i - start_ix;
			if(len > longest){
				longest = len;
				long_ix = start_ix;
			}
			if(len < smallest){
				smallest = len;
				small_ix = start_ix;
			}
			start_ix = i + 1;
		}
	}
	char long_word[MAX]="", small_word[MAX] = "";
	strncat(long_word, str+long_ix, longest);
	strncat(small_word, str+small_ix, smallest);
	puts(long_word);
	puts(small_word);
	return 0;
}
```

