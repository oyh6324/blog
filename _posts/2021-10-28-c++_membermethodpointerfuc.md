---
title: "C++. 멤버 함수 포인터 알아보기 (2)"
categories:
  - C++
tags:
  - C++
  - 프로그래밍 언어
  - 기초
  - 포인터
---

## 🌟 멤버 함수 포인터의 불편함

저번에 봤던 코드를 보면 멤버 함수 포인터를 사용하려면 `(student.*pOutput)();`이렇게 감싸서 사용해야 하는 불편함이 있었다. 멤버 함수 포인터를 사용할 때 이러한 불편함을 제거하는 새 방법이 있음!



## 🌟 사용법

```c++
#include <iostream>
#include <functional> //새 라이브러리 추가
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
    function <void()> func;
    
    CStudent student;
    func = bind(&CStudent::Output, &student); //주소 저장

    func();

    return 0;
}
```

function은 C++11부터 지원하는 함수 포인터로, 전역, 멤버 가리지 않고 함수의 주소를 쉽게 저장해준다.



 `func = bind(&CStudent::Output, &student);`  이 부분에서 보면 알 수 있듯 저장할 함수와 객체를 쓰면 됨!
