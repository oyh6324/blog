---
title: "C++. Operator 알아보기"
categories:
  - C++
tags:
  - C++
  - 프로그래밍 언어
  - 기초
---

## 🌟 Operator Overloading

구조체를 사용하다 보면 다른 변수와 다르게 구조체끼리 더하고 빼는, 등등의 연산 활동이 안되는 걸 느낄 것이다. 그때 구조체에서 연산자를 구조체를 위한 연산자로 오버로딩 할 수 있다.

## 🌟 사용법

```c++
#include <iostream>

using namespace std;

class CStudent
{
private:
    int number;
public:
    CStudent(int number)
    {
        this->number = number;
    }

    CStudent operator +(CStudent& ref) //+연산자 재정의
    {
        return CStudent(number + ref.number);
    }
};

int main()
{
    CStudent student1(10);
    CStudent student2(20);

    CStudent Sum = student1 + student2; //number가 30으로 초기화 된 구조체 생성됨

    return 0;
}
```

연산자 오버로딩은 -도 할 수 있고 *도 할 수 있다. 리턴하는 값을 올바르게 쓴다면 뭐든 구조체에 맞게 수정할 수 있음!
