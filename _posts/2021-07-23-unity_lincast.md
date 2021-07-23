---
title: "Unity. Physics.Linecast()"
categories:
  - Unity
tags:
  - 중급
  - Unity
---

## Physics.Linecast()

Raycast와 비슷하다. Raycast는 원하는 방향으로 선을 긋지만, Linecast는 시작 지점과 끝 지점이 명확하게 있어야 선을 그을 수 있다.

## 사용법

```c#
using UnityEngine;
using System.Collections;

public class ExampleClass : MonoBehaviour {
    public Transform target;
    void Update() {
        if (Physics.Linecast(transform.position, target.position)) {
            Debug.Log ("blocked");
        }
    }
}
```

유니티 공식 문서에서 들고 옴!

인자는 **시작 지점**, **끝 지점**, **레이어 마스크** 이렇게 세 가지가 자주 사용된다.