---
title: "C언어. 재귀함수로 팩토리얼 구현하기"
categories:
  - C
tags:
  - C
  - 재귀함수
  - 프로그래밍 언어
---

## 재귀함수란?

함수를 정의할 때 자기 자신을 호출하면 그 함수를 재귀함수라고 한다. 피보나치나 최소공배수 등 다양한 예제가 있지만 오늘 인강으로 들은 팩토리얼을 기록하겠음!

## 재귀함수를 사용한 팩토리얼

```c
#include <stdio.h>
#include <string.h>

long loop_factorial(int n); //반복문 사용
long recursive_factorial(int n); //재귀함수 사용

int main() {
	int num = 3;
	
	printf("%d\n", loop_factorial(num));
	printf("%d\n", recursive_factorial(num));

	return 0;
}

long loop_factorial(int n) {
	long num = 1;
	for (int i = 1; i <= n; i++) {
		num *= i;
	}

	return num;
}

long recursive_factorial(int n) {
	if (n == 1)
		return 1;
	else
		return n*recursive_factorial(n - 1);
}
```

이렇게 하면 출력되는 건 6일 것이다. 재귀함수 return 쓰는 게 너무 헷갈린다. 다음엔 피보나치랑 다른 것도 써야지...
