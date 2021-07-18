---
title: "Unity. C# 추상 클래스(Abstract Class) 사용하기"
categories:
  - Unity
tags:
  - 기초
  - Unity
  - C#
---

## 추상 클래스란?

인터페이스와 비슷하지만, 내부 코드가 없는 인터페이스와 달리 추상 클래스는 내부 코드를 만들어 둘 수 있다.

## 사용법

```c#
public abstract class SampleClass : MonoBehaviour {

    public abstract void SayHello();
 
    void Start () {
        SayHello();
    }
}
```

추상 클래스에서 자식 클래스에 재정의가 필요한 함수만 앞에 `abstract`를 붙인다.

```c#
public class Korean : SampleClass {

    public override void SayHello()
    {
        Debug.Log("안녕하세요.");
    }
 
}
```

그리고 자식 클래스를 만들어서 이렇게 재정의하면 된다. 인터페이스와 매우 유사!