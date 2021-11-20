---
title: "Java. 해쉬 코드(Hash Code) 알아보기"
categories:
  - Java
tags:
  - Java
  - 중급
  - 프로그래밍 언어
---

## 🌟 해쉬 코드란?

해쉬 코드란 객체의 유니크한 저장 주소를 말한다. 메모리에 생성된 객체의 주소를 정수로 변환하여 반환한다.

## 🌟 사용법

```java
public class Main{
    public static void main(String[] args){
        Student student1 = new Student();
        Student student2 = new Student();
        
        System.out.println(student1.hashCode());
        System.out.ptinyln(student2.hashCode());
    }
}
```

Student 클래스가 있다고 가정하고, 두 객체를 만들어서 해쉬 코드를 확인하면 대충 서로 다른 정수값이 출력될 것이다. 그게 메모리 주소를 정수로 변환한 해쉬 코드다.



해쉬 코드를 사용할 때 equals()와 함께 재정의를 하는데, 그건 다음에~
