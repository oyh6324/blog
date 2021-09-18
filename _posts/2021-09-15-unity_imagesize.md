---
title: "Unity. UGUI의 Image 크기 변경하기"
categories:
  - Unity
tags:
  - Unity
  - UGUI
---

## 🌟 Image

UI의 Image는 Rect Transform 가지고 있고 여기서 width과 height을 조절할 수 있다. 모든 UGUI는 Rect Transform을 가지고 있음!

## 🌟 사용법

```c#
void Start()
{
        gameObject.GetComponent<RectTransform>().sizeDelta = new Vector2(100, 100); //width과 height 한 번에 지정
        float width= gameObject.GetComponent<RectTransform>().rect.width; //길이 가져오기
        float height = gameObject.GetComponent<RectTransform>().rect.height;
}
```

sizeDelta로 길이를 지정할 수 있고, rect.width/height로 길이를 가져올 수도 있다.