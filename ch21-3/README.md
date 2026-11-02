# 실습과제1
```c
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#include <string.h>
```
- 헤더파일 선언

```c
int main(void) {
    
    char res_str[50] = "";
```
- 입력받은 문자열에 붙여 넣을 배열 선언

```c
    while(1) {
        
        char add_str[20];
        printf("문자열 입력 : ");
        fgets(add_str, sizeof(add_str), stdin);
```
- 이어 붙일 문자열 선언 및 입력받기

```c
        add_str[strlen(add_str) - 1] = '\0';
        
        if(strcmp(add_str, "quit") == 0) break;
```
- 문자열 '\n' 제거 및 널문자 삽입 및 무한 반복문 탈출 조건

```c
        if(strlen(res_str) > 0) strcat(res_str, " ");
```
- 1개라도 입력 받았을때 문자 띄어쓰기 구현

```c
        strcat(res_str, add_str);
        
        printf("입력된 문자열 : ");
        puts(res_str);
    }   
    return 0;
}
```
- strcat 함수로 문자열 붙이고 출력
<img width="364" height="153" alt="image" src="https://github.com/user-attachments/assets/6f48e91d-cb6e-40bb-b11d-ed463944bd3e" />


---

# 실습과제2
```c
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#include <string.h>
```
- 헤더파일 선언

```c
char MyStrlen(char []);
void RemoveBSN(char []);
```
- 길이 반환하는 함수, 널문자 삽입 함수 선언

```c
int main(void) {
    
    char str[100];
    printf("문자열 입력: ");
    fgets(str, sizeof(str), stdin);
```
- 배열 선언 후 문자열 입력 받기

```c
    printf("길이: %d, 내용: %s \n", MyStrlen(str), str);
```
- 제거 전 문자열 출력

```c
    RemoveBSN(str);
    printf("길이: %d, 내용: %s \n", MyStrlen(str), str);
    
    return 0;
}
```
- 함수 호출 및 출력 후 프로그램 종료

```c
char MyStrlen(char str[]){ return strlen(str); }
```
- 문자열 반환

```c
void RemoveBSN(char str[]){ str[strlen(str) - 1] = '\0'; }
```
- 널문자 삽입

---

# 실습과제3
```c
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#include <string.h>
```
- 헤더파일 선언

```c
void my_strcpy(char*, char*);
```
- 복사 할 함수 선언

```c
int main(void) {
    
    char str1[20] = "1234567890";
    char str2[20];
```
- 원본 함수와 복사 할 배열 선언

```c
    my_strcpy(str2, str1);
    puts(str2);
    return 0;
}
```
- 복사 함수 호출 및 출력 후 프로그램 종료

```c
void my_strcpy(char* dest, char* str){

```
    int i = 0;
- 배열 인덱스에 접근할 변수 선언 및 초기화

```c
    while(str[i] != '\0'){
        dest[i] = str[i];
        i++;
    }
    
    dest[i] = '\0';
}
```
- 배열 인덱스에 접근해서 복사 후 문자열 끝에 널문자 삽입

---

# 실습과제4 

```c
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#include <string.h>
```
- 헤더파일 선언

```c
void my_strcat(char*, char*);
```
- 이어 붙일 함수 선언

```c
int main(void) {
    
    char str1[20] = "First~";
    char str2[20] = "Second";
    my_strcat(str1, str2);
```
- 두 문자열 선언 후 함수 호출

```c
    puts(str1);
    return 0;
}
```
- 결과 출력 후 프로그램 종료

```c
void my_strcat(char* dest, char* str){
    
    int i = 0;
    int j = 0;
```
- 인덱스에 접근할 두 변수 선언

```c
    while(dest[i] != '\0'){ i++; }
    
    while(str[j] != '\0') {
        
        dest[i] = str[i];
        i++;
        j++;
    }
    
    dest[i] = '\0';
}
```
- 반복문을 통해 문자 하나씩 이어 붙인 후 마지막 널문자 삽입

---

# 실습과제5
