# 실습과제 1
1. 주소에 의한 호출을 사용해야 하는 3가지 경우를 설명하라.

① 원본 데이터를 직접 수정해야 할 때
② 반환해야 하는 값이 여러 개일 때
③ 배열과 같이 용량이 큰 데이터를 전달할 때
   → 주소값만 전달하기 때문에 메모리 사용을 줄일 수 있다.


2. 최대값을 구하는 알고리즘을 설명하라.

구하려는 값들 중 하나를 최대값으로 정하고,
반복문을 통해 다른 값들과 비교하면서 더 큰 값이 나오면
최대값을 갱신한다.


3. const 선언을 사용하는 이유를 설명하시오.

값이 변경되는 것을 방지하기 위해 사용한다.


# 실습과제 2

```c
#include <stdio.h>

int main(void){
    
    int arr[5];
    
    printf("정수 5개 입력\n");
    
    for(int i = 0; i < 5; i++){
        
        printf("%d번째 정수 : ", i + 1);
        scanf("%d", &arr[i]);
    }
    
    int min = arr[0];
    
    for(int i = 0; i < 5; i++) {if(min > arr[i]) min = arr[i];}
    
    printf("최소값 : %d\n", min);
    return 0;
}
```

# 실습과제 3

```c
#include <stdio.h>

void get_data(int []);

int main(void)
{
    int i, data[5];

    get_data(data);

    for(i = 0; i < 5; i++)
        printf("%d번째 data: %d\n", i+1, data[i]);

    return 0;
}

void get_data(int arr[])
{
    for(int i = 0; i < 5; i++)
    {
        printf("%d번째 data를 입력하시오: ", i + 1);
        scanf("%d", &arr[i]);
    }
}
```

# 실습과제 4

```c
#include <stdio.h>
void get_parts(double num, int *int_part, double *frac_part);

int main(void) {
    double num;
    int integer_part;
    double fractional_part;

    printf("실수를 입력하시오 : ");
    scanf("%lf", &num);

    get_parts(num, &integer_part, &fractional_part);

    printf("정수부 : %d\n", integer_part);
    printf("소수부 : %g\n", fractional_part);

    return 0;
}

void get_parts(double num, int *int_part, double *frac_part) {
    *int_part = (int)num;
    *frac_part = num - *int_part; 
}
```

# 실습과제 5

## 교재 324페이지 2번 문제

```c
void ShowData(const int * ptr){
    int * nptr=ptr;
    printf("%d ln", *rptr);
    *nptr=20;
}

int main (void){
 int num=10;
 int * ptr=&num;
 ShowData(ptr);
 return 0;
}

```
- 위 코드에 문제점 : 값을 수정하지 않을 const 값을 억지로 변경하려 했기 때문


# 도전 문제 1

---
```c
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
```

헤더 파일 선언

```c
void Even(int arr[]);
void Odd(int arr[]);
```

짝수 홀수를 나눌 함수 선언

```c

int main(void){
    int arr[10];
    
    for(int i = 0; i < 10; i++){
        printf("입력 : ");
        scanf("%d", &arr[i]);
    }
    
    Even(arr);
    Odd(arr);
}

```

메인함수에서 배열을 입력받고 각각의 함수를 호출

```c

void Even(int arr[]){
    printf("짝수 출력 : ");
    
    for(int i = 0; i < 10; i++){
        if(arr[i] % 2 == 0){
            printf("%d ", arr[i]);
        }
    }
    
    printf("\n");
}

```
반복문 안에서 조건문을 통해 짝수 조건 판별 후 출력

```c

void Odd(int arr[]){
    printf("홀수 출력 : ");
    
    for(int i = 0; i < 10; i++){
        if(arr[i] % 2 != 0){
            printf("%d ", arr[i]);
        }
    }
}
```

반복문 안에서 조건문을 통해 홀수 조건 판별 후 출력

## 도전과제1 실행 결과
<img width="232" height="290" alt="image" src="https://github.com/user-attachments/assets/cfc38340-0219-41f2-9abc-799ad5d8188d" />

---

#도전과제 2

```c

---

#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>

```

헤더파일 선언

```c

void Trans(int arr[], int n);

```

2진수로 변경할 함수 선언

```c

int main(void){
    int arr[100];
    
    int n;
    printf("10진수 입력 : ");
    scanf("%d", &n);
    
    Trans(arr, n);
    return 0;
}

```

입력 받을 10진수와 변환할 함수 호출

```

```c

void Trans(int arr[], int n){
    int i = 0;
    
    while(n > 0){
        arr[i] = n % 2;
        n /= 2;
        i++;
    }
    
    for(int j = i - 1; j >= 0; j--){
        printf("%d", arr[j]);
    }
    
    printf("\n");
}

```

while문을 통해 2진수 변환 공식으로 배열에 저장 후 for문에서 배열에 역순으로 출력해서 되기 때문에 j-- 라는 조건을 달아 역순으로 출력

## 도전과제 2 실행 결과
<img width="167" height="48" alt="image" src="https://github.com/user-attachments/assets/a7c2504b-63e5-48d7-b2a5-96c6e7e6d2e2" />


# 도전과제 3

```c
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>

```

헤더파일 선언

```c
void Sort(int *, int*);

```

숫자를 분류할 함수 선언

```c

int main(void){
    int arr[10]; int result[10];

```

입력받을 배열과 결과를 도출할 배열 선언

```c
    for(int i = 0; i < 10; i++){
        
        printf("입력 : " );
        scanf("%d", &arr[i]);
    }

```

반복문을 통해 입력받기

```c
    Sort(arr, result);

```

분류 함수를 호출

```c
    for(int i = 0; i < 10; i++){
        
        printf("%d ", result[i]);
    }
    
    printf("\n");
    
    return 0;
}

```

반복문을 통해 결과 배열을 도출

```c
void Sort(int *arr, int *result){


```

```c
    int left = 0;
    int right = 9;

```

짝수는 오른쪽부터 역순으로 출력해야 하니 초기 값을 9로 초기화, 홀수는 정방향으로 출력이니 0으로 값을 초기화

```c
    for(int i = 0; i < 10; i++){
        
        if(arr[i] % 2 == 0){
            result[right] = arr[i];
            right--;
        }
        
        else {
            result[left] = arr[i];
            left++;
        }
    }
}
```

짝수는 배열에 9번째 부터 채워나가며 right 변수를 빼나가고, 홀수는 0번째 부터 left 변수를 키워나가며 채운다

## 도전과제3 실행 결과
