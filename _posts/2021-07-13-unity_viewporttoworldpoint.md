---
title: "Unity. Camera.ViewportToWorldPoint()"
categories:
  - Unity
tags:
  - 중급
  - Unity
---

## Camera.ViewportToWorldPoint()

카메라로 보는 화면을 3D 공간의 XYZ 위치로 변환시킨다. 

## 사용법

```c#
Camera camera = GetComponent<Camera>();
Vector3 position = camera.ViewportToWorldPoint(new Vector3(0.5f, 0.5f, 0f));
```

여기서 `(0.5f, 0.5f, 0f)`은 카메라의 정중앙을 뜻한다. 카메라가 보는 정중앙의 좌표를 받아냈다고 보면 됨! 카메라 좌표 함수는 이외에도 많지만 다음에 알아보는 걸로...!