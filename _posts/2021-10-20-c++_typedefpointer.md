---
title: "C++. typedef 포인터 별칭 알아보기"
categories:
  - C++
tags:
  - C++
  - 프로그래밍 언어
  - 포인터
  - 중급
---

## 🌟 typedef 구조체

전에 C언어를 공부할 때 typedef로 구조체를 간략하게 선언하는 걸 배워었다. C++을 하다 보니 typedef로 선언한 구조체 중 별칭이 특이한 게 보여서 메모함!



구조체는 별칭을 여러 개 둘 수 있는데 이때 포인터 별칭도 사용할 수 있다.

별칭을 포인터로 만들면 구조체를 포인터로 선언할 때 편하다. 한 번 써보겠음!

## 🌟 사용법

```c++
#include <iostream>
using namespace std;

typedef struct _tagStudent
{
    int number;
    int kor;
    int math;
    int eng;
} STUDENT, * PSTUDENT;

int main()
{
    STUDENT student;
    PSTUDENT pStudent = &student; //포인터 구조체
    pStudent->number = 10;
    pStudent->kor = 100;

    return 0;
}
```

PSTUDENT라는 포인터 별칭을 만들고, 바로 포인터 구조체를 만들어서 구조체를 참조했다. 별칭 편함!