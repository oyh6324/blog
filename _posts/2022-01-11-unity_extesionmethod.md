---
title: "Unity. C# 확장 메소드(Extension Method) 알아보기"
categories:
  - Unity
tags:
  - Unity
  - C#
  - 중급
---

## 🌟 확장 메소드란?

확장 메소드는 정적 메소드처럼 정의하지만, 사용은 인스턴스 메소드처럼 하는 메소드다.



여기서 정적 메소드는 static을 붙인 메소드고, 인스턴스 메소드는 클래스 개체의 생성을 해야 하는 일반 메소드다.



바로 예시!

## 🌟 사용법

> 확장 코드

```c#
public static class Extension
{
    public static void Print(this string str)
	{
    	Debug.Log(str);
	}
}
```



> 사용

```c#
public class Test
{
    void Start()
    {
        "Hi".Print();
    }
}
```



이렇게 하면 바로 Hi가 출력됨!



____________



확장 메소드는 정적 메소드처럼 정의하지만, 첫 번째 매개 변수로 어떤 확장 메소드인지 결정하게 된다.
