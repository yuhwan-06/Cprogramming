# 실습과제1

| 수식 | 결과값 | 결과값의 자료형 |
| :---: | :---: | :---: |
| `&ch` | **100** | **char** |
| `&in` | **101** | **int** |
| `&db` | **105** | **double** |
| `*&ch` | **'A'** | **char** |
| `*&in` | **10** | **int** |
| `*&db` | **3.4** | **double** |

# 실습과제 2

---

## 코드

```c
#include <stdio.h>
```

헤더 파일을 선언

```c
int main(void)
```

메인 함수 선언

```c
{
```

```c
int a = -100;
```

• 정수형 변수 `a`를 선언 및 초기화

```c
char b = 'A';
```

• 문자형 변수 `b`를 선언 및 초기화

```c
double c = 3.14;
```

• 실수형 변수 `c`를 선언및 초기화

```c
int *pa = &a;
```

• 정수형 포인터 `pa`를 선언하고 변수 `a`의 주소를 저장

```c
char *pb = &b;
```

• 문자형 포인터 `pb`를 선언하고 변수 `b`의 주소를 저장

```c
double *pc = &c;
```

• 실수형 포인터 `pc`를 선언하고 변수 `c`의 주소를 저장

```c
printf("int형 변수 a의 값은 : %d\n", *pa);
```

• 포인터 `pa`가 가리키는 변수 `a`의 값을 역참조하여 출력

```c
printf("char형 변수 b의 값은 : %c\n", *pb);
```

• 포인터 `pb`가 가리키는 변수 `b`의 값을 역참조하여 출력

```c
printf("double형 변수 c의 값은 : %lf\n", *pc);
```

• 포인터 `pc`가 가리키는 변수 `c`의 값을 역참조하여 출력

```c
return 0;
```

• 프로그램이 정상적으로 종료되었음을 나타냄

```c
}
```

<img width="296" height="64" alt="image" src="https://github.com/user-attachments/assets/14498831-abb5-4760-9ba3-4938a39f81f0" />

# 실습과제 3

---

```c
#include <stdio.h>

int main(void)
{
    int* ptr = (int*)125; // 정수형 변수인 125를 강제 형변환을 통해서 주소값처럼 쓰게 했기 때문

    *ptr = 10;

    printf("%d\n", *ptr);

    return 0;
}

// 실행 중단 이유 : 임의로 만든 주소(*ptr)에 값을 저장하려 했기 때문
```

# 실습과제 4

---

```c
#include <stdio.h>
int main(void)
{
    int a = 100, b=200;
    int sum;
    
    int *pa = &a;
    int *pb = &b;
    int *psum = &sum;
    
    *psum = *pa + *pb;
    
    printf("두정수의 합 : %d\n", *psum);
    return 0;
}
```
<img width="143" height="19" alt="image" src="https://github.com/user-attachments/assets/cf3d45ec-fac3-4804-b6db-5ce96448a8e7" />

# 실습과제 5

## 문제 설명

int형 변수 `x`와 `y`를 선언하여 각각 `5`와 `15`로 초기화하고, int형 포인터 변수 `px`와 `py`를 선언하여 각각 `x`와 `y`를 가리키게 하시오.

1. 포인터 `px`와 `py`를 사용하여 `x`의 값은 3배로 증가시키고(`*px *= 3`), `y`의 값은 5만큼 감소시키시오.
2. 임시 포인터 변수 `temp`를 새로 선언하여 두 포인터 `px`와 `py`가 가리키는 대상(주소)을 서로 교환하시오.
3. 교환 후 `px`와 `py`가 가리키는 값을 출력하여 포인터가 서로 바뀐 대상을 올바르게 가리키는지 확인하시오.

## 정답 코드

```c
#include <stdio.h>

int main(void)
{
    // 1. 변수 및 포인터 초기화
    int x = 5, y = 15;  // int형 변수 x와 y를 선언하고 각각 5와 15로 초기화
    int *px = &x;  // 포인터 px를 선언하고 x의 주소를 저장
    int *py = &y;  // 포인터 py를 선언하고 y의 주소를 저장

    // 2. 포인터를 이용한 간접 참조 연산
    *px *= 3;  // x의 값을 3배로 변경 (5 → 15)
    *py -= 5;  // y의 값을 5 감소 (15 → 10)

    // 3. 포인터 변수가 가리키는 주소(대상) 교환
    int *temp = px;  // 임시 포인터 변수 temp에 px의 주소를 저장
    px = py;  // px가 py가 가리키던 주소를 가리키도록 변경
    py = temp;  // py가 temp가 저장한 원래 px의 주소를 가리키도록 변경

    // 4. 교환된 포인터가 가리키는 값 출력
    printf("px가 가리키는 값: %d\n", *px);  // y의 값인 10 출력
    printf("py가 가리키는 값: %d\n", *py);  // x의 값인 15 출력

    return 0;  // 프로그램 정상 종료
}
```
<img width="163" height="41" alt="image" src="https://github.com/user-attachments/assets/8962d8b4-0a62-4373-a049-91dae35deda7" />
