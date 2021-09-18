---
title: "Unity. C# 전처리기 지시어 알아보기"
categories:
  - Unity
tags:
  - 기초
  - Unity
  - C#
---

## 🌟 전처리기 지시어란?

컴파일 되기 바로 전에 전처리 작업을 진행 하는데 그때 사용할 수 있는 게 전처리기 지시어다.

## 🌟 지시어 종류

- **define**: 기호를 정의한다.
- **undef**: 기호 정의를 해제한다.
- **if**: 조건을 만족하면 아래 코드를 실행한다.
- **else**: if문의 조건을 만족하지 않는다면 아래 코드를 실행한다.
- **elif**: 위와 동일
- **region**: 코드 블록 지정한다.
- **endregion**: 블록의 끝을 표시한다.

## 🌟 유니티에서 지정한 플랫폼 매크로

![image-center]({{ site.url }}{{ site.baseurl }}/assets/images/unity/unity.preprocessor.jpg){: .align-center}
_유니티 공식 문서_

플랫폼 별로 컴파일 코드를 바꿀 수 있다!

## 🌟 사용법

```c#
#if UNITY_EDITOR
      Debug.Log("Unity Editor");
#endif

#if UNITY_IOS
      Debug.Log("IOS");
#endif
```

이런 식으로 사용할 수 있다. define은 많이 사용해 봤으니 넘어감! 다른 지시어는 필요할 때 찾아봐야지~