---
title: "알고리즘. 문자열 뒤집기"
categories:
  - Algorithm
tags:
  - 알고리즘
  - 기초
---



## 🌟 문자열 뒤집기

말 그대로 문자열이 `String`이라면 `gnirtS`로 뒤집는 걸 말한다.

문자열의 개수만큼 반복문을 돌려도 좋지만 더 빠르게 돌릴 수 있는 방법이 있음!



## 🌟 코드

```c++
#include <iostream>

using namespace std;

int main()
{
    char arr[] = "String";
    char result[sizeof(arr)/sizeof(*arr)]="";

    memcpy(result, arr, sizeof(arr));
    for (int i = 0; i < sizeof(result) / 2; i++) { 
        // swap
        int temp = result[i];
        result[i] = result[sizeof(result) - 1 - i]; 
        result[sizeof(result) - 1 - i] = temp;
    }

    // 출력
    for (int i = 0; i < sizeof(result); i++) {
        cout << result[i] << " ";
    }
}
```

배열을 반 잘라서 바꿔줌! 배열을 길이만큼 도는 것보다 훨씬 빨리 돈다.



> [Take Action](https://marobiana.tistory.com/159)

