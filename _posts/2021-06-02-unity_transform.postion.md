---
title: "Unity. position과 localPostion"
categories:
  - Unity
tags:
  - Unity
  - 기초
---

## 🌟 position, localPostion

position은 현재 게임 오브젝트의 절대적인 위치값을 나타낸다. loalPosition은 부모가 있을 때, 부모의 위치로부터 상대적인 위치값을 나타낸다. 

## 🌟 사용법

```c#
void Start() {
	transform.position = new Vector3(0, 0, 0);
	transform.localPosition = new Vector3(0, 0, 0);
}
```

첫 번째 코드는 월드 상의 `(0, 0, 0)`로 오브젝트를 보내고, 두 번째 코드는 부모 객체 속에서 `(0, 0, 0)`로 이동한다. localPosition은 부모가 없으면 알아서 월드 상의 좌표로 보내주니 헷갈릴 때는 localPosition 쓰기!