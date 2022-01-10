---
title: "Unity. C# 문자열 null 또는 Empty 확인하기"
categories:
  - Unity
tags:
  - Unity
  - 기초
  - C#
---

## 🌟 string.IsNullOrEmpty()

`string.IsNullOrEmpty()`를 사용하면 안에 들어 있는 문자열이 Null 또는 string.Empty임을 확인할 수 있다.



Null은 말 그대로 null을 말하고, string.Empty는 "" 이걸 말한다.



## 🌟 사용법

```c#
string str = "";
if(string.IsNullOrEmpty(str))
{
    Debug.Log("Null 또는 Empty");
}
```



bool을 반환함!
