---
title: "Unity. 오브젝트 바라보게 하기"
categories:
  - Unity
tags:
  - Unity
  - 기초
---



## 🌟 tranform.LookAt()

쿼터니언할 때 배웠던 Quaternion.LookRotation보다 조금 더 간단하게 쓸 수 있다. 마찬 가지로 타겟을 정하고 그걸 바라보게 만드는 함수임!



## 🌟 사용법

```c#
public Transform target;

private void Update()
{
    transform.LookAt(target);
}
```

이렇게 하면 이 코드가 붙은 오브젝트는 target 위치를 계속 바라볼 것이다.
