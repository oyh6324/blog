---
title: "Java. Stream 알아보기"
categories:
  - Java
tags:
  - Java
  - 중급
  - 프로그래밍 언어
---



## 🌟 Stream이란?

Iterator과 비슷한 역할을 하는데, 람다식으로 처리를 해서 좀 더 간결한 반복자다.



자료의 대상과 관계 없이 동일한 연산을 수행하고, 한번 사용한 스트림은 재사용이 안되며, 기존 자료를 변경할 수 없다. 그리고 중간 연산과 최종 연산으로 구분한다.

## 🌟 사용법

```java
String[] array = {"영현", "공부", "하자"};
Stream<String> s = Arrays.stream(array);
s.forEach(str -> System.out.print(str + ","));
```

이렇게 하면 `영현, 공부, 하자`를 출력할 것이다.

