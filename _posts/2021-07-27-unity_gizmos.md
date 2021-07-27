---
title: "Unity. 기즈모(Gizmo) 사용하기"
categories:
  - Unity
tags:
  - 중급
  - Unity
---

## 기즈모란?

씬 화면에서 오브젝트와 관련되어 가시화된 그래픽을 볼 수 있다. 이것들이 모두 기즈모임.

## 사용법

```c#
void OnDrawGizoms() //씬에서 항상 보임
{
	Gizmos.color = Color.red;
	Gizmos.DrawCube(transform.position, Vector3.one); //정사각형 그리기
}

void OnDrawGizmosSelected() //오브젝트가 선택됐을 때 보임
{
	Gizmos.color = Color.red;
	Gizmos.DrawSphere(transform.position, 3f); //구 그리기
}
```

DrawCube의 인자는 **정사각형의 위치**와 **크기**이고, DrawSphere의 인자는 **구의 위치**와 **반지름 길이**이다.

DrawMesh라는 것도 있는데, 메쉬 모양의 기즈모로 인자는 **메쉬**와 **위치**이다. 

DrawIcon은 원하는 이미지를 기즈모로 만든 것인데, 인자는 **우치**와 **이미지 이름**이다. “img.jpg”이런 식으로 쓰면 된다.