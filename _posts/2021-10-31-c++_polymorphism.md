---
title: "C++. 업캐스팅과 다운캐스팅 알아보기"
categories:
  - C++
tags:
  - C++
  - 프로그래밍 언어
  - 기초
---



## 🌟 다형성이란?

상속 관계에 있는 두 클래스 간에 형변환이 가능한 것을 말한다. 이때 자식에서 부모로 형변환 하는 걸 **업캐스팅**, 부모에서 자식으로 형변환 하는 걸 **다운캐스팅**이라고 한다.



## 🌟 사용법

```c++
#include <iostream>

using namespace std;

class CParent
{
public:
    void Output()
    {
        cout << "부모입니다.";
    }
};

class CChild : public CParent
{
public:
    void Output()
    {
        cout << "자식입니다.";
    }
};

int main()
{
    CChild child;
    CChild* pChild = &child;

    CParent* pParent = pChild; //업캐스팅
    
    pParent->Output();
    
    pChild = (CChild*)pParent; //다운캐스팅

    pChild->Output();
}
```

업캐스팅한 후 출력한 걸 보면 부모라고 출력한 걸 알 수 있고, 다운캐스팅한 후 출력하면 자식이라고 출력한 걸 알 수 있다.
