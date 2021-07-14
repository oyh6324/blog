---
title: "Unity. Physics.Raycast()"
categories:
  - Unity
tags:
  - 중급
  - Unity
---

## Physics.Raycast()

Raycast는 내가 원하는 좌표에서 원하는 방향으로 선, Ray를 그어서 그 안에 들어 있는 물체를 감지하는 함수다.

## 사용법

```c#
RaycastHit hit;

void Update()
{
	Debug.DrawRay(transform.position, transform.forward * 10f, Color.red);
	if (Physics.Raycast(transform.position, transform.forward, out hit, 10f))
		Debug.Log("충돌 감지");
}
```

`Debug.DrawRay()`는 Raycast의 Ray를 에디터 상으로 확인하기 위해 그은 것이고, 인자는 원점, Ray가 나아갈 방향, 색이 있다. 방향은 기본적으로 1f가 할당되서 뒤에 10f 같은 거리를 곱해야 원하는 거리를 설정할 수 있다.

`(Physics.Raycast()`의 인자는 원점, 방향, 충돌 감지된 오브젝트 정보가 들어 있는 RaycastHit, 거리. 이렇게 4가지가 있다. 충돌을 감지하면 true를 반환하고 그렇지 않으면 false를 반환한다. 