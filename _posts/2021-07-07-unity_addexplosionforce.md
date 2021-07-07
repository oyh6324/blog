---
title: "Unity. Rigidbody.AddExplosionForce()"
categories:
  - Unity
tags:
  - Unity
  - 기초
---

## Rigidbody.AddExplosionForce()

폭발이 일어난 것처럼 폭발점 근처의 오브젝트를 흔들 수 있는? 함수다. 폭발의 힘을 받은 오브젝트 입장에서 사용한다.

## 사용법

```c#
    public float radius = 5.0f;
    public float power = 10.0f;

    void Start()
    {
        Vector3 explosionPos = transform.position; //폭발 위치
        Collider[] colliders = Physics.OverlapSphere(explosionPos, radius); //폭발 힘을 받을 충돌체 감지
        foreach (Collider hit in colliders)
        {
            Rigidbody rb = hit.GetComponent<Rigidbody>();

            if (rb != null)
                rb.AddExplosionForce(power, explosionPos, radius, 3.0F); //폭발 힘, 폭발 위치, 폭발 반경, 위로 솟구치는 힘
        }
    }
```

`Rigidbody.AddExplosionForce()`는 `Physics.OverlapSphere()`와 쓰면 좋다. 위 코드대로 사용하면 폭발점에 위치한 오브젝트의 반경 5.0f 안에 있는 colliders들이 폭발에 의해 힘을 받아 흔들리는 모션을 보여줄 것이다. 모션은 폭발점에서 멀어질수록 약해진다.