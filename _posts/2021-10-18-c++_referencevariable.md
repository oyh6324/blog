---
title: "C++. 레퍼런스 변수 알아보기"
categories:
  - C++
tags:
  - C++
  - 프로그래밍 언어
  - 기초
---

## 🌟 레퍼런스 변수란?

레퍼런스는 다른 대상을 참조하게 해주는 기능을 뜻하고, 레퍼런스 변수는 이러한 기능을 가지고 있는 변수를 말한다. 포인터와 유사한 느낌!



레퍼런스 변수를 사용하려면 변수 이름 앞에 '&'을 붙이면 된다.

```c++
int& ref;
```

이렇게!



## 🌟 사용법

```c++
#include <iostream>

using namespace std;

int main()
{
    int iNum = 100;
    int& iRefNum = iNum; //iNum을 참조함
    
    cout << iRefNum; //iNum을 출력함. 100이 나옴
    
    iRefNum = 1234;
    
    cout << iNum; //1234가 출력됨
    
    return 0;
}
```

사용법은 매우 간단하다. 참조 변수를 만들고, 참조하고 싶은 변수를 넣으면 된다. iRefNum은 이제 iNum과 동일한 주소값을 가지고 있어서, iRefNum의 값을 바꾸면 iNum도 값이 바뀌게 된다.



포인터와 유사하지만 다른 점은 포인터와 다르게 참조하는 대상을 변경하지 못한다.