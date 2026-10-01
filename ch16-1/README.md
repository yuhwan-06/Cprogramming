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
- <img width="80" height="54" alt="image" src="https://github.com/user-attachments/assets/bba8dc98-3ea1-4037-ad38-dad399674ef9" />


# 실습과제 2
---
```c
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
```
- 헤더파일 선언

```c
int main(void) {

    int score[3][3];
    double avg[3];

    int max_student = 0;
```
- 점수를 입력받을 변수와, 갱신할 평균과 최고점수 학생 변수 선언

```c
    for (int i = 0; i < 3; i++) {

        printf("%d번째 학생의 국어, 영어, 수학 성적을 입력: ", i + 1);
        scanf("%d %d %d", &score[i][0], &score[i][1], &score[i][2]);

        avg[i] = (score[i][0] + score[i][1] + score[i][2]) / 3.0;
    }
```
- 반복문을 통해 점수 입력받고 평균 점수 갱신

```c
    for (int i = 1; i < 3; i++) {

        if (avg[i] > avg[max_student]) {
            max_student = i;
        }
    }
```
- 조건문을 통해 최고점수 학생 갱신

```c
    printf("최우수 학생은 %d번째 학생이고 평균점수는 %.0f점이다.\n",
           max_student + 1, avg[max_student]);

    return 0;
}
```
- 결과 출력 및 코드 종료
- <img width="495" height="107" alt="image" src="https://github.com/user-attachments/assets/5baed5a4-16ce-4f0b-b7f7-5e83f993c206" />

# 실습과제 3
---
```c
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
```
- 헤더파일 선언

```c
int main(void){
    
    int arr[3][3] = {
        
        {-5, 2, 35},
        {-20, 5, 100},
        {-75, 5, -25}
    };
```
- 3x3 크기에 2차원 배열 선언

```c
    int max = arr[0][0];
    int max_row = 0;
    int max_col = 0;
```
- 갱신할 최대값과 최대값에 행렬 값 선언 및 초기화

```c
    for(int i = 0; i < 3; i++){
        
        for(int j = 0; j < 3; j++){
            
            if (arr[i][j] > max){
                
                max = arr[i][j];
                max_row = i;
                max_col = j;
            }
        }
    }
```
- 이중 반복문 내부에서 조건문을 통해 최대값과 그에 맞는 행렬값 갱신

```c
    printf("최대값의 위치 : %d행 %d열\n", max_row + 1, max_col + 1);
    printf("최대값은 : %d\n", max);
    
    return 0;
}
```
결과값 출력 및 코드 종료
<img width="225" height="52" alt="image" src="https://github.com/user-attachments/assets/ffe8d4f1-4599-414c-8a8b-815b47ff8130" />

# 실습과제 4
---
```c
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
```
- 헤더파일 선언
  
```c
int main(void) {

    char str[4][10];
    int lens[4];
```
- 입력뱓을 문자열과 개수를 받을 변수 선언

```c
    for(int i = 0; i < 4; i++){
        
        printf("%d번째 문자 입력 : ", i + 1);
        scanf("%s", str[i]);
        
        for(int j = 0; str[i][j] != '\0'; j++){
            
            lens[i] = j + 1;
        }
    }
```
- 반복문 바깥에서 문자를 입력받고 안쪽에서 길이 카운트

```c
    for(int i = 0; i < 4; i++){
        printf("%d번째 문자 길이 : %d\n", i + 1, lens[i]);
    }
    
    return 0;
}
```
- 결과 출력및 코드 종료
<img width="263" height="203" alt="image" src="https://github.com/user-attachments/assets/bd11ad39-e7cf-45ce-897f-8269bb60949e" />
  
# 실습과제 5
---
```c
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
```
- 헤더파일 선언

```c
int main(void) {

    char str[4][10];
    int last = 0;
```
- 입력받을 문자열 4개를 저장할 2차원 배열과, 사전에서 제일 뒤에 나오는 문자열의 행 번호를 저장할 변수 선언

```c
    for(int i = 0; i < 4; i++){

        printf("%d번째 문자열 입력: ", i + 1);
        scanf("%s", &str[i][0]);

        if(str[i][0] > str[last][0]){
            last = i;
        }
    }
```
- 반복문 안에서 문자열을 입력받고, 첫 문자를 비교해서 가장 뒤에 나오는 문자열의 행 번호를 갱신

```c
    printf("사전에서 제일 뒤에 나오는 문자열: %s\n", str[last]);

    return 0;
}
```
- 결과 출력 및 코드 종료
<img width="370" height="127" alt="image" src="https://github.com/user-attachments/assets/e15e33eb-06af-4ced-8852-2c41e8219721" />
