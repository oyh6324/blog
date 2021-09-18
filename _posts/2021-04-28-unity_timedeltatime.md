---
title: "Unity. Time.deltaTime 사용법"
categories:
  - Unity
tags:
  - Unity
  - 기초
---

## 🌟 Time.deltaTime이란

지난 프레임이 완료되는 데 까지 걸린 시간을 나타내며, 단위는 초를 사용한다. 예를 들어 초당 40프레임이 돈다면 `Time.deltaTime`은 1/40이라고 할 수 있다. 60프레임이 돈다면 1/60!

## 🌟 사용법

```c#
void Update() {
	float translation = Time.deltaTime * 10; 
	transform.Translate(0, 0, translation);
}
```

Update는 한 프레임 당 한번 도니까 `Time.deltaTime`에 10을 곱하면 1초에 10이라는 게 됨. 그러면 해당 오브젝트는 1초에 10만큼 이동하는 것! 

## 🌟 쓰는 이유

사람마다 컴퓨터 프레임이 다르니까 최적화를 위해 `Time.deltaTime`을 사용한다. 초당 이동속도가 같다면 게임에서 다른 사람과 차이가 나지 않을테니까!