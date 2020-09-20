## Structures

### Question 1 - Distance

```c
#include <stdio.h>
#include <stdlib.h>
#include <math.h>

struct point{
    int x;
    int y;
};

float distance(struct point p1, struct point p2){
    return sqrt(pow(p1.x - p2.x, 2) + pow(p1.y - p2.y, 2));
}

struct point closest_to_origin(struct point p1, struct point p2){
    struct point origin = {0, 0};
    float p1_dist = distance(p1, origin);
    float p2_dist = distance(p2, origin);
    return p1_dist < p2_dist ? p1 : p2;
}

int main() {
    struct point p1;
    struct point p2;
    scanf("%d%d", &p1.x, &p1.y);
    scanf("%d%d", &p2.x, &p2.y);

    // printf("%f", distance(p1, p2));
    struct point closest = closest_to_origin(p1, p2);
    printf("%d %d", closest.x, closest.y);

    return 0;
}
```

<br>

### Question 2 - Extreme Points

```c
#include <stdio.h>
#include <math.h>

typedef struct{
    float x;
    float y;
}Point_t;

float distance(Point_t p1, Point_t p2){
    return sqrt( pow(p1.x-p2.x, 2) + pow(p1.y-p2.y, 2) );
}


int main(){
    int i, j, N;
    scanf("%d", &N);

    Point_t pArr[N];
    for(i = 0 ; i < N ; i++)
        scanf("%f %f", &pArr[i].x, &pArr[i].y);

    Point_t p1 = pArr[0], p2 = pArr[1];
    float max_dist = distance(p1, p2);

    for(i = 0 ; i < N-1 ; i++){
        for(j = i+1 ; j < N ; j++){
            if(distance(pArr[i], pArr[j]) > max_dist){
                max_dist = distance(pArr[i], pArr[j]);
                p1 = pArr[i];
                p2 = pArr[j];
            }
        }
    }

    printf("%.2f %.2f\n", p1.x, p1.y);
    printf("%.2f %.2f\n", p2.x, p2.y);

    return 0;
}

```

<br>

### Question 3 - Moving Rectangle

```c
#include <stdio.h>

typedef struct{
    float x;
    float y;
}Point_t;

typedef struct{
    Point_t ll, ur;
}Rect_t;

void move(Rect_t *r, int moveX, int moveY){
    r->ll.x += moveX;
    r->ll.y += moveY;

    r->ur.x += moveX;
    r->ur.y += moveY;
}

int main(){
    Rect_t r;
    scanf("%f %f %f %f", &r.ll.x, &r.ll.y, &r.ur.x, &r.ur.y);

    int moveX, moveY;
    scanf("%d %d", &moveX, &moveY);

    move(&r, moveX, moveY);

    printf("%.2f %.2f %.2f %.2f\n", r.ll.x, r.ll.y, r.ur.x, r.ur.y);

    return 0;
}
```

<br>

### Question 4 - Letter Grades

```c
#include <stdio.h>

// Fill the definition of the struct.
typedef struct{
    int student_id;
    float mt_grade;
    float final_grade;
    char letter_grade;
} Student;

void set_grade(Student *p){
    float score;
    score = p->mt_grade * 0.4 + p->final_grade * 0.6;

    if(score > 75)
        p->letter_grade = 'A';
    else if(score > 50)
        p->letter_grade = 'B';
    else if(score > 25)
        p->letter_grade = 'C';
    else
        p->letter_grade = 'F';
}

int main(){
    int N;
    scanf("%d", &N);
    Student cmpe[N];
    int i;
    for(i=0; i < N; i++){
        scanf("%f %f", &cmpe[i].mt_grade, &cmpe[i].final_grade);
        cmpe[i].student_id = 1000 + i;
        // Call set grade function
        set_grade(&cmpe[i]);
    }

    for(i = 0; i < N; i++)
        printf("%d %c\n", cmpe[i].student_id, cmpe[i].letter_grade);

    return 0;
}

```

<br>

### Question 5 - Flights

```c
#include <stdio.h>
#include <string.h>

typedef struct{
    int flight_no;
    char org[4];
    char dst[4];
    int start;
    int arrival;
}Flight_t;

Flight_t read_flight(){
    Flight_t fl;
    scanf("%d %s %s %d %d", &fl.flight_no, fl.org, fl.dst, &fl.start, &fl.arrival);
    return fl;
}

void print_flight(Flight_t f){
    printf("%d %s %s %d %d\n", f.flight_no, f.org, f.dst, f.start, f.arrival);
}

int main() {
    int N, i;
    scanf("%d", &N);
    Flight_t flights[N];
    for(i = 0; i < N; i++){
        flights[i] = read_flight();
    }
    char org[4], dst[4];
    scanf("%s %s", org, dst);
    for(i = 0; i < N; i++){
        if(strcmp(flights[i].org, org) == 0 && strcmp(flights[i].dst, dst) == 0){
            print_flight(flights[i]);
        }
    }

    return 0;
}
```

<br>

### Question 6 - Sorted Flights

```c
#include <stdio.h>
#include <string.h>

typedef struct{
    int flight_no;
    char org[4];
    char dst[4];
    int start;
    int arrival;
}Flight_t;

Flight_t read_flight(){
    Flight_t fl;
    scanf("%d %s %s %d %d", &fl.flight_no, fl.org, fl.dst, &fl.start, &fl.arrival);
    return fl;
}

void print_flight(Flight_t f){
    printf("%d %s %s %d %d\n", f.flight_no, f.org, f.dst, f.start, f.arrival);
}

/*
 * sorts flights according to their
 * starting time and the originating airport code.
 *
 * if f1 > f2 return 1
 * if f1 == f2 return 0
 * if f1 < f2 return -1
 */
int compare_flights(Flight_t *f1, Flight_t *f2){
    if(f1->start > f2->start)
        return 1;
    else if(f1->start < f2->start)
        return -1;
    else{
        if(strcmp(f1->org, f2->org) > 0)
            return 1;
        else if(strcmp(f1->org, f2->org) < 0)
            return -1;
        else
            return 0;
    }
}

int main(){
    int i, j;
    int N;
    scanf("%d", &N);

    Flight_t flights[N];

    for(i = 0 ; i < N ; i++){
        flights[i] = read_flight();
    }


    for(i = 0 ; i < N ; i++){
        for(j = 0 ; j < N-1 ; j++){
            if(compare_flights(&flights[j], &flights[j+1]) > 0){
                Flight_t temp = flights[j];
                flights[j] = flights[j+1];
                flights[j+1] = temp;
            }
        }
    }


    for(i = 0 ; i < N ; i++)
        print_flight(flights[i]);

    return 0;
}
```

<br>

### Question 7 - Book Prices

```c
#include <stdio.h>

struct book{
    int page;
    int price;
    char name[5];
};

void sort_books(struct book bArr[], int n){
    int i, j;

    for(i = 0 ; i < n ; i++){
        for(j = 0 ; j < n-1 ; j++){
            if(bArr[j].price > bArr[j+1].price){
                struct book temp = bArr[j];
                bArr[j] = bArr[j+1];
                bArr[j+1] = temp;
            }
        }
    }
}

int main() {
    int i, n;
    scanf("%d", &n);

    struct book bArr[n];
    for(i = 0 ; i < n ; i++)
        scanf("%d %s %d", &bArr[i].page, bArr[i].name, &bArr[i].price);

    sort_books(bArr, n);

    for(i = 0 ; i < n ; i++)
        printf("%s: %d pages (%d gold)\n", bArr[i].name, bArr[i].page, bArr[i].price);

    return 0;
}

```

<br>

### Question 8 - Smaller Better Faster Stronger (2018 Fall Final Q4)

```c
#include <stdio.h>

typedef struct rectangle{
    float edge1;
    float edge2;
}Rectangle;

// DO_NOT_EDIT_ANYTHING_ABOVE_THIS_LINE
    
Rectangle min_rectangle_area(Rectangle rect[], int N){
    int i;
    Rectangle min_rect = rect[0];

    for(i = 1 ; i < N ; i++)
        if(rect[i].edge1 * rect[i].edge2 < min_rect.edge1 * min_rect.edge2)
            min_rect = rect[i];

    return min_rect;
}

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
    r, N
    // DO_NOT_EDIT_ANYTHING_BELOW_THIS_LINE
    );
    
    // Prints the area of the rectangle that has the smallest area
    printf("%.2f\n", r_min.edge1*r_min.edge2);
        
    return 0;
}

```

<br>

### Question 9 - Family

```c
#include <stdio.h>
#include <stdlib.h>

struct Person{
    int age;
    int salary;
};

typedef struct Family{
    struct Person persons[9];
    int personCount;
} Fam_t;

int poorest_family(Fam_t f[], int size){
    int min_salary = 0;
    int i, j, index = 0;
    
    for(j = 0; j < f[0].personCount; j++){
        min_salary += f[0].persons[j].salary;
    }

    for(i = 1; i < size; i++){
        int total = 0;
        for(j = 0; j < f[i].personCount; j++){
            total += f[i].persons[j].salary;
        }
        if(total < min_salary){
            min_salary = total;
            index = i;
        }
    }
    return index;
}

int richest_member(struct Family f){
    int i, max = 0, index = -1;
    for(i = 0; i < f.personCount; i++){
        if(f.persons[i].salary > max){
            max = f.persons[i].salary;
            index = i;
        }
    }
    return index;
}


int main() {
    struct Family families[3];
    int i, j;
    for(i = 0; i < 3; i++){
        scanf("%d", &families[i].personCount);
        for(j = 0; j < families[i].personCount; j++){
            scanf("%d%d", &families[i].persons[j].age, &families[i].persons[j].salary);
        }
    }
    int poorest = poorest_family(families, 3);
    int richest = richest_member(families[poorest]);
    printf("Richest person in the poorest family is %d years old.\n", families[poorest].persons[richest].age);
    return 0;
}
```

