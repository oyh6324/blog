---
title: "C++. 멤버 함수 포인터 알아보기"
categories:
  - C++
tags:
  - C++
  - 프로그래밍 언어
  - 기초
  - 포인터
---

## 🌟 함수 포인터

전에 C 공부했을 때 알아듯이 함수를 가리키는 함수 포인터를 만들 수 있다. 그렇다면 클래스 안에 있는 멤버 함수는 어떻게 포인터로 만들까!



## 🌟 사용법

```c++
#include <iostream>
#include <string>
using namespace std;

class CStudent
{
public:
    void Output()
    {
        cout << "학생입니다.";
    };
};

int main()
{
    CStudent student; //객체 생성
    
    void(CStudent:: * pOutput)() = &CStudent::Output; //Output을 가리키는 포인터 생성
    (student.*pOutput)(); //포인터를 통해 멤버 함수 Output 호출
    
    return 0;
}
```



멤버 함수를 포인터로 사용할 때는

```c++
void(클래스명:: 포인터 이름)() = &클래스명::멤버 함수 이름;

(클래스 객체명.*포인터 이름)();
```

이렇게 하면 됨!
