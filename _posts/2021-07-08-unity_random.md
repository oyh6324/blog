---
title: "Unity. Random.Range()"
categories:
  - Unity
tags:
  - Unity
  - 기초
---

## Random.Range()

랜덤한 float 수를 반환한다. 이때 안에 정수를 넣으면 정수를, 실수를 넣으면 실수로 값을 반환함!

## 사용법

```c#
void Start()
{
	int random = Random.Range(0, 4); //0, 1, 2, 3 중 하나 반환
}
```

앞의 인자는 min이고 뒤의 인자는 max다. max-1까지 범위로 둔다.