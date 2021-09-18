---
title: "Unity. 라이프사이클(Life Cycle)"
categories:
  - Unity
tags:
  - Unity
  - 기초
---

## 🌟 Life Cycle

유니티의 생명 주기, 스크립트를 실행하면 정해진 순서대로 여러 개의 이벤트 함수가 발생하는 데 그 주기를 생명 주기라고 한다.

## 🌟 초기화 영역

- **Awake**: 게임 오브젝트 생성한 후, 최초 한 번만 실행된다.
- **OnEnable**: 스크립트가 활성화될 때마다 계속 실행된다.
- **Start**: Update 시작 직전에 최초 한 번만 실행된다.

## 🌟 물리 연산 영역
- **FixedUpdate**: Update와 달리 타이머를 통해 호출되기 때문에 `Time.deltaTime`를 사용하지 않아도 된다. 물리 연산 시작 전에 사용한다.

## 🌟 게임 로직 영역
- **Update**: 한 프레임에 한 번씩 호출되는 함수다. 
- **LateUpdate**: 모든 Update가 실행된 후 호출되는 함수다.

## 🌟 해체 영역
- **OnDisable**: 스크립트가 비활성화될 때마다 계속 실행된다.
- **OnDestroy**: 게임 오브젝트가 삭제될 때 실행된다.