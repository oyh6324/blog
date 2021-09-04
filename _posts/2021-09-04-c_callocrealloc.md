---
title: "C언어. calloc()과 realloc() 알아보기"
categories:
  - C
tags:
  - C언어
  - 프로그래밍 언어
  - 중급
  - 포인터
  - 동적 할당
---

## calloc()

calloc()은 malloc()과 매우 비슷하지만, 초기화 값을 쓰레기 값 대신 0으로 해준다는 차이점이 있다. 그리고 매개변수도 두 개를 필요한다.

## realloc()

realloc()은 malloc()이나 calloc()으로 메모리 할당 후, 자리를 더 늘리고 싶을 때 사용한다.

## 사용법

```c
int *ptr = NULL;
ptr = (int *)calloc(10, sizeof(int)); //동적 할당
ptr = (int *)realloc(ptr, 15*sizeof(int)); //10->15로 재할당

free(ptr);
```