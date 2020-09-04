### Warm Up Question - Rook and Pawns

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

## Strings

### Question 1 - Length 

```c
#include <stdio.h>
#include <string.h>
#define MAX 50

void normalizeString(char s[]){
    if(s[strlen(s)-2] == '\r' || s[strlen(s)-2] == '\n')
        s[strlen(s)-2] = '\0';
    else if(s[strlen(s)-1] == '\r' || s[strlen(s)-1] == '\n')
        s[strlen(s)-1] = '\0';
}

int length(char s[]){
	int i;

	for(i = 0; s[i] != '\0'; i++);

	return i;
}

int main(){
	char string[MAX];

	fgets(string, MAX, stdin);
	normalizeString(string);
	printf("%d", length(string));

    return 0;
}
```

### Question 2 - Copy

```c
#include <stdio.h>
#include <string.h>
#define MAX 50

void copystr(char dest[], char src[]){
	int idx = 0;
	while(src[idx]!='\0'){
		dest[idx] = src[idx];
		idx++;
	}
	dest[idx] = '\0';
}

int main(){
	char source[MAX],destination[MAX];
	char xx[MAX];
	fgets(source, MAX, stdin);
	copystr(destination, source);

	printf("Source string: %s",source);
	printf("Destination string: %s",destination);

	strcpy(xx,source);
	printf("From strcpy %s",xx);

    return 0;
}
```

### Question 3 - Compare

```c
#include <stdio.h>
#include <string.h>

int mystrcmp(char s1[], char s2[]){
	int i;
	for(i = 0 ; i < strlen(s1)+1 && i < strlen(s2)+1 ; i++)
		if(s1[i] - s2[i] != 0)
			return s1[i]-s2[i];

	return 0;
}

int main()
{
	int i;
	char s1[100], s2[100];
	fgets(s1, 100, stdin);
	fgets(s2, 100, stdin);

	printf("mystrcmp(s1,s2) --> %d ?==? %d <-- strcmp(s1,s2)", mystrcmp(s1,s2), strcmp(s1,s2));

	return 0;
}
```

### Question 4 - Count Words

```c
#include <stdio.h>
#include <string.h>

int main(){
	char string[101];
	int i, counter = 1;
	fgets(string, 101, stdin);

	for(i = 0; string[i] != '\0'; i++){
		if(string[i] == ' '){
			counter++;
		}
	}

	printf("%d", counter);

}
```

### Question 5.a - nth Word

```c
#include <stdio.h>
#include <string.h>

int main(){
	char string[101], word[101] = "";
	int i, n, word_counter = 1, word_idx = 0;

	fgets(string, 101, stdin);
	scanf("%d", &n);

	for(i = 0; string[i] != '\0'; i++){
		if(word_counter == n){
			word[word_idx] = string[i];
			word_idx++;
		}
		if(string[i] == ' '){
			word_counter++;
		}
	}

	puts(word);

	return 0;
}
```

### Question 5.b - nth Word

```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#define MAX 150

void worderaser(char str[], int x)
{
	int i, counter=1;
	int start_ix = 0; // beginning of the first word
	int end_ix = strlen(str)-1; // end of the last word

	for(i = 0; str[i] != '\0'; i++){
		if(str[i] == ' '){
			counter++;
			if(counter == x){
				start_ix = i + 1; // the start index of nth word
			}
			if(counter == x + 1){ // the index of the space after the nth word
				end_ix = i;
				break;
			}
		}
	}

	if(strlen(str)-1 == end_ix){
		start_ix -= 1; // for the last space before the last word
	}

	strcpy(str + start_ix, str + end_ix + 1);

}

int main(void) {
	char str[MAX];
	int num;
	fgets(str,MAX,stdin);
	scanf("%d",&num);
	worderaser(str,num);
	printf("%s",str);

	return 0;
}
```

### Question 6.a - Frequentt

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
	char str[101];
	int i;
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

### Question 6.b - Frequentt

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

### Question 7 - Exclude

```c
#include <stdio.h>
#include <string.h>

void normalizeString(char s[]){
    if(s[strlen(s)-2] == '\r' || s[strlen(s)-2] == '\n')
        s[strlen(s)-2] = '\0';
    else if(s[strlen(s)-1] == '\r' || s[strlen(s)-1] == '\n')
        s[strlen(s)-1] = '\0';
}

int main(){
	int i;
	char s1[100], s2[100];
	fgets(s1, 100, stdin);
	fgets(s2, 100, stdin);

	normalizeString(s1);
	normalizeString(s2);

	for(i = 0 ; i < strlen(s1) ; i++){
		if(strncmp(s1+i, s2, strlen(s2)) == 0){
			strcpy(s1+i, s1+i+strlen(s2)+1);
			break;
		}
	}

	puts(s1);

	return 0;
}
```

### Question 8 - Sort

```c
#include <stdio.h>
#include <string.h>

void normalizeString(char s[]){
    if(s[strlen(s)-2] == '\r' || s[strlen(s)-2] == '\n')
        s[strlen(s)-2] = '\0';
    else if(s[strlen(s)-1] == '\r' || s[strlen(s)-1] == '\n')
        s[strlen(s)-1] = '\0';
}

int main(){
	char str[101];
	fgets(str, 101, stdin);
	normalizeString(str);

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

### Question 9 - Substring

```c
#include <stdio.h>
#include <string.h>
#define MAX 100

void normalizeString(char s[]){
    if(s[strlen(s)-2] == '\r' || s[strlen(s)-2] == '\n')
        s[strlen(s)-2] = '\0';
    else if(s[strlen(s)-1] == '\r' || s[strlen(s)-1] == '\n')
        s[strlen(s)-1] = '\0';
}

int isSubstring(char str[], char search_str[]){
	int i;

	for(i = 0 ; i < strlen(str) ; i++){
		if(strncmp(str+i, search_str, strlen(search_str)) == 0){
			return 1;
		}
	}
	return 0;
}


int main()
{
	char str[MAX],search[MAX];

    fgets(str, MAX, stdin);
	fgets(search, MAX, stdin);

	normalizeString(search);

	printf("%d", isSubstring(str, search));

	return 0;
}
```

### Question 10 - Word Lengths

```c
#include <stdio.h>
#include <string.h>
#define MAX 100

void normalizeString(char s[]){
    if(s[strlen(s)-2] == '\r' || s[strlen(s)-2] == '\n')
        s[strlen(s)-2] = '\0';
    else if(s[strlen(s)-1] == '\r' || s[strlen(s)-1] == '\n')
        s[strlen(s)-1] = '\0';
}

int main()
{
    char str[MAX], longest[MAX], smallest[MAX], current[MAX];
    int i, j = 0, longest_length = 0, smallest_length = MAX, current_length;

    fgets(str, MAX, stdin);
    normalizeString(str);

    for(i = 0; i <= strlen(str); i++){
    	if(str[i] == ' ' || str[i] == '\0'){
    		//We have reached a word, we add null character to its end
    		current[j] = '\0';
			current_length = strlen(current);

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

### Extra: String to Lowercase

```c
#include <stdio.h>
#include <string.h>
#define MAX 50

void toLower(char y[]){
	int i;

	int shift = 'a' - 'A';
	for(i = 0; y[i] != '\0'; i++){
		if(y[i] >= 'A' && y[i] <= 'Z'){
			y[i] += shift;
		}
	}
}

int main(){
	char string[MAX];

	fgets(string, MAX, stdin);
	toLower(string);

	puts(string);

    return 0;
}
```

### Extra: ReVeRsE 

```c
#include <stdio.h>
#include <string.h>
#define MAX 50

void reverse(char y[]){
	int i;

	int shift = 'a' - 'A';
	for(i = 0; y[i] != '\0'; i++){
		if(y[i] >= 'A' && y[i] <= 'Z'){
			y[i] += shift;
		}
		else if(y[i] >= 'a' && y[i] <= 'z'){
			y[i] -= shift;
		}
	}
}

int main(){
	char string[MAX];

	fgets(string, MAX, stdin);
	reverse(string);

	puts(string);

    return 0;
}
```
