---
title: "Unity. 레이어 마스크(LayerMask) 알아보기"
categories:
  - Unity
tags:
  - Unity
  - 기초
---

## 🌟 레이어 마스크란?

오브젝트마다 있는 레이어를 사용해서 특정한 레이어만 활용할 때 사용한다. 레이어 마스크 변수를 통해 어떤 레이어인지 구분함!



## 🌟 사용법

```c#
int mask = 1<<8; //Layer 8
RaycastHit hit;
if (Physics.Raycast(ray, out hit, 100.0f, mask))
{
    Debug.Log(hit.collider.gameObject.name);
}
```

`1<<8`은  `0000000000000000000000001000000`을 의미하며, 8번째 레이어를 뜻한다. 따라서 위 코드대로 사용하면 8번째 레이어에 해당하는 오브젝트만 반환될 것이다!



쉬프트 연산자를 통해 가져오지 않고 레이어 이름으로도 가져올 수 있다.

```c#
LayerMask layerMask = LayerMask.GetMask("Wall");
```

이렇게! 
