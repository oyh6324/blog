---
title: "Java. 제네릭 프로그래밍 알아보기"
categories:
  - Java
tags:
  - Java
  - 중급
  - 프로그래밍 언어
---

## 🌟 제네릭 프로그래밍이란?

제네릭 프로그래밍은 앞에 C#을 공부했을 때와 똑같이, 변수의 선언이나 메소드의 매개 변수를 여러 자료형으로 변환될 수 있게 하는 방식으로 제네릭 클래스나 제네릭 메소드가 이에 해당된다.



## 🌟 사용법

```java
public class GenericClass <T>
{ ... }
```

 

보통 이런 식으로 많이 사용하지만 `<>` 안의 글자는 프로그래머가 지정할 수 있기에 여러 상황에 따라 다른 글자로 바꿀 수 있다.



| 표시 | 내용    |
| ---- | ------- |
| <T>  | Type    |
| <E>  | Element |
| <K>  | Key     |
| <V>  | Value   |
| <N>  | Number  |



대부분 이렇게 사용함!

________________



자바의 제네릭도 C#과 비슷하게 사용한다.



```java
public class TestClass <T>{
    private T t;
    
    public void set(T t){
        this.t = t;
    }
    public T getT(){
        return t;
    }
}

public class Main{
    public static void main(String[] args){
        TestClass<String> test = new TestClass<>();
        
        test.set("영현");
        
        System.out.println(test.getT());
    }
}
```

이렇게 하면 `영현`을 출력할 것이다. 더 다양하게 사용하기도 하던데...그건 언젠가 해봐야지...



{: .notice--primary}

☝ 주의할 점은 static을 사용했을 때는 제네릭을 쓸 수 없다. 왜냐면 static은 생성될 때 이미 타입이 결정되기 때문!
