---
title: "Unity. 스크립트로 버튼 이벤트 추가하기"
categories:
  - Unity
tags:
  - Unity
  - UGUI
---

## 🌟 Button Event

UI의 Button 오브젝트는 인스펙터 창에서 이벤트를 추가할 수도 있지만, 코드 상에서도 이벤트를 추가할 수 있다. onClick()을 쓰면 됨!

## 🌟 사용법

```c#
public Button button;

void Start()
{
        button.onClick.AddListener(buttonEvent); //이벤트 추가
        button.onClick.RemoveAllListeners(); //이벤트 모두 제거
}

void buttonEvent()
{
       Debug.Log("Button Click");
}
```

`onClick.AddListener()`가 원하는 메소드를 이벤트로 추가해주고 `onClick.RemoveAllListeners()`가 원하는 버튼의 모든 이벤트를 제거해준다. 하나만 제거할 수 있는 `onClick.RemoveListener()`도 있다!