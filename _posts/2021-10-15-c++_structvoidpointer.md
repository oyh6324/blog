---
title: "C++. 구조체와 void 포인터 알아보기"
categories:
  - C++
tags:
  - C++
  - 프로그래밍 언어
  - 포인터
  - 중급
---



> 포인터 복습하고 가기!



C언어 배울 때 포인터도 같이 배웠지만 복습 차원 간단하게 다시 알아보겠음!

_포인터란?_

- 메모리 주소를 가리키는 변수

- 86비트 컴퓨터에서는 4바이트, 64비트 컴퓨터에서는 8바이트 단위로 구성되어 있음

- 포인터를 통해 데이터 값을 넣는 걸 역참조라고 함

  ```c++
  int* pNum;
  int iNum = 10;
  pNum = &iNum; //pNum은 iNum의 주소값을 가짐
  *pNum = 1234; //pNum을 통해 역참조 //iNum은 1234가 됨
  ```

- 배열은 그 자체가 메모리 주소다!



대충 이 정도 하면 끝!



## 🌟 구조체 포인터

구조체 포인터란 위에서 사용한 것과 마찬 가지로, 내가 만든 객체의 메모리 주소를 포인터로 받는 것이다. 



```c++
#include <iostream>

using namespace std;

struct _tagStudent //구조체
{
    int iNumber;
    int iKor;
    int iEng;
};

int main()
{
    struct _tagStudent tStudent = { 123, 60, 70 };
    _tagStudent* pStudent = &tStudent; //구조체 포인터로 메모리 주소 받음

    (*pStudent).iNumber = 456;
    pStudent->iNumber = 456;

    return 0;
}
```

구조체 포인터로 역참조를 하려면 간단하게 `*pStudent.iNumber = 456`해도 될 거라 생각하지만, *의 연산자 우선 순위가 .보다 낮아서 *을 먼저 인식하게 해줘야 한다.

그래서 `(*pStudent).iNumber = 456`가 되는 것! 그런데 이렇게 하면 불편하니까 포인터 전용으로 ` ->`이런 기호를 사용하여 역참조를 할 수 있게 했다.





## 🌟 void 포인터

void 포인터는 어떤 타입이든 저장이 가능한 포인터다. 하지만 역참조는 할 수 없고, 메모리 주소만 저장이 가능하다.



```c++
#include <iostream>

using namespace std;

int main()
{
    int i;
    char c;
    
    void* ptr1 = &i;
    void* ptr2 = &c;
    
    return 0;
}
```

간단!



void 포인터를 다시 사용하려면 참조하고 있는 값이 무슨 타입인지 모르므로 형변환을 해야 한다.

```c++
cout << (int*)ptr1;
```

이렇게!