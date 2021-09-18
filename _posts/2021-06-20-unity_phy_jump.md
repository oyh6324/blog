---
title: "Unity. 물리에 의한 점프"
categories:
  - Unity
tags:
  - Unity
  - 중급
---

## 🌟 Rigidbody를 사용한 점프

```c#
public class SimpleJump : MonoBehaviour
{
    public float jumpPower;
    private Rigidbody2D rigidbody;
    void Awake()
    {
        rigidbody = GetComponent<Rigidbody2D>();
    }
    void Update()
    {
        if (Input.GetButtonDown("Jump"))
        {
            rigidbody.AddForce(Vector2.up * jumpPower, ForceMode2D.Impulse);
        }
    }
}
```

유니티에서 지정된 점프 키를 눌렀을 때, `Rigidbody`로 캐릭터가 점프하는 것처럼 위로 올라가는 코드다. `AddForce`는 순간적으로 힘을 주는 함수인데, 게임에서 점프할 때 많이 쓰인다.