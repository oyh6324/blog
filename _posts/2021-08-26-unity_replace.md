---
title: "Unity. C# 특정 문자열 바꾸기"
categories:
  - Unity
tags:
  - 기초
  - Unity
  - C#
---

## Replace()

Replace()를 사용하면 원하는 문자열을 다른 문자열로 바꿀 수 있다.


## 사용법

```c#
string str1 = "Hello, My name is YoungHyun.";
string str2 = str1.Replace("YoungHyun", "DaYoung");
```

이렇게 하면 str1은 `Hello, My name is DaYoung.`이 될 것이다.