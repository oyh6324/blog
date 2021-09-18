---
title: "Unity. GetComponent 사용하기"
categories:
  - Unity
tags:
  - Unity
  - 기초
---

## 🌟 GetComponent란

해당 GameObject에 속해 있는 Component를 하나 가져올 수 있게 하는 함수!

```c#
public GameObject sample;
private void Awake()
{
	Image sampleImg = sample.GetComponent<Image>(); //sample 게임 오브젝트에서 Image Component 추출
}
```

public으로 등록한 오브젝트에서 `GetComponent`로 접근하여 해당 오브젝트의 Component를 가져올 수 있다.

```c#
private void Awake()
{
	Image thisImg = GetComponent<Image>(); //본 오브젝트에서 Image Component 추출
}
```

만약 GetComponent 앞에 게임 오브젝트를 지운다면 이 스크립트를 사용하고 있는 오브젝트에서 해당 타입의 Component를 가져올 수 있도록 할 수 있다.
`GetComponent`는 기본적으로 `GetComponent<T>()` 형식으로 쓴다. T는 Component의 타입이다.

## 🌟 GetComponentInChildren

`GetComponentInChildren`은 `GetComponent`와 마찬가지로 Component를 가져오는 역할을 하는데, 해당 오브젝트의 자식 오브젝트 중 가장 먼저 나열되어 있는 오브젝에서 Component를 가져온다. 쓰는 방법은 `GetComponent`와 동일!

## GetComponentInParent

`GetComponentInParent`는 해당 오브젝트의 부모 위치에 있는 오브젝트에게서 Component를 가져온다. 

## 🌟 Array 형식

위 함수는 Component를 하나씩 가져오지만 배열 형태로 가져오는 함수도 있다. `GetComponents`, `GetComponentsInChildren`, `GetComponentsInParent`는 자기 자신을 포함하여 해당되는 각 오브젝트의 Component를 배열로 가져올 수 있다.