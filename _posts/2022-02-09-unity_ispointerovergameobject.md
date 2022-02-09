---
title: "Unity. IsPointerOverGameObjet로 클릭한 UI 확인하기"
categories:
  - Unity
tags:
  - Unity
  - 중급
---

## 🌟 IsPointerOverGameObjet()

포인터가 UI 위에 있는 걸 알려주는 함수다. 게임 오브젝트 위에 있으면 false, UI 위에 있으면 true가 반환됨!



## 🌟 사용법

```c#
if(UnityEngine.EventSystems.EventSystem.current.IsPointerOverGameObject())
{
    //UI 누른 게 맞았을 때
}
```



모바일에서 안 되는 건 포인터 아이디를 지정해줘야 하기 때문!



0: 첫 번째 터치, 1: 두 번째 터치, -1: 컴퓨터 클릭!



`IsPointerOverGameObject(0)`



이렇게 사용하면 됨!
