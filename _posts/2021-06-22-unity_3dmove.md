---
title: "Unity. 방향키로 이동하기"
categories:
  - Unity
tags:
  - Unity
  - 중급
---

## 🌟 3D에서 방향키로 간단하게 이동하기

방향키로 간단하게 움직이는 방법!

```c#
public class PlayerMove : MonoBehaviour
{
    public float speed = 5f;
    private Rigidbody rigidbody;

    void Start()
    {
        rigidbody = GetComponent<Rigidbody>();
    }
    void Update()
    {
        float inputX = Input.GetAxis("Horizontal"); //오른쪽, 왼쪽 방향키
        float inputZ = Input.GetAxis("Vertical"); //위, 아래 방향키
        Vector3 velocity = new Vector3(inputX, 0, inputZ); 
        velocity = velocity * speed;
        playerRigidbody.velocity = velocity; //원하는 방향으로 speed 만큼 이동함
    }
}
```

velocity를 이용하면 간단하게 3D 오브젝트를 이동시킬 수 있다. velocity는 Rigidbody의 속도를 말한다. velocity를 높이면 Rigidbody를 갖고 있는 오브젝트의 속도가 높아진다!