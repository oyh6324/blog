---
title: "Java. 상속 알아보기"
categories:
  - Java
tags:
  - Java
  - 기초
  - 프로그래밍 언어
---

## 🌟 자바의 상속

다른 언어와 마찬가지로 부모 클래스와 자식 클래스를 만들 수 있다. 단, 자바는 `extends`라는 키워드를 덧붙여야 함!



## 🌟 사용법

```java
Class PClass{
    public void POutput() {
        System.out.println("부모입니다.");
    }
}

Class CClass extends PClass{ //상속받음
    public void COutput(){
        System.out.println("자식입니다.");
    }
}
```

이렇게!
