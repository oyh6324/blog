---
title: "Unity. Rigidbody 정리"
categories:
  - Unity
tags:
  - Unity
  - 기초
---

## 🌟 Rigidbody란

오브젝트에 물리 효과를 넣어주는 컴포넌트다. `Rgidbody`를 추가하면 오브젝트가 사실적으로 움직이고 중력을 받을 수 있다.

## 🌟 프로퍼티

- **Mass**: 오브젝트의 질량
- **Drag**: 공기 저항이 오브젝트에 미치는 정도(0이면 없는 것)
- **Angular Drag**: 오브젝트가 토크로 회전할 때 공기 저항이 미치는 정도
- **Use Gravity**: 중력 영향의 유무
- **Is Kinematic**: 활성화되면 물리 엔진으로 제어되지 않음
- **Interpolate**: None(보간 적용하지 않음), Interpolate(이전 프레임의 트랜스폼에 맞게 움직임 처리), Extrapolate(다음 프레임의 트랜스폼 추정해 움직임 처리)
- **Collision Detection**: Discrete(모든 콜라이더에 대해 불연속 충돌 검사 사용. 기본값), Continuous(Continuous, Continuous Dynamic 충돌로 설정된 오브젝트에 스위핑 기반 연속 충돌 검사 사용. 정적 콜라이더에 연속 충돌 검사를 사용. 그 외 다른 콜라이더에는 불연속 충돌 검사 사용. 빠르게 움직이는 오브젝트에 적합), Continuous Speculative(추측성 연속 충돌 검사 사용. 키네마틱 바디 설정할 수 있음. 리소스 덜 소모)
- **Constrain**t: Freeze Position(x, y, z 축 고정 가능), Freeze Rotation(회전 고정 가능)