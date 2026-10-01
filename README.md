# 실습과제 1
---
```c
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
```
- 헤더파일 선언

```c
int main(void){
    
    int arr1[2][2] = {
        {2, 4},
        {5, -5}
    };
    
    int arr2[2][2] = {
        {-2, 3},
        {0, -5}
    };
    
    int result[2][2];
```
- 더할 두 2차원 배열 초기화 및 결과를 도출할 2차원 배열 선언

```c
    for(int i = 0; i < 2; i++){
        
        for(int j = 0; j < 2; j++){
            
            result[i][j] = arr1[i][j] + arr2[i][j];
        }
    }
```
- 2중 반복문을 통해 배열 값을 더해서 결과에 대입하기

```c
    for(int i = 0; i < 2; i++){
        for(int j = 0; j < 2; j++){
            printf("%d ", result[i][j]);
        }
        
        printf("\n");
    }
    
    return 0;
}
```
- 결과값 출력 후 코드 종료


# 실습과제 3
---
```c
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
```
- 

int main(void){
    
    int arr[3][3] = {
        
        {-5, 2, 35},
        {-20, 5, 100},
        {-75, 5, -25}
    };
    
    int max = arr[0][0];
    int max_row = 0;
    int max_col = 0;
    
    for(int i = 0; i < 3; i++){
        
        for(int j = 0; j < 3; j++){
            
            if (arr[i][j] > max){
                
                max = arr[i][j];
                max_row = i;
                max_col = j;
            }
        }
    }
    
    printf("최대값의 위치 : %d행 %d열\n", max_row + 1, max_col + 1);
    printf("최대값은 : %d\n", max);
    
    return 0;
}
