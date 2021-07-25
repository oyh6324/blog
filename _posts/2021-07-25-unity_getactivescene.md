---
title: "Unity. GetActiveScene()로 현재 씬 확인하기"
categories:
  - Unity
tags:
  - 기초
  - Unity
---

## GetActiveScene()

현재 씬이 무슨 씬인지 궁금할 때는 SceneManager.GetActiveScene를 사용하면 알 수 있다.

## 사용법

```c#
string sceneName = SceneManager.GetActiveScene().name; //현재 씬의 이름
int sceneNum = SceneManager.GetActiveScene().buildIndex; //현재 씬의 인덱스
```

위 두가지 정보로 현재 씬을 파악할 수 있다. 인덱스는 바뀔 수도 있으니 이름으로 찾는 게 나음!