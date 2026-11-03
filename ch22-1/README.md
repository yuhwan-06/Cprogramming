# 실습과제 1

1. 구조체가 필요한 이유를 설명하라
   - 많은 데이터들을 개별적으로 선언하기 어려움이 있어서

2. 배열과 공통점과 차이점을 설명하라
   - 공통점 : 초기화 방식, 메모리 할당 방식이 같다
   - 차이점 : 배열의 원소들은 자료형이 같아야 하지만 구조체에서는 자료형이 달라도 된다

3. 기본자료형과 구조체의 차이를 설명하라
   - 구조체에서는 자료형의 구성을 직접 정의가 가능하지만, 기본자료형은 c언어에서 이미 정의되어있음

4. 구조체 정의와 구조체 변수 선언의 의미를 각각 설명하라
   - 정의 : 새로운 자료형을 정의
   - 변수 선언의 의미 : 메모리에 변수를 할당하는 것

---
  
# 실습과제 2

```c
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#include <string.h>

struct student {

    char name[20];
    int student_num;
    char addres[20];

};

int main(void) {

    struct student man;

    printf("학번을 입력하세요 : "); scanf("%d", &(man.student_num));
    getchar();

    printf("이름을 입력하세요 : "); fgets(man.name, 20, stdin);
    man.name[strlen(man.name) - 1] = '\0';

    printf("주소를 입력하세요 : "); fgets(man.addres, 20, stdin);

    printf("학번 : %d\n", man.student_num);
    printf("이름 : %s\n", man.name);
    printf("주소 : %s\n", man.addres);

    return 0;
}
```

---

# 실습과제 3

```c
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#include <string.h>

struct car {

    char model[20];
    char car_num[20];
    int dirve_dist;
};

int main(void) {

    struct car my_car;

    printf("모델 입력 : "); fgets(my_car.model, 20, stdin);
    my_car.model[strlen(my_car.model) - 1] = '\0';
    
    printf("번호판 입력 : "); fgets(my_car.car_num, 20, stdin);
    my_car.car_num[strlen(my_car.car_num) - 1] = '\0';
    
    printf("주행 거리 입력 : "); scanf("%d", &(my_car.dirve_dist));

    printf("모델 : %s\n", my_car.model);
    printf("번호판 : %s\n", my_car.car_num);
    printf("주행 거리 : %d", my_car.dirve_dist);

    return 0;
}
```

---

# 실습과제 4

```c
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#include <string.h>

struct point {

    int left_top[2];
    int right_bot[2];
};

int main(void) {
    
    struct point s;

    printf("좌측 상단 좌표 입력 : ");
    scanf("%d %d", &s.left_top[0], &s.left_top[1]);
    
    printf("우측 상단 좌표 입력 : ");
    scanf("%d %d", &s.right_bot[0], &s.right_bot[1]);
    
    printf("사각형 폭 : %d\n", s.right_bot[0] - s.left_top[0]);
    printf("사각형 높이 : %d\n", s.left_top[1] - s.right_bot[1]);
    
    return 0;
}
```

---

실습과제 5

```c
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#include <string.h>

struct point {

    int x;
    int y;
};

int main(void) {
    
    struct point p1={10,10}, p2= {20,20};
    printf("교환전 P1의 좌표: (%d, %d)\n", p1.x, p1.y);
    printf("교환전 P2의 좌표: (%d, %d)\n", p2.x, p2.y);
    
    int temp1 = p1.x;
    int temp2 = p1.y;
    
    p1.x = p2.x;
    p1.y = p2.y;
    
    p2.x = temp1;
    p2.y = temp2;
    
    printf("교환후 P1의 좌표: (%d, %d)\n", p1.x, p1.y);
    printf("교환후 P2의 좌표: (%d, %d)\n", p2.x, p2.y);
    return 0;
}
```
