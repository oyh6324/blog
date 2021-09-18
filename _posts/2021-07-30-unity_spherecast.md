---
title: "Unity. Physics.SphereCast()"
categories:
  - Unity
tags:
  - 중급
  - Unity
---

## 🌟 Physics.SphereCast()

연속하는 구 안의 충돌체를 반환한다.

![image-center]({{ site.url }}{{ site.baseurl }}/assets/images/unity/unity.spherecast.jpg){: .align-center}
_푸른 지점의 충돌체를 반환_

## 🌟 사용법

```c#
using UnityEngine;
using System.Collections;

public class ExampleClass : MonoBehaviour {
	CharacterController charCtrl;
	
	void Start() {
		charCtrl = GetComponent<CharacterController>();
	}
	
	
    void Update() {
        RaycastHit hit;

        Vector3 p1 = transform.position + charCtrl.center;
        float distanceToObstacle = 0;
        
        // Cast a sphere wrapping character controller 10 meters forward
        // to see if it is about to hit anything.
        if (Physics.SphereCast(p1, charCtrl.height / 2, transform.forward, out hit, 10)) {
        	distanceToObstacle = hit.distance;
        }
    }
}
```

유니티 공식 문서에서 들고 왔다. 인자는 **시작 지점**과 **구체의 반경**, **ray의 길이**, **layerMask**가 주로 쓰인다.