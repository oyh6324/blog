---
title: "C언어. 재귀함수로 피보나치 구현하기"
categories:
  - C
tags:
  - C언어
  - 재귀함수
  - 프로그래밍 언어
---

## 피보나치란?

피보나치 수는 앞의 두 항을 더한 수로, `0, 1, 1, 2, 3, 5, 8……` 이런 식으로 전개된다. 이때 0은 1항이 아닌 0항으로 생각해야 한다!

## 재귀함수를 사용한 피보나치

```c
#include <stdio.h>
#include <string.h>

int fibonacci(int number);

int main() {

	printf("%d",fibonacci(5));
	return 0;
}

int fibonacci(int number) {
	if (number > 2) //3항까지만 재귀함수로 계산
		return fibonacci(number - 1) + fibonacci(number - 2);
	else //2항 이하는 1을 리턴
		return 1;
}
```

이렇게 하면 피보나치 수 중 5항인 5를 출력할 것이다.

피보나치는 가장 대표적인 재귀함수 예제다. 그런데 맨날 까먹네! 하~~