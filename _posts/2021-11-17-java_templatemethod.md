---
title: "Java. 디자인패턴-템플릿 메소드(Template Method)"
categories:
  - Java
tags:
  - Java
  - 디자인 패턴
  - 프로그래밍 언어
---

## 🌟 템플릿 메소드란?

추상 메소드나 구현된 메소드를 활용해서 전체 흐름을 정리하는 메소드를 말한다. 프레임워크에서 많이 사용됨!



## 🌟 사용법

버거 만드는 예제!

### BuggerTemplate

```java
public abstract class BuggerTemplate{
    public abstract void patty(); //추상 메소드
    
    private void buns(){
        System.out.println("빵");
    }
    
    public final void MakeBugger(){ //override 방지
        buns();
        patty();
        buns();
        System.out.println("햄버거를 만들었습니다.");
    }
}
```

자식 클래스에서 구현이 필요한 것은 추상 메소드로 남겨둔다!



### BulgogiBugger

```java
public class BulgogiBugger extends BuggerTemplate{
    @Override
    public void patty(){
        System.out.println("불고기 패티");
    }
}
```



### ShrimpBugger

```java
public class ShrimpBugger extends BuggerTemplate{
    @Override
    public void patty(){
        System.out.println("새우 패티");
    }
}
```



### Main

```java
public class MakeBuggers{
    public static void main(String[] args){
        BuggerTemplate bulgogiBugger = new BulgogiBugger();
        bulgogiBugger.MakeBugger();
        
        BuggerTemplate shrimpBugger = new ShrimpBugger();
        shrimpBugger.MakeBugger();
    }
}
```



이렇게 하면 이제

`빵`

`불고기 패티`

`빵`



`빵`

`새우 패티`

`빵`



이렇게 출력될 것이다!
