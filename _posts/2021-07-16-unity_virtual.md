---
title: "Unity. C# 가상 함수(Virtual) 사용하기"
categories:
  - Unity
tags:
  - 기초
  - Unity
  - C#
---

## 가상 함수란?

virtual을 사용하여 함수를 만들면, 그 클래스를 상속 받은 자식 클래스에서 그 함수를 재정의할 수 있다. 

## 사용법

```c#
public class Man //부모 클래스
{
	public virtual void Hello()
	{
		Debug.Log("인사하기");
	]
}

//자식 클래스
public class Korean : Man
{
	public override void Hello() //함수 재정의
	{
		Debug.Log("안녕하세요.");
	]
}

public class American : Man
{
	public override void Hello() //함수 재정의
	{
		Debug.Log("Hi.");
	]
}
```

유니티에서 사용하면 아마 각자 다른 스크립트가 될 확률이 높지만, 간단하게 모아 보자면 위 코드의 형식대로 될 것이다. 부모 클래스에서 가상 함수를 사용하고, 이 가상 함수를 자식 클래스에서 재정의 할 수 있다. 재정의 하지 않으면 부모 클래스의 함수를 실행하게 된다. 

```c#
public class Korean : Man
{
	public override void Hello() //함수 재정의
	{
		base.Hello();
		Debug.Log("안녕하세요.");
	]
}
```

또한 위 코드의 `base.Hello()`는 부모 클래스의 가상 함수를 사용한 것이다. 

또한 override 대신 new를 사용하면 부모 클래스의 함수를 숨길 수 있다. 숨기고 자식 클래스의 함수를 대신 사용한다.