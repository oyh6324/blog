---
title: "Unity. MoveTowards 사용법"
categories:
  - Unity
tags:
  - Unity
  - 기초
---

## MoveTowards

게임 오브젝트를 현재 위치에서 원하는 위치로 이동시킬 수 있는 함수다. 보통 Update()에 넣어야 하고, 원하는 속도만큼 갈 수 있다.

## 사용법

```c#
void Update() {
	transform.position = Vector3.MoveTowards(transform.position, target.position, 10f);
}
```

해당 오브젝트를 현재 위치, `transform.position`에서 원하는 위치, `target.position`으로 10f의 속도만큼 이동시킨다. Update()에 안 넣으면 이동이 안되니 주의!	