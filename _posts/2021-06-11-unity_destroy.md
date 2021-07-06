---
title: "Unity. Destroy 사용법"
categories:
  - Unity
tags:
  - Unity
  - 기초
---

## Destroy()

`Destroy()`는 원하는 게임 오브젝트를 파괴하는 함수다.

##  사용법

```c#
void Start()
{
	Destroy(gameObject);
}
```

이 스크립트를 갖고 있는 오브젝트가 게임이 시작할 때 파괴된다는 의미!

```c#
void Start()
{
	Destroy(gameObject, 3f);
}
```

뒤에 시간을 붙이면 n초 뒤에 파괴한다는 뜻!