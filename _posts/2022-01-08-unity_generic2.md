---
title: "Unity. C# 제네릭(Generic) 사용하기 (2)"
categories:
  - Unity
tags:
  - Unity
  - 중급
  - C#
---



제네릭을 사용할 때 조건을 사용할 수 있다!



```c#
public T Load<T>(string path) where T : Object
{
    return Resources.Load<T>(path);
}
```



`where T : Object`는 T가 Object 타입라고 조건을 거는 것. `where T : new()`라고 해서 T는 디폴트 생성자를 가져야 한다고 지정할 수도 있다. 이외에도 파생 클래스여야 한다거나, 인터페이스를 가져야 한다거나 조건을 붙일 수 있음.
