# 실습과제 1

<img width="911" height="676" alt="image" src="https://github.com/user-attachments/assets/00744616-44da-46ae-bd98-dbec1f8e1d38" />

# 실습과제 2

```c
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
```
- 헤더파일 선언

```c
int Get_Max(int **dptrarr, int size);
```
- 최대값을 구할 함수 선언

```c
int main(void) {

    int num1 = 50, num2 = 20, num3 = 30;
    int* ptrarr[3] = {&num1, &num2, &num3};
    int max;
```
- 변수들과 변수들의 주소값을 저장하는 포인터 배열, 최대값을 저장할 변수 선언

```c
    max = Get_Max(ptrarr, 3);
    printf("최대값 : %d\n", max);
    
    return 0;
}
```
- 최대값 함수를 호출해서 변수에 대입 후 최대값 출력, 코드 종료

```c
int Get_Max(int **dptarr, int size){
    
    int max = *dptarr[0];
```
- 최대값을 포인터 배열 첫번째 값으로 초기화

```c
    for(int i = 0; i < size; i++){
        
        if(*dptarr[i] > max){
            max = *dptarr[i];
        }
    }
```
- 최대값 구하는 알고리즘으로 최대값 구하기

```c 
    return max;
}
```
- 최대값을 반환 후 코드 함수 종료


# 실습과제 3

```c 
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
```
- 헤더파일 선언

```c 
void prn_str(char **ptrarr, int count);
```
- 문자를 출력할 함수 선언

```c 
int main(void) {
    
    char *ptrarr[] = {"eagle", "tiger", "lion", "squillr"};
    int count;
    count = sizeof(ptrarr)/sizeof(ptrarr[0]);
```
- char형의 포인터 배열 선언 후 초기화, 포인터 배열의 크기 선언 후 초기화

```c 
    prn_str(ptrarr, count);
    
    return 0;
}
```
- 출력함수 호출 후 코드 종료

```c 

void prn_str(char **ptrarr, int count){
    
    for(int i = 0; i < count; i++){
        
        printf("%s\n", ptrarr[i]);
    }
}
```
- 반복문을 사용하여 문자열 출력


# 실습과제 4

```c
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>

void MaxAndMin(int [], int **, int **);

int main(void){
    
    int *maxPtr, *minPtr;
    int arr[5];
    
    for(int i = 0; i < 5; i++){
        
        printf("%d번째 숫자 입력 : ", i + 1);
        scanf("%d", &arr[i]);
    }
    
    MaxAndMin(arr, &maxPtr, &minPtr);
    
    printf("최대 : %d, 최소 : %d\n", *maxPtr, *minPtr);
    
    return 0;
}


void MaxAndMin(int arr[], int **maxptr, int **minptr){
    
    int *max, *min;
    
    max = min = &arr[0];
    
    for(int i = 0; i < 5; i++){
        
        if(*max < arr[i]) max = &arr[i];
        if(*min > arr[i]) min = &arr[i];
    }
    
    *maxptr = max;
    *minptr = min;
}
```
