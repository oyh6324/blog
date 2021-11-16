---
title: "Java. instanceof로 객체 타입 알아보기"
categories:
  - Java
tags:
  - Java
  - 기초
  - 프로그래밍 언어
---

## 🌟 instanceof란?

객체의 타입을 알 수 있는 연산자다!



## 🌟 사용법

```java
Animal animal = new Animal();
if(animal instanceof Animal){
    System.out.println("Animal 클래스입니다.");
}
```

Animal이라는 클래스가 있다고 가정했을 때, Animal 객체를 생성한 후 instanceof로 확인하면 if문 안의 출력문이 나올 것이다. instanceof는 확인하고자 하는 클래스가 맞다면 true를, 아니라면 false를 반환한다.
