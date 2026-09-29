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
