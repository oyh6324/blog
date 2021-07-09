---
title: "Unity. C# 프로퍼티(Property)"
categories:
  - Unity
tags:
  - 기초
  - C#
  - Unity
---

## Property

C#에서 private 변수를 사용하면 get/set 함수를 만들어서 접근해야 했는데, 프로퍼티를 사용하면 간단하게 get/set을 만들 수 있다.

## 사용법

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

get은 속성 값을 반환하고, set은 값을 할당한다. 여기서 set에 조건을 달아 20미만은 값을 지정할 수 없도록 해주었다. value는 set을 사용할 때 쓰는 매개변수이다.

여기서 public 변수를 읽기만 가능하게 제어할 수도 있다.

```c#
public int age { get; private set; }
```

이렇게 사용하면 age는 외부에서 읽을 수는 있지만, 값을 할당할 수는 없다.