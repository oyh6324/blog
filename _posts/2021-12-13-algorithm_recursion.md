---
title: "알고리즘. Recursion(순환)-팩토리얼"
categories:
  - Algorithm
tags:
  - 알고리즘
  - 순환
  - 기초
---



## 🌟 Recursion

순환은 자기 자신을 호출하는 걸 말한다. 재귀 함수라고도 함!



순환은 반복문에서 많이 사용되는데 자기 자신을 참조하면 그 함수가 끊임없이 돌게 되니 탈출구를 만들어둬야 한다.



그걸 Base Case라고 하며, 순환에 빠지지 않게 하는 경우다.



반대로 Recursion Case는 순환을 반복하는 경우다.



순환 함수에는 Base Case가 반드시 필요하다. 예시로 팩토리얼 함수를 만들어 보겠음!



## 🌟 팩토리얼

```c++
#include <iostream>
using namespace std;

int Factorial(int num){
    int num(<=1)
        return 1;
    
    return num * Factorial(num -1);
}

int main(){
    cout << Factorial(3);
    
    return 0;
}
```

3!은 3X2X1이므로 6이 출력될 것이다.
