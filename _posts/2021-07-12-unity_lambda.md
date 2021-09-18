---
title: "Unity. C# 람다식 사용하기"
categories:
  - Unity
tags:
  - 중급
  - Unity
  - C#
---

## 🌟 람다식(Lambda Expression)이란?

C#에 있는 무명 함수 표현법 중 하나로, `(input-parameters) => { <sequence-of-statements> }` 이런 식으로 사용될 수 있다. 무슨 말인지 잘 모르겠으니 예제를 보자!

## 🌟 사용법

```c#
void PrintHello(string name)
{
	Debug.Log("Hello, " + name);
}

```

Hello 이름을 출력하는 함수를 람다식으로 바꾸면 다음과 같다.

```c#
name => Debug.Log("Hello, " + name);
```

`input-parameters`는 여기서 name이고 `=>` 다음이 이 무명 함수가 실행할 내용이다. 즉, `PrintHello`가 람다 함수로 바뀌어서 한 줄이 된 것!

람다식은 델리게이트와 함께 사용하면 편리하다. 또한 **`() => {}`**은 아무것도 하지 말라는 뜻이다.
 
```c#
private int age;
public int Age {
	get { return age; }
	set {
		if (value > 20) {
			age = value;
		}
	}
}
```

람다는 프로퍼티를 줄일 때도 유용하다 위 코드를 사용하면

```c#
private int age;
public int Age {
	get => age;
	set => {if (value > 20) age = value;}
}
```

이렇게 바꿀 수 있다. 별로 달라진 것 같진 않지만 아무튼 유용함! 생각날 때 써보도록 하자! 까먹지 말고!