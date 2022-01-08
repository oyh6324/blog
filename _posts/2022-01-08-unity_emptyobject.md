---
title: "Unity. 스크립트로 빈 GameObject 만들기"
categories:
  - Unity
tags:
  - Unity
  - 기초
---



```c#
GameObject go = new GameObject("name");
```

이렇게 하면 만들어짐.



```c#
go = new GameObject { name = "name" };
```



이름이 눈에 잘 들어오는 형식!
