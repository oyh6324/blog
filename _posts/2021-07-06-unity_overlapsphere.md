---
title: "Unity. Physics.OverLapShphere()"
categories:
  - Unity
tags:
  - Unity
  - 중급
---

## 🌟 Physics.OverLapShphere()

위 함수는 원하는 오브젝트를 중심으로 구를 만들어서 그 안에 있는 오브젝트를 배열로 저장할 수 있다. 게임에서 적이 플레이어를 인식할 때 사용하기 좋을 듯!

## 🌟 사용법

```c#

float radius = 5f;

void Start()
{
	Collider[] hitColliders = Physics.OverlapSphere(transform.position, radius);
}
```

hitColliders에 radius의 길이만큼 안에 들어 있는 모든 충돌체가 Collider 배열로 들어간다. 이때 자기 자신도 포함됨! 여기서 `LayerMask`를 써서 충돌체를 걸러낼 수 있는데 다음과 같이 쓰면 된다.

```c#
int layer = 10;
int layerMask = 1 << layer
Collider[] hitColliders = Physics.OverlapSphere(transform.position, radius, layerMask);
```

이렇게 사용하면 10번 레이어로 지정된 오브젝트만 배열에 넣을 수 있다. `1 << layer`는 비트 연산자인데, 비트 연산자는 다음에 쓰는 걸로!