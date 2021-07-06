---
title: "Unity. Input으로 입력 받기 (2) 가상 버튼"
categories:
  - Unity
tags:
  - Unity
  - 기초
---

## 가상 버튼이란

가상 버튼은 유니티 내부에 있는, ‘buttonName’에 의해 식별되고 있는 버튼을 말한다. 가상 버튼은 유니티 상단의 `Edit-Project Settings-Input Manager`에 들어가면 확인할 수 있다.

![2](/assets/img/Unity기초/unity.input2-2.jpg){: width="500"}
_Project Settings의 Input Manager_

위 사진과 같이 Horizon, Vertical 등 다양한 버튼이 등록되어 있는데 사용자 마음대로 바꿀 수 있다. 

## 가상 버튼 입력 처리

가상 버튼 또한 마우스와 키보드와 마찬가지로 세 가지 상태로 나눌 수 있다. 버튼을 누르고 있는 동안 발동되는 `GetButton`과 버튼을 누른 순간 발동되는 `GetButtonDown`, 버튼을 눌렀다 뗐을 때 발동되는 `GetButtonUp`이 있다.

```c#
if (Input.GetButton("Fire1")) //true or false 반환
{
	//버튼을 누르고 있을 때 해야할 것
}
if (Input.GetButtonDown("Jump")) //true or false 반환
{
	//버튼을 눌렀을 때 해야할 것
}
if (Input.GetButtonUp("Fire2")) //true or false 반환
{
	//버튼을 뗐을 때 해야할 것
}
```

총을 쏘는 버튼이나 점프 버튼은 위와 같이 사용하면 된다. 그리고 `GetButton` 말고도 `GetAxis`가 있는데 이는 -1부터 1까지의 값을 반환한다.

```c#
float horizontal = Input.GetAxis("Horizontal"); //-1~1 반환
float vertical = Input.GetAxis("Vertical"); //-1~1 반환
```

좌우나 위아래의 움직임에 대해 주로 쓰인다. 예를 들자면, Horizontal을 통해 왼쪽으로 가면 -1과 가깝게, 오른쪽으로 가면 1과 가깝게 지정한 것이다. 이를 통해 캐릭터의 움직임을 구현할 수 있다.

## 가상 버튼을 쓰는 이유

가상 버튼을 사용하면 키보드와 조이콘에 대응할 수 있다는 장점이 있다. Horizontal에 방향키와 조이콘을 넣어두면 `GetAxis` 를 통해 코드를 수월하게 짤 수 있다!