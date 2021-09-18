---
title: "Unity. 라인 렌더러(Line Renderer) 알아보기"
categories:
  - Unity
tags:
  - 중급
  - Unity
---

## 🌟 Line Renderer란?

라인 렌더러 컴포넌트는 3D 공간에서 두 개 이상의 점으로 그것을 연결하는 직선을 그린다. 단순한 직선에서 곡선이나 더 복잡한 선까지 하나로 연결만 되어 있다면 다 그릴 수 있다.

![image-center]({{ site.url }}{{ site.baseurl }}/assets/images/unity/unity.linerenderer.jpg){: .align-center}
_유니티 공식 문서의 Line Renderer_

## 🌟 사용법

```c#
private LineRenderer lineRenderer;

void Start()
{
	lineRenderer.positionCount = 10; //사용할 점의 개수
	lineRenderer.SetPosition(0, new Vector3(0, 0, 0)); //인덱스 순서로 점을 연결
	...
}
```

인덱스를 추가하여 점을 늘리고 선을 연결할 수 있다!