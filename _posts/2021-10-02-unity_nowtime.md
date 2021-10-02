---
title: "Unity. 현재 시간 구하기"
categories:
  - Unity
tags:
  - 기초
  - Unity
  - C#
---

## 🌟 DateTime

C#의 `DateTime`을 사용하면 간편하게 현재 날짜와 시간을 구할 수 있다!



### 기본 형태

```c#
DateTime.Now.ToString();
```

이렇게 생겼으며, 안의 포맷을 바꿔 원하는 모양으로 만들 수 있다!



### 형식 문자열 종류

- **yyyy**: 년도 전체
- **yy**: 년도, 마지막 두 자리
- **y**: 년도, 마지막 한 자리
- **M**: 월, 한 자리 또는 두 자리
  - ex) 1, 2, 3, 11 등
- **MM**: 월, 두 자리
  - ex) 01, 02, 12 등
- **MMM**: 월, 글자까지 붙여서 
  - ex) 10월, 11월 등
- **MMMM**: 월, 글자까지 붙여서 
  - ex) 10월, 11월 등
- **d**: 일, 한 자리 또는 두 자리 
  - ex) 1, 2, 28, 29 등
- **dd**: 일, 두 자리
  - ex) 01, 02, 31 등
- **ddd**: 요일 약어
  - ex) 토, 일, 월 등
- **dddd**: 요일 전체 이름
  - ex) 토요일, 월요일 등
- **HH**: 시 (24시간 기준)
- **hh**: 시 (12시간 기준)
- **mm**: 분, 두 자리
  - ex) 02, 13, 58 등
- **m**: 분, 한 자리
  - ex) 1, 5, 38 등
- **ss**: 초, 두 자리
- **s**: 초, 한 자리
- **tt**: 오전, 오후
  - ex) AM, PM
- **t**: 오전, 오후 한 자리
  - ex) A, P



## 🌟 사용법

```c#
using System;

void Start()
{
    string nowDate = System.DateTime.Now.ToString("yyyyMMdd");
    string nowTime = System.DateTime.Now.ToString("HHmmss"); 
}
```

이렇게 사용하면 오늘 nowDate는 오늘 날짜인 `20211002`을 출력할 것이고, nowTime은 `143902` 즉, 2시 39분 2초를 출력할 것이다!