---
title: "Unity. Vector3.SmoothDamp()"
categories:
  - Unity
tags:
  - 중급
  - Unity
---

## 🌟 Vector3.SmoothDamp()

게임을 만들 때 메인 카메라가 어느 정도 거리를 두고 플레이어를 따라 가게 하려면, Rig 오브젝트를 만들어서 메인 카메라를 하위에 두고 일정한 거리를 두게 만들어 Rig 오브젝트가 플레이어를 따라 가게 만드는 방법이 있다. 하지만 이것보다 더 부드러운 움직임을 구사해야 하는 경우가 있는데, 그때 바로 `Vector3.SmoothDamp()`를 사용한다.

## 🌟 사용법

```c#
public class ExampleClass : MonoBehaviour {
    public Transform target;
    public float smoothTime = 0.3F;
    private Vector3 velocity = Vector3.zero;
    void Update() {
        Vector3 targetPosition = target.TransformPoint(new Vector3(0, 5, -10));
        transform.position = Vector3.SmoothDamp(transform.position, targetPosition, ref velocity, smoothTime);
    }
}
```

첫 번째 인자는 **현재 위치**, 두 번째 인자는 **도달할 위치**, 세 번째는 **오브젝트의 마지막 속도, 즉, 현재 속도**이다. 이 때 세 번째 인자는 값이 매번 수정되고 마지막 인자는 타겟에 도달하기 위한 대략적인 시간이다. 시간이 짧을 수록 타겟에 빨리 도착한다.

```c#
public static Vector3 SmoothDamp(Vector3 current, Vector3 target, ref Vector3 currentVelocity, float smoothTime, float maxSpeed = Mathf.Infinity, float deltaTime = Time.deltaTime);
```

예시에는 없었지만 뒤에 추가적으로 최대 속도를 지정할 수 있다. deltaTime은 이 함수가 마지막으로 호출되고 나서의 경과 시간이다. 둘 다 디폴트로 지정된 게 있다.