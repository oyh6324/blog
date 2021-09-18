---
title: "Unity. Random.insideUnitSphere로 구 안의 랜덤 위치 반환하기"
categories:
  - Unity
tags:
  - 중급
  - Unity
---

## 🌟 Random.insideUnitSphere

Random.insideUnitSphere는 Vector3를 반환하며 반경 1의 구 안의 랜덤한 위치를 반환한다.

## 🌟 사용법

```c#
using UnityEngine;
using System.Collections;

public class ExampleClass : MonoBehaviour {
    void Example() {
        transform.position = Random.insideUnitSphere * 5;
    }
}
```

유니티 공식 문서에서 들고 옴! 반경 5의 구에서 임의의 위치 반환하고 있다. 