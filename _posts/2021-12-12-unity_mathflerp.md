---
title: "Unity. Mathf.Lerp() 사용하기"
categories:
  - Unity
tags:
  - Unity
  - 기초
---



## 🌟 Mathf.Lerp()

선형 보간을 사용하여 부드럽게 움직이는 걸 구현할 때 Mathf.Lerp()를 쓴다.



선형 보간이란, a와 b가 있을 때 그 사이를 직선으로 연결하고 직선의 거리에 따라 그 사이값을 계산하는 방법이다.



`Mathf.Lerp(float a, float b, float t)` 이렇게 사용해서, t는 퍼센트고 t가 0에 가까울수록 a와 가까워지고, 1에 가까울수록 b에 가까워진다.



## 🌟 사용법

```c#
float speed = 5f;

float x = transform.position.x;
float targetX;

private void Update()
{
    x = Mathf.Lerp(x, targetX, Time.deltaTime * speed);
    transform.position = new Vector2(x, transform.position.y);
}
```



이렇게 하면 일정한 시간에 따라 원하는 속도로 target의 위치에 해당 오브젝트가 이동할 것이다.
