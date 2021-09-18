---
title: "Unity. SerializeField와 HideInInspector 알아보기"
categories:
  - Unity
tags:
  - 기초
  - Unity
---

## 🌟 SerializeField와 HideInInspector 

SerializeField는 원하는 변수 또는 함수를 인스펙터 창에서도 보일 수 있게 직렬화하는 키워드다. 반대로 HideInInspector는 인스펙터 창에서 원하는 변수 또는 함수를 가려주는 역할을 한다.

## 🌟 직렬화란?

우리가 볼 수 없는 추상적인 데이터를 볼 수 있고 저장 가능하게 바꾸는 것을 말한다. 이 반대는 **역직렬화**라고 한다.

## 🌟 사용법

```c#
using UnityEngine;
using System.Collections;

[SerializeField]
private int a; //private지만 인스펙터에 보임

[HideInInspector]
public string name; //public이지만 인스펙터에 안 보임
```

이렇게 간단하게 사용할 수 있다. 바로 아래나 옆에 있는 변수만 해당된다. 클래스나 구조체를 노출하고 싶은 경우에는 `Serializable`을 사용하면 된다.