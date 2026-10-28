# 실습과제1
1. 표준 입출력 스트림을 접근하는 방법을 설명하라.
    - FLIE 구조체를 사용
2. 공백을 포함한 문자열을 입력 받을 때 사용가능한 함수는?
    - fgets
3. gets 함수사용시 가장 큰 문제점은 무엇인가?
    - 배열에 크기를 초과한 데이터를 입력받으면 배열 크기를 초과한 메모리 공간에 덮어쓰게 된다
4. fgets 함수 사용시 문제점은 무엇인가?
    - 엔터(\n) 까지 입력을 받아 의도치 않은 결과를 낳을 수 있다
5. 널문자(‘\0’)와 널포인터(NULL)의 용도를 설명하시오.
    - 널문자는 문자의 끝을 구분하기 위함, 널포인터는 쓰레기값을 건드는것을 방지하기 위함

---

# 실습과제2

```c
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
```
- 헤더파일 선언

```c
int main(void){
        
    while(1) {
        
        int ch = '\0';
```
- 변수 ch 초기화

```c
        printf("문자 입력 : ");
        ch = getchar();
```
- getchar 함수로 문자 입력받기

```c    
        if(ch == 'q' || ch == 'Q') break;
```
- 반복문 종료를 위한 조건문 작성

```c
        printf("입력 받은 문자 : ");
        putchar(ch);
```
- putchar 함수로 입력받은 값 출력

```c
        int temp;
        while ((temp = getchar()) != '\n' && temp != EOF);
```
- 버퍼에 남아있는 \n 값 초기화

```c
        printf("\n");
    }
    
    return 0;
}
```
- 프로그램 종료

---

# 실습과제3

```c
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#include <string.h>
```
- 헤더파일 선언

```c
int main(void)
{
    char name[100];
    char address[200];
    char carNum[100];
```
- 이름, 주소, 차 번호 배열 변수 선언

```c
    printf("이름: ");
    fgets(name, sizeof(name), stdin);

    printf("주소: ");
    fgets(address, sizeof(address), stdin);

    printf("자동차번호: ");
    fgets(carNum, sizeof(carNum), stdin);
```
- fgets 함수롤 변수 입력받기

```c
    name[strcspn(name, "\n")] = '\0';
    address[strcspn(address, "\n")] = '\0';
    carNum[strcspn(carNum, "\n")] = '\0';
```
- 줄바꿈 제거

```c
    puts("<결과 출력>");
    printf("이름:");
    puts(name);

    printf("주소:");
    puts(address);

    printf("자동차번호:");
    puts(carNum);

    return 0;
}
```
- put 함수로 출력 후 프로그램 종료
<img width="227" height="137" alt="image" src="https://github.com/user-attachments/assets/1431a77c-9ce4-4622-9466-02b566ce6bb1" />
