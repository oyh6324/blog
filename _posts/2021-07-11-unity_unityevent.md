---
title: "Unity. UnityEvent 사용하기"
categories:
  - Unity
tags:
  - 중급
  - Unity
---

## UnityEvent란?

`UnityEvent`는 델리게이트를 Unity에서 사용하기 편하게 만든 것이다. 따라서 C#에는 없고 Unity에만 존재한다.

## 사용법

```c#
public class ExampleClass : MonoBehaviour
{
    UnityEvent m_MyEvent;

    void Start()
    {
        if (m_MyEvent == null)
            m_MyEvent = new UnityEvent();

        m_MyEvent.AddListener(Ping); //UnityEvent에 함수 추가
    }

    void Update()
    {
        if (Input.anyKeyDown && m_MyEvent != null)
        {
            m_MyEvent.Invoke(); //UnityEvent 호출
        }
    }

    void Ping()
    {
        Debug.Log("Ping");
    }
}
```

위 코드는 유니티 공식 문서에서 가져옴! 

코드를 보면 알 수 있듯 `AddListener`로 유니티 이벤트에 필요한 함수를 추가할 수 있고, `Invoke`로 유니티 이벤트를 실행할 수 있다. 추가한 함수를 지우고 싶다면 `RemoveListener`를 사용하면 된다. 유니티 이벤트에 여러 개의 동일한 함수를 입력하면, 하나만 콜백한다. 그리고 등록한 함수는 4개의 인자까지만 가져야 한다.