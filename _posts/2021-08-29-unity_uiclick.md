---
title: "Unity. UI에서 마우스 클릭 받기"
categories:
  - Unity
tags:
  - Unity
  - UGUI
---

## 🌟 UGUI란?

유니티에서 제공하는 UI를 말한다. Canvas 안에서 다른 UI 오브젝트를 만들 수 있으며, Eventsystem가 UI의 터치 이벤트를 지원하고 있다.

## 🌟 종류

![image-center]({{ site.url }}{{ site.baseurl }}/assets/images/unity/unity.uiclick.jpg){: .align-center}
_유니티 공식 문서_

유니티 공식 문서에서 들고 온 인터페이스 종류다. 저 인터페이스를 구현하면 각각의 함수를 사용할 수 있음!

## 🌟 사용법

```c#
public class Sample : MonoBehaviour, IPointerClickHandler //인터페이스 상속
{
    public void OnPointerClick(PointerEventData eventData)
    {
        Debug.Log("클릭했습니다.");
    }
```

Sample 스크립트가 붙은 UGUI의 오브젝트는 이제 클릭을 감지할 수 있게 된다. 모바일에서도 잘 작동함!