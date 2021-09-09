---
title: "C언어. restrict 알아보기"
categories:
  - C
tags:
  - C언어
  - 프로그래밍 언어
  - 중급
---

## restrict란?

restrict는 포인터 한정자로 단 하나의 포인터 외에 이 메모리에 접근할 수 없다고 지정하는 것이다. 또한 이 한정자가 붙은 포인터는 더 많은 최적화를 받을 수 있다.

## 사용법

```c
int* _restrict rePtr = (int*)malloc(10*sizeof(int));

rePtr[0] += 3;
rePtr[0] += 5; //알아서 +=8로 바꿔줌
```

한정자를 붙이고 동적할당 한 뒤, restrict가 붙은 포인터는 최적화가 되어 성능이 오른다. 근데 쓸 일이 잘 없다고 한다....