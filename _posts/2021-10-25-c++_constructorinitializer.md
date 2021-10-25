---
title: "C++. 생성자 초기화 리스트(Initializer list) 알아보기"
categories:
  - C++
tags:
  - C++
  - 프로그래밍 언어
  - 기초
---

## 🌟 초기화 리스트란? 

생성자에서 그 클래스의 멤버 변수를 초기화하면 생성자가 호출되고 초기화가 되는데 생성자가 선언됨과 동시에 초기화할 수 있는 방법이 있다. 그게 바로 초기화 리스트!



## 🌟 사용법

```c++
#include <iostream>
#include <string>
using namespace std;

class CStudent
{
private:
    string m_name;
    int m_number;
    
public:
    CStudent(string name, int number): 
    m_name(name), m_number(number) //멤버 변수 초기화
    {
        
    }
};

int main()
{
    CStudent student = CStudent("영현", 1010);
    return 0;
}
```

이렇게 사용하면 선언과 동시에 초기화를 할 수 있다.



```c++
클래스명(매개 변수): 멤버 변수(매개 변수)...
```

이런 식!



같은 역할을 하는 원래 생성자는 이렇게 생겼다.

```c++
    CStudent(string name, int number){ //생성자
        this->name = name;
        this->number = number;
    }
```

