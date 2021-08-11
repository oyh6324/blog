---
title: "C언어.  문자 입력하기 (2) getchar와 putchar"
categories:
  - C
tags:
  - C언어
  - 프로그래밍 언어
  - 문자 입출력 함수
---

## getchar와 putchar

getchar()은 문자 전용 입력 함수다. scanf()는 다른 형식의 데이터도 입력받을 수 있지만, getchar()은 문자만 가능! putchar도 문자를 콘솔에 출력하는 함수다.

## 사용법

```c
char ch;
ch = getchar() //ch에 입력받음
putchar(ch); //ch 출력
```

getchar에 입력 받아 ch에 저장하고 출력하는 코드다.