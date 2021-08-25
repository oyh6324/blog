---
title: "Unity. Instantiate()로 오브젝트 복사하기"
categories:
  - Unity
tags:
  - 중급
  - Unity
---

## Instantiate()

복제하는 걸 인스턴스(instance)화 한다고 하며, 이때 Instantiate()가 쓰인다. 똑같은 몬스터를 찍어내거나 총알을 발사할 때 많이 쓰임!

## 사용법

```c#
using UnityEngine;

public class InstantiateExample : MonoBehaviour
{
    public GameObject prefab; //복제할 오브젝트

    void Start()
    {
        for (int i = 0; i < 10; i++) //10개 복제
            Instantiate(prefab, new Vector3(i * 2.0f, 0, 0), Quaternion.identity);
    }
}
```

유니티 공식 문서에서 들고 옴!
인수는 **복제할 오브젝트**, **새 오브젝트의 위치**, **새 오브젝트의 방향**을 나타낸다.

```c#
public GameObject prefab;

void Start()
{
    GameObject gameObject = Instantiate(prefab, gameobject.transform.parent);
}
```

이렇게 하면 prefab을 이 코드가 붙은 오브젝트의 자식에 붙여 넣기 할 수 있다.