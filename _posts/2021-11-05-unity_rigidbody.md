---
title: "Unity. 리지드바디와 OnCollisionEnter, OnTirggerEnter"
categories:
  - Unity
tags:
  - Unity
  - 기초
---



리지드바디의 속성 중 isKinematic은 유니티의 물리 영향을 받을 지 말지 결정한다. 



두 개의 오브젝트가 있을 때, 한쪽에 isKinematic가 off된 채로 리지드바디가 있고, Collider도 있으며 상대한테도 Collider가 있다면 OnCollisionEnter가 작동한다.



Collider의 isTrigger는 마찬가지로 물리를 무시할 수 있다.

둘 다 Collider가 있고, 둘 중 하나가 isTrigger 켜져 있으며, 둘 중 하나 리지드바디가 있으면 OnTriggerEnter가 작동한다.