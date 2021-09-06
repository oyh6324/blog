---
title: "Unity. Context Menu로 함수 실행하기"
categories:
  - Unity
tags:
  - Unity
  - 기초
---

## ContextMenu란?

함수 위에다가 작성하여 인스펙터 창에서 함수를 호출할 수 있게 하는 기능이다. 

## 사용법

```c#
public class ContextTesting : MonoBehaviour {
	/// Add a context menu named "Do Something" in the inspector
	/// of the attached script.
	[ContextMenu ("Do Something")] 
	void DoSomething () {
		Debug.Log ("Perform operation");
	}
}
```

유니티 공식 문서에서 들고 옴! 저걸 오브젝트에 넣고 인스펙터 창에 가면 스크립트의 오른쪽 점 세개 모양 안에 Do Something이 있을 것이다. 그걸 누르면 저 함수를 호출할 수 있다~!