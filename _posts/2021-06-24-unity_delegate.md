---
title: "Unity. 델리게이트(Delegate)"
categories:
  - Unity
tags:
  - Unity
  - 중급
---

## Delegate

델리게이트는 여러 개의 함수를 가리키는 포인터 같은 역할을 한다. 델리게이트에 함수를 등록하고 그 델리게이트를 실행하면 등록된 함수들이 실행된다.

## 사용법

```c#
delegate void PlayerDie();
PlayerDie playerDie;

void PlayerDestroy()
{
	//플레이어를 삭제하는 코드
}

void ItemReset()
{
	//아이템을 제거하는 코드
}

void GameOver()
{
	//게임을 종료하는 코드
}

void Start()
{
	playerDie = PlayerDestroy; //함수 등록
	playerDie += ItemReset;
	playerDie += GameOver;

	playerDie();
}
```

플레이어가 죽었을 때 델리게이트로 후속 처리하는 코드다. 플레이어가 죽었다면, 플레이어를 삭제하고 아이템도 리셋한 뒤 게임을 끝내야 한다. 델리게이트를 사용하면 순차적으로 실행됨으로써 효율을 높일 수 있다. 