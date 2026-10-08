# 실습과제 1

1. 함수 선언, 호출, 정의를 각각 설명하라
  - 선언은 이름 반환형 매개변수 등을 미리 알려주는것, 함수를 실행하는것, 정의는 함수가 실제 기능할 내용을 작성하는것
2. 함수의 자료형은?
  - 함수를 실행 후 반환할 값의 자료형
3. 함수명의 자료형은?
  - 함수의 (시작)주소
4. void 포인터의 용도는?
  - 자료형의 상관없이 데이터의 주소를 저장하는 용도
5. void 포인터에 간접참조 연산을 적용할 때 주의할 점은?
  - 간접참조 연산자 * 을 사용할 수 없다는것, void 포인터가 어떤 자료형을 가르키는지 모르기 때문
6. 강제형변환과 자동형변환을 설명하시오
  - 강제형변환은 사용자가 직접 지정하여 자료형을 변경(ex. double a = 3.14 >>>> int b >>> b = (int)a)
    자동형변환은 컴파일러가 알아서 자료형을 변경(ex. int a = 10, double b >>>>> b = a >>>>> b = 10.0)

---

# 실습과제 2

## 함수의 매개변수에 함수 포인터를 활용하는 예제
```c
#include <stdio.h>
```
- 헤더파일 선언

```c
int add(int a, int b) 
{
    return a + b;
}
```
- 덧셈함수

```c
int sub(int a, int b)
{
    return a - b;
}
```
- 뺄셈함수

```c
int main()
{
    int (*fp)(int, int);
```
-함수 포인터 선언

```c
    fp = add;
```
- add 함수의 메모리 주소를 함수 포인터 fp에 저장

```c
    printf("결과 값 : %d\n", fp(10, 20));
```
-add 함수를 호출

```c
    fp = sub;
```
-sub 함수의 메모리 주소를 함수 포인터 fp에 저장

```c
    printf("결과 값 : %d\n", fp(10, 20));
```
-sub 함수 호출

    return 0;
}


---
# 실습과제 3

```c
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
```
- 헤더파일 선언

```c
int Add(int n1, int n2);
int Sub(int n1, int n2);
int Multiply(int n1, int n2);
int Division(int n1, int n2);
```
- 사칙연산을 수행할 함수 선언
  
```c
int ReturnResult(int n1, int n2, int (*fp)(int, int));
```
- 결과 값을 반환할 함수 포인터 선언

```c
int main(void){
    
    int n1, n2, choice, result;
    int (*fp)(int, int) = NULL;
```
- 계산할 변수, 결과값 변수, 함수 포인터 주소 저장할 변수 선언 및 초기화

```c
    printf("연산을 선택(1 : 덧셈, 2 : 뺄셈, 3 : 곱셈, 4 : 나눗셈) : ");
    scanf("%d", &choice);
    
    printf("두개의 정수 입력 : ");
    scanf("%d %d", &n1, &n2);
```
- 연산, 계산할 숫자 입력받기

```c
    switch(choice) {
            
        case 1: fp = Add; break;
        case 2: fp = Sub; break;
        case 3: fp = Multiply; break;
        case 4: fp = Division; break;
    }
```
- switch문으로 연산 선택

```c    
    result = ReturnResult(n1, n2, fp);
    printf("결과값 : %d\n", result);
    
    return 0;
}
```
- 결과값 변수에 포인터 함수 호출해서 대입, 결과 출력 후 코드 종료

```c
int ReturnResult(int n1, int n2, int (*fp)(int, int)) {
    return fp(n1, n2);
}
```
- 포인터 함수 정의

```c
int Add(int n1, int n2) {return n1 + n2;}
int Sub(int n1, int n2) {return n1 - n2;}
int Multiply(int n1, int n2) {return n1 * n2;}
int Division(int n1, int n2) {return n1 / n2;}
```
- 사칙연산 함수 정의
