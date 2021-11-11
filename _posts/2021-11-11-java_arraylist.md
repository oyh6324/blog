---
title: "Java. ArrayList 알아보기"
categories:
  - Java
tags:
  - Java
  - 기초
  - 프로그래밍 언어
---

## 🌟 ArrayList란?

자바에서 제공되는 객체 배열이 구현된 클래스다. List 인터페이스를 상속받았고, 크기가 가변적으로 변한다. C#에서 쓰는 List랑 비슷하다고 보면 될 듯!

## 🌟 사용법

```java
ArrayList<String> list = new ArrayList<String>(); //선언
list.add("영현"); //추가
list.add(0, "abc"); //0 자리에 추가
list.remove(0); //0 삭제
```

써보니 일반 List랑 다를 게 없다. 그냥 똑같은듯!



리스트를 다 지우고 싶을 때는 list.clear()를 하면 된다.
