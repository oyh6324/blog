---
title: "Unity. 월드 좌표계의 오브젝트 방향 구하기"
categories:
  - Unity
tags:
  - Unity
  - 기초
  - C#
---

 ## 🌟 TransformDirection()

TransformDirection()은 로컬 공간에서 월드 공간으로 방향을 변환하는 함수다. 이를 통해 캐릭터나 다른 오브젝트의 방향을 월드 좌표로 알아낼 수 있다.



## 🌟 사용법

```c#
Vector3 look = transform.TransformDirection(Vector3.forward);
```

이렇게 사용하면 정면 방향의 월드 좌표를 가져올 수 있다.

