---
title: "C++. 디폴트 매개 변수(Default Parameter) 알아보기"
categories:
  - C++
tags:
  - C++
  - 프로그래밍 언어
  - 기초
---

## 🌟 디폴트 매개 변수란?

함수의 매개 변수 중, 처음부터 값이 정해져 있는 매개 변수를 뜻한다. 그 함수를 호출할 때, 사용자가 매개 변수의 값을 바꾸지 않는다면 디폴트 매개 변수는 처음의 값으로 사용됨!



## 🌟 사용법

```c++
#include <iostream>
using namespace std;

int AddTen(int x, int y = 10)
{
    return x + y;
}

int main()
{
    cout << AddTen(5);
    
    return 0;
}
```

디폴트 인자는 반드시 오른쪽 맨 끝에 있어야 하고, 호출할 때는 값이 정해지지 않은 인자만 값을 넣어주면 된다. 이렇게 하면 15가 출력될 거임!



오른쪽 맨 끝이기만 하면 디폴트 인자는 여러 개가 와도 상관없다.