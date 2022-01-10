---
title: "Unity. C# Stack 알아보기"
categories:
  - Unity
tags:
  - Unity
  - C#
---

## 🌟 Stack

데이터 구조 중 하나로, 알고 있겠지만 가장 먼저 들어 온 데이터가 가장 나중에 나가는 형식이다!



## 🌟 사용법

```c#
Stack<int> stack = new Stack<int>();

void Start()
{
    stack.Push(1);
    stack.Push(5);
    
    int num = stack.Pop(); //맨 위의 데이터를 제거하고 반환
    int num2 = stack.Peek(); //맨 위의 데이터를 반환
}
```



데이터를 꺼낼 때에는 Pop과 Peek 메소드가 있는데, Peek은 데이터를 제거하지 않고 반환만 한다.
