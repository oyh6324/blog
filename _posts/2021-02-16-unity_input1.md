---
title: "Unity. Input으로 입력 받기 (1) 마우스, 키보드"
categories:
  - Unity
tags:
  - Unity
  - 기초
---

## 마우스 입력 처리

마우스 입력은 기본적으로 세 가지 경우로 나누어서 처리된다. 
마우스를 누르는 동안 계속 발동되는 `GetMouseButton`과 누르는 순간 발동되는 `GetMouseButtonDown`, 그리고 마우스를 눌렀다가 떼는 순간 발동되는 `GetMouseButtonUp`이 이에 해당한다.

모두 bool 값을 반환하고 주로 Update에서 자주 사용된다. (마우스를 눌렀는지 안 눌렀는지 계속 확인해야 하니까!)

```c#
if (Input.GetMouseButton(0)) //true or false 반환
{
	//마우스를 누르고 있을 때 해야할 것
}
if (Input.GetMouseButtonDown(1)) //true or false 반환
{
	//마우스를 눌렀을 때 해야할 것
}
if (Input.GetMouseButtonUp(2)) //true or false 반환
{
	//마우스를 뗐을 때 해야할 것
}
```

그리고 여기서 숫자 0, 1, 2는 정수형 파라미터로 마우스의 버튼을 구분해준다. 

- **0**: 마우스 왼쪽 버튼
- **1**: 마우스 오른쪽 버튼
- **2**: 마우스 중앙 버튼


## 키보드 입력 처리

키보드도 마우스와 마찬가지로 키를 누르고 있을 때 발동되는 `GetKey`과 키를 누르는 동안 발동되는 `GetKeyDown`, 눌렀다 뗐을 때 발동되는 `GetKeyUp` 세 가지 경우로 나눌 수 있다.

마우스와 똑같이 bool 값을 반환한다.

```c#
if (Input.GetKey(KeyCode.UpArrow)) //true or false 반환
{
	//키보드를 누르고 있을 때 해야할 것
}
if (Input.GetKeyDown(KeyCode.Space)) //true or false 반환
{
	//키보드를 눌렀을 때 해야할 것
}
if (Input.GetKey(KeyCode.LeftShift)) //true or false 반환
{
	//키보드를 뗐을 때 해야할 것
}
```

KeyCode를 통해 어떤 키를 눌렀는지 구분한다. 방향키, 스페이스바, Shift 키 뿐만이 아니라 키보드의 모든 키를 넣을 수 있다.

KeyCode 말고 다른 것도 넣을 수 있는데 그건 다음 포스트~~!