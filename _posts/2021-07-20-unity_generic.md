---
title: "Unity. C# 제네릭(Generic) 사용하기"
categories:
  - Unity
tags:
  - 중급
  - Unity
  - C#
---

## 제네릭이란?

함수나 클래스를 정의할 때, int나 string처럼 정해두지 않도 타입 파라미터를 사용해서 데이터 형식을 지정하지 않는 걸 말한다! 코드재사용이 높다는 장점이 있음!

## 사용법

```c#
void SumI(int a, int b)
{
	int c = a + b;
	Debug.Log(c);
}

void SumF(float a, float b)
{
	float c = a + b;
	Debug.Log(c);
}
```

제네릭을 사용하면 비슷한 두 함수를 하나로 만들 수 있다.

```c#
void Sum<T>(T a, T b)
{
	var c = a + b;
	Debug.Log(c);
}
```

이렇게! 여기서 `var`는 a와 b 값에 따라 아무 타입이나 지정된다.