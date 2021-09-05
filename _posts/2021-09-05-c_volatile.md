---
title: "C언어. volatile 알아보기"
categories:
  - C
tags:
  - C언어
  - 프로그래밍 언어
  - 중급
---

## volatile란?

자료형 한정자 중 하나로, 변수 앞에 붙이면 컴파일러가 최적화를 막지 못하게 막는다. 컴파일러가 알 수 없는 일에 값이 바뀔 수 있다고 생각하여 항상 메모리에 올리는 것!

## 사용법

```c
static int foo;

void bar(void)
{
    foo = 0;

    while (foo != 255);
}
```

위키백과에서 예시를 들고 왔다. 위 코드 대로 사용하면 컴파일러는 최적화를 하여

```c
void bar_optimized(void)
{
    foo = 0;

    while (true);
}
```

이런 코드로 바꿔버린다. 그러면 영원히 반복문을 빠져 나오지 못한다. 이때 volatile를 쓰면

```c
static volatile int foo;

void bar (void)
{
    foo = 0;

    while (foo != 255);
}
```

최적화를 시키지 않는다. 왜냐면 foo가 항상 메모리에 올라가 있고 값이 바뀔지도 모르니까!