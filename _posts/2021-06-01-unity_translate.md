---
title: "Unity. Translate 사용법"
categories:
  - Unity
tags:
  - Unity
  - 기초
---

## Transform.Translate

`Transform.Translate`는 게임 오브젝트를 벡터값만큼 평행 이동 할 수 있는 함수다. 현재 오브젝트의 위치에서 해당 방향으로 이동한다고 생각하면 될 듯!

## 사용법

```c#
void Update() {
	transform.Translate ( Vector3.forward * Time.deltaTime ); //앞으로 이동
	transform.Translate ( Vector3.up * Time.deltaTime , Space.World ); //절대 좌표를 통해 위로 이동
}
```

기본값은 게임 오브젝트 기준으로 움직인다. `Space.World`를 사용하면 절대 좌표를 기준으로 이동한다.