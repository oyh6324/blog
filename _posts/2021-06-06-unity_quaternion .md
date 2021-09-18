---
title: "Unity. Rotation과 Quaternion(쿼터니언)"
categories:
  - Unity
tags:
  - Unity
  - 기초
---

## 🌟 Rotation

Rotation 함수는 오브젝트를 회전시킬 수 있다. 

##  🌟 Rotation과 Quaternion(쿼터니언) 사용법

```c#
void Update()
{
	transform.rotation = Quaternion.Euler(new Vector3(10, 10, 10));
}
```

`Quaternion.Euler`은 오일러각을 쿼터니언으로 바꾼 것. x축, y축, z축을 각각 10만큼 회전시키는 코드다! 저 자리에 그냥 Vector3 값을 넣으면 안된다!