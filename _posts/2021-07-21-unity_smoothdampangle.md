---
title: "Unity. Mathf.SmoothDampAngle()"
categories:
  - Unity
tags:
  - 중급
  - Unity
---

## 🌟 Mathf.SmoothDampAngle()

시간이 지남에 따라 목표 각도로 향하는 함수다.

## 🌟 사용법

```c#
using UnityEngine;
using System.Collections;

public class ExampleClass : MonoBehaviour {
    public Transform target; //도달하려는 위치
    public float smooth = 0.3f; //타켓에 도착하는 대략적인 시간
    public float distance = 5.0f; 
    private float yVelocity = 0.0f; //현재 속도 담을 변수
    void Update() {
        float yAngle = Mathf.SmoothDampAngle(transform.eulerAngles.y, target.eulerAngles.y, ref yVelocity, smooth);
        Vector3 position = target.position;
        position += Quaternion.Euler(0, yAngle, 0) * new Vector3(0, 0, -distance);
        transform.position = position;
        transform.LookAt(target);
    }
}
```

유니티 공식 문서에서 가져옴!

SmoothDampAngle의 인자는 **현재 위치값**, **도달하려는 위치**, **현재 속도**, **타겟에 도착하는 시간**, 선택적으로 **최대 속도**와 **경과 시간**이 있다. 앞의 네 개만 신경쓰면  될듯!

`float yAngle = Mathf.SmoothDampAngle(transform.eulerAngles.y, target.eulerAngles.y, ref yVelocity, smooth);`을 보면 transform.eulerAngles.y에서 target.eulerAngles.y이 각도로 smooth 시간 동안 변경되는 걸 알 수 있다! 밑의 코드는 잘 모르겠음