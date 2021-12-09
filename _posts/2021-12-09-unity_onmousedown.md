---
title: "Unity. OnMouseDown으로 오브젝트 클릭하기"
categories:
  - Unity
tags:
  - Unity
  - 기초
---



## 🌟 OnMouseDown()

전에 UI에서 클릭을 받을 때는 따로 인터페이스를 추가해서 넣었는데, OnMouseDown은 MonoBehavior 인터페이스에 있는 함수라 따로 추가할 필요 없다.



OnMouseDown()가 작동되려면 콜라이더를 가지고 있어야 하고, 모바일에서는 구동되지 않는다.

## 🌟 사용법

```c#
void OnMouseDown(){
    Debug.Log("클릭함");
}
```

이렇게 하고 오브젝트에 스크립트를 넣으면 끝!
