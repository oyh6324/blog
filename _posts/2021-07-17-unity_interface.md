---
title: "Unity. C# 인터페이스(Interface) 사용하기"
categories:
  - Unity
tags:
  - 기초
  - Unity
  - C#
---

## 인터페이스란?

가상 함수랑 비슷한데, 인터페이스는 인터페이스로 지정한 클래스의 자식 클래스들이 부모 클래스의 함수나 프로퍼티를 모두 재정의해야 한다는 점이 다르다. 재정의 하지 않으면 오류가 뜨므로 인터페이스는 필요한 함수만 써야 한다.

## 사용법

```c#
public interface IHello
{
	void SayHello();
}
```

이렇게 인터페이스를 선언하고

```c#
public class Korean : MonoBehaviour, IHello 
{
	public void SayHello()
	{
		Debug.Log("안녕하세요.");
	}
}
```

다른 클래스에서 인터페이스 클래스를 상속받은 뒤, 부모 클래스의 함수를 재정의 하면 된다.

인터페이스 스크립트는 ‘I’로 저장하는 게 좋다. 그래야 구분하기 편하니까!