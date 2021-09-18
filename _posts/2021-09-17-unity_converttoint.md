---
title: "Unity. 문자열과 정수 변환하기"
categories:
  - Unity
tags:
  - 기초
  - Unity
  - C#
---

## 🌟 정수에서 문자열

```c#
void Start()
{
        int a = 1000;
        string str = a.ToString();
}
```

`ToString()`을 쓰면 문자열로 바뀜!

## 🌟 문자열에서 정수

```c#
        int a = 1000;
        string str = a.ToString();

        int b = Convert.ToInt32(str);
```

`Convert.ToInt32()`를 쓰면 문자열에서 정수로 바꿀 수 있음!