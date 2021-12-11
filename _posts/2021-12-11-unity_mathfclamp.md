---
title: "Unity. Mathf.Clamp() 사용하기"
categories:
  - Unity
tags:
  - Unity
  - 기초
---



## 🌟 Mathf.Clamp()

최소값과 최대값을 정해서 그 안에 들어 있는 값외에 다른 값이 되지 않게 한다.



## 🌟 사용법

```c#
float min = 10f;
float max = 20f;
float pointX = Mathf.Clamp(Input.mousePosition.x, min, max);
```



Mathf.Clamp()는 value, min, max 순서로 인자를 넣어야 하며, value 값이 min과 max 사이에 있으면 value 값을, 사이에 없다면 min 또는 max를 반환한다.



위 코드는 마우스의 x 좌표에 따라 min과 max 사이의 값을 반환한다.
