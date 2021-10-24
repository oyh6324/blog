---
title: "C++. Class의 생정자 오버로딩 알아보기"
categories:
  - C++
tags:
  - C++
  - 프로그래밍 언어
  - 기초
---

## 🌟 오버로딩이란?

오버로딩이란 같은 함수 이름을 가지고 있지만 매개 변수나 반환하는 자료형이 달라서 좀 더 다양하게 메소드를 만드는 것을 말한다. 클래스의 생성자도 오버로딩할 수 있다.



## 🌟 사용법

```c++
#include <iostream>
#include <string>
using namespace std;

class CStudent
{
private:
    string name;
    int number;
    
public:
    CStudent(string name, int number){ //생성자
        this->name = name;
        this->number = number;
    }
    
    CStudent(string name){ //생성자
        this->name = name;
        this->number = 1000;
    }
};

int main()
{
    CStudent student = CStudent("영현", 1010);
    CStudent student = CStudent("민지");
    return 0;
}
```

인자가 하나인 생성자는 이름을 원하는 대로 초기화할 수 있고, 인자가 두 개인 생성자는 이름과 번호 모두 원하는 대로 초기화할 수 있다. 같은 메소드이나 인자가 다르므로 생성자를 오버로딩한 것!



> ☝ 잠깐!

오버로딩은 모호하게 하지 않도록 주의해야 한다. 예를 들어,

```c++
class CStudent
{
private:
    string name;
    int number;
    
public:
    CStudent(string name, int number){
        this->name = name;
        this->number = number;
    }
    
    CStudent(string name){ 
        this->name = name;
        this->number = 1000;
    }
    
    CStudent(string name, int number=1000)
    {
        this->name = name;
        this->number = number;
    }
};
```

이렇게 디폴트 매개 변수가 있는 경우, 두 번째 생성자와 모호한 경우가 생길 수 있어 주의해야 한다. 