---
title: "Unity. 디자인패턴-싱글톤(Singleton)"
categories:
  - Unity
tags:
  - Unity
  - 알고리즘
---

## 🌟 Singleton

- **게임 전체를 관리하는 스크립트**
- **씬을 이동해도 파괴되지 말아야 함**
- **게임에서 단 하나만 존재해야 함**
- **게임에서 전역 변수 역할을 함**

위에 해당된다면 싱글톤 패턴으로 스크립트를 짜야 한다. 싱글톤은 주로 게임 매니저 역할을 하는 스크립트에 많이 씀!

## 🌟 사용법

```c#

public static GameManager instance = null;

void Awake()
{
	if (instance == null)
	{
		instance = this; //자기 자신을 인스턴스로 넣어줌
		DontDestroyOnLoad(gameObject); //씬이 로드되었을 때, 이동되었을 때 파괴하지 않고 게임 매니저를 유지
	}
	else
	{
		Destroy(this.gameObject); //인스턴스가 null이 아니라면 이 객체를 파괴
	}
}

public static GameManager Instance
{
	get
	{
		if (null == instance)
		{
			return null;
		}
		return instance;
	}
}

```

이렇게 게임 매니저를 싱글톤으로 구성하면 `GameManager.Instane.(public 변수나 함수)`를 통해 다른 객체에서 접근할 수 있다. 싱글톤을 사용하는 객체에 너무 많은 기능을 넣으면 안된다. 프로젝트를 진행하면서 갈아엎을 수도 있기 때문!