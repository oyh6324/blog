---
title: "Java. 인터페이스(Interface) 알아보기"
categories:
  - Java
tags:
  - Java
  - 기초
  - 프로그래밍 언어
---

## 🌟 인터페이스란?

C# 공부했을 때와 마찬가지로 선언만 해놓고 정의는 자식 클래스에서 하는 게 인터페이스다!



### 인터페이스 요소

- **상수**: 모든 변수는 상수로 변환
- **추상 메소드**: 모든 메소드는 추상 메소드로 구현
- **디폴트 메소드**: 기본 구현을 가졌지만 오버라이딩 가능함
- **정적 메소드**: 인스턴스 생성과 상관없이 인터페이스 타입으로 사용 가능한 메소드
- **private 메소드**: 인터페이스 내부만 사용 가능



## 🌟 사용법

```java
public interface Print{
    void namePrint(String name);
}

public class NamePrint implements Print{
    @Override
    public void namePrint(String name){
        System.out.println(name + "입니다.");
    }
}

public Class Main{
    public static void main(String[] args){
        Print print = new NamePrint();
        print.namePrint("영현");
    }
}
```

인터페이스는 하위 클래스에서 꼭 implements를 사용해줘야 한다.
