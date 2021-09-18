---
title: "Unity. 코루틴(Coroutine)"
categories:
  - Unity
tags:
  - Unity
  - 중급
---

## 🌟 Coroutine

코루틴은 반환값을 통해 실행을 중지해서 Unity에게 제어권을 돌려주고, 계속할 때는 다음 프레임에서 중지한 곳부터 실행을 계속하는 하뭇다. 코루티는 대부분 반환값으로 특정 시간을 기다릴 수 있게 사용함! 

## 🌟 사용법

```c#

public static GameManager instance = null;

void Awake()
{
	StartCoroutine(Fade());
}

IEnumerator Fade()
{
	for (float f = 1f; f >= 0; f -= 0.1f) 
	{
		Color c = renderer.material.color; //해당 게임 오브젝트의 컬러
        		c.a = f; //투명도 조절
        		renderer.material.color = c; //조절한 투명도를 게임 오브젝트에게 씌움
        		yield return new WaitForSeconds(0.1f); //0.1초 기다림
	}
}

```

위 코드는 게임 오브젝트의 밝기를 조절하는 함수로 코루틴을 사용해서 몇 초 동안 사라지게 할 지 정할 수 있게 했다. 코루틴은 `StartCoroutine()` 함수를 통해 시작하며, `StartCoroutine()`을 사용하는 방법에는 두 가지가 있는데 위 코드처럼 사용할 수도 있고, `StartCoroutine("Fade")` 이런 식으로 사용할 수도 있다. 문자열 버전은 코루틴을 중간에 멈출 수 있지만, 더 높은 런타임 오버 헤드를 가지며 하나의 매개 변수만 사용할 수 있다.
