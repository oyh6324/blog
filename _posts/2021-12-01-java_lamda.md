---
title: "Java. 람다식 사용하기"
categories:
  - Java
tags:
  - Java
  - 중급
  - 프로그래밍 언어
---



## 🌟 람다식이란?

클래스를 생성하지 않고, 함수의 호출만으로 실행하는 걸 말한다. 함수형 프로그래밍!

그냥 함수를 줄여서 익명으로 사용한다고 생각하면 됨.



## 🌟 사용법

```java
(int x, int y) -> {return x + y;}
str -> {System.out.println(str);} //매개 변수가 2개 이하일 때 괄호 생략
str -> str.length(); //return과 중괄호 생략
```



사용법은 C# 공부했을 때와 똑같다!

____

FunctionalInterface(구현해야 할 메소드가 하나)를 선언한다.

```java
interface Sum{
    public int sum(int a, int b);
}
```



```java
public static void main(String[] args){
    Sum sum1 = (a, b) -> a + b;
}
```

메인에서 sum 메소드를 람다로 구현함!
