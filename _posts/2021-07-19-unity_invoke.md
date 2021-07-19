---
title: "Unity. Invoke와 InvokeRepeating, CancelInvoke 사용하기"
categories:
  - Unity
tags:
  - 중급
  - Unity
  - C#
---

## Invoke, InvokeRepeating, CancelInvoke

모두 함수를 실행하지만, 지연되게 실행할 수 있는 함수다. 셋 다 기능이 다름!

## 사용법

### Invoke

```c#
void Start()
{
	Invoke("SayHello", 3.0f);
]

void SayHello()
{
	Debug.Log("안녕하세요.");
}
```

Invoke의 인자는 **함수명**, **지연 시간**으로 이루어져 있으며 지연 시간 후에 원하는 함수가 작동된다. 위 코드대로 하면 스크립트가 활성화되고 3초 뒤에 ‘안녕하세요’가 출력될 것!

### InvokeRepeating

```c#
void Start()
{
	InvokeRepeating("SayHello", 3.0f, 2.0f);
]

void SayHello()
{
	Debug.Log("안녕하세요.");
}
```

InvokeRepeating은 **반복 주기**를 인자로 받아서 지연 시간 후 함수를 호출하고 반복 주기만큼 일정하게 계속 호출하는 함수다. 3초가 지나고 SayHello가 호출된 뒤, 이제 2초마다 계속 호출될 것이다.

### CancelInvoke

```c#
CancelInvoke("SayHello");
```

CancelInvoke는 간단하다. Invoke 함수를 취소할 수 있음!