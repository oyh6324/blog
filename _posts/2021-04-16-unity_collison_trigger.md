---
title: "Unity. Collison과 Trigger로 충돌 처리하기"
categories:
  - Unity
tags:
  - Unity
  - 기초
---

## Component 셋팅

충돌 처리를 하고 싶다면 기본적으로 해당 오브젝트에 `Collider`나 `Rigidbody` 컴포넌트를 넣어줘야 한다. `Collider`는 2D 전용, 사각형, 원형 등등 다양하게 있는데 오브젝트 모양과 속성에 따라 아무거나 사용하면 된다. `Rigidbody`는 2D인지 아닌지만 확인하면 된다! 물리 효과가 필요하지 않는 오브젝트라면 `Collider`만, 물리 효과가 필요하다면 둘 다 넣어야 한다. 그냥 게임 속 벽이라면 `Collider`만 넣어도 됨!! 움직이는 캐릭터라면 `Rigidbody`까지! 어쨌든 `Collider`는 필수.

## Collison 함수

```c#
void OnCollisionEnter(Collision collision) {
	//충돌 했을 때 사용할 코드 
}
void OnCollisionExit(Collision collisionInfo) {
	//충돌에서 벗어났을 때 사용할 코드
}
void OnCollisionStay(Collision collisionInfo) {
	//충돌하고 있을 때 사용할 코드
}
```

충돌 처리 함수는 세 가지가 있다. 첫 번째는 충돌했을 때 처음 호출되고, 두 번째는 충돌이 끝났을 때 호출되며, 세 번째는 충돌하고 있을 때 계속 호출된다. 

```c#
void OnCollisionEnter(Collision collision) {
	if(collision.tag=="Monster") { }
}
```

보통 충돌 처리가 필요한 오브젝트에 tag를 걸어서 어떤 오브젝트인지 확인한다. layer도 사용하는데 이건 다음에...언젠가...

## Trigger 함수

Collision은 부딪히면 튕기거나 그러는데 게임 NPC처럼 그냥 통과해서 지나가야 하는 경우도 있기 때문에, 물리 효과를 제외한 충돌 감지 함수도 있다. `Collider` 컴포넌트에서 `isTrigger` 항목에 체크하면 물리 효과를 뺄 수 있다. 하지만 그러면 충돌 감지 처리는 위 함수가 아닌 Trigger를 사용해야 함!!!

```c#
void OnTriggerEnter(Collider other) {
	//충돌 했을 때 사용할 코드 
}
 void OnTriggerExit(Collider other) {
	//충돌에서 벗어났을 때 사용할 코드
}
void OnTriggerStay(Collider other) {
	//충돌하고 있을 때 사용할 코드
}
```

사용 방법은 Collision 함수와 동일하다. 그런데 Collision과 Trigger 함수 모두 `Rigidbody`가 non-kinematic이어야 작동한다. 그게 무ㅓ더라?