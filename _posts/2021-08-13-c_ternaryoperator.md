---
title: "C언어. 삼항연산자 알아보기"
categories:
  - C
tags:
  - C언어
  - 프로그래밍 언어
  - 기초
---

## 🌟 삼항연산자란?

종종 볼 수 있는 물음표를 사용한 조건 연산자를 삼항연산자라고 한다. `조건 ? 참일 때의 값 : 거짓일 때의 값` 이런 식으로 사용할 수 있다.

## 🌟 사용법

```c
int num = 10;
int maxNum = 0;

maxNum = (num > maxNum) ? num : maxNum;
```

num이 maxNum보다 크다면 maxNum은 값은 num이 될 것이다. 삼항연산자는 중첩해서 사용할 수도 있다.