---
title: "C++. 템플릿(template) 알아보기"
categories:
  - C++
tags:
  - C++
  - 프로그래밍 언어
  - 중급
---



## 🌟 템플릿(Template)이란?

템플릿은 컴파일 단계에서 어떤 메소드의 타입을 결정짓는 기능이다. 함수 템플릿과 클래스 템플릿으로 나누어지며, 간단하게 말하자면 같은 기능을 하는 메소드가 있을 때 매개 변수나 리턴 타입의 영향을 받지 않는다고 생각하면 됨!



## 🌟 사용법

```c++
#include <iostream>
using namespace std;


int ISum(int a, int b)
{
    return a + b;
}

float FSum(float a, float b)
{
    return a + b;
}
```

함수의 자료형이 다르므로 같은 기능을 하고 있음에도 두 개를 써야하는 번거로움이 있을 때 템플릿을 쓰면 됨.



```c++
#include <iostream>
using namespace std;

//템플릿
template <typename T>
T Sum(T a, T b)
{
    return a + b;
}

int main()
{
    cout << Sum<int>(10, 20); //30 출력
    cout << Sum<float>(10.5, 20.5); //31 출력
}
```

이렇게 사용하면 간단!



클래스도 이와 비슷하게 사용하면 된다.

```c++
template <typename T>
class CTemplate
{
    ...
}
```

이런 느낌.
