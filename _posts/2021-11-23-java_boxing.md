---
title: "Java. 오토박싱(Autoboxing)과 언박싱(Unboxing) 알아보기"
categories:
  - Java
tags:
  - Java
  - 중급
  - 프로그래밍 언어
---

## 🌟 오토박싱과 언박싱이란?

오토박싱이란, Wrapper 클래스의 객체로 변환시키는 것을 말한다. Wrapper 클래스는 기본 타입의 데이터를 객체로 변환할 때 포장하는 것을 말한다. Integer 같은 것들! Integer는 사용하면 알아서 객체로 오토박싱된다.



언박싱은 객체를 기본 타입으로 변환하는 것을 말한다. Integer 같은 경우는 int로 변환된다.



## 🌟 사용법

```java
Integer a = 10;
int b = 20;
int c = a + b; //a는 언박싱 된다
```

따라서 위 코드를 사용하면 자동으로 형변환이 일어난다.



______________________



> 📌 참조 블로그 [개발 흔적 남기기](https://myhappyman.tistory.com/75)

