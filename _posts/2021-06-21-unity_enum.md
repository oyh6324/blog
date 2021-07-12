---
title: "Unity. C# enum과 switch 사용"
categories:
  - Unity
tags:
  - Unity
  - 중급
  - C#
---

## enum

enum은 C#에서 사용하는 열거형 상수 집합이다. 열거형 멤버의 이름을 정할 수 있고, 각각 연결된 상수 값은 int 형식을 가진다.

```c#
public enum State
{
	Idle,
	Shooting,
	Dead
}
```

이런 식으로 State라는 enum을 만들면 `Idle=0`, `Shooting=1`,  `Dead=2` 이런 식으로 단어와 상수 값이 연결된다. 배열 같은 느낌?

```c#
public enum State
{
	Idle,
	Shooting=4,
	Dead
}
```

이렇게 중간에 상수 값을 바꿔줄 수도 있다. 그러면  `Idle=0`, `Shooting=4`,  `Dead=5`가 된다.

## enum과 switch

```c#
 private enum Dress
    {
        Top, Helmet, Bottom
    }

private void WearingCheck()
    {
        switch (dress)
        {
            case Dress.Top:
                //dress=Dress.Top일 때 할 것
                break;
            case Dress.Bottom:
                //dress=Dress.Bottom일 때 할 것
                break;
            case Dress.Helmet:
                //dress=Dress.Helmet일 때 할 것
                break;
        }
```

이런 식으로 enum과 switch를 활용하면 상성이 좋다! enum은 상수 값을 쓰는 것보다 멤버 이름을 쓰는 게 더 알아보기 쉬운 듯!