---
title: "Unity.  Quaternion(쿼터니언)의 함수들"
categories:
  - Unity
tags:
  - Unity
  - 기초
---

## Quaternion.LookRotation()

```c#
void Update()
{
	Vector3 relativePos = target.position - transform.position; //바라볼 방향 구함
	transform.rotation = Quaternion.LookRotation(relativePos); //relativePos로 바라보기
}
```

`Quaternion.LookRotation()` 벡터 값에 대해 회전할 수 있도록 하는 함수다. 다시 말해 target 오브젝트 쪽을 바라보게 만들 수 있다. 게임 만들 때 유용할 듯!

##  Quaternion.Lerp()

```c#
void Update()
{
	transform.rotation = Quaternion.Lerp(from.rotation, to.rotation, 0.5f);
}
```

`Quaternion.Lerp()`은 A와 B 사이의 값을 리턴하는 함수다. 0.5f면 딱 절반, A와 B의 중간값이고 이 값이 작을수록 A에 가깝고 클수록 B에 가깝다. 위 코드는 from.rotation과 to.rotation의 중간값만큼 오브젝트를 회저시키고 있음.

##  Quaternion.eulerAngles

```c#
void Update()
{
	 rotation.eulerAngles = new Vector3(10, 0, 0);
}
```

`Quaternion.eulerAngles`은 쿼터니언을 오일러각으로 변환한다. 