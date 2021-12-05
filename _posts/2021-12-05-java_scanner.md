---
title: "Java. Scanner로 입력하기"
categories:
  - Java
tags:
  - Java
  - 기초
  - 프로그래밍 언어
---



## 🌟 Scanner란?

입력을 받을 수 있게 하는 클래스다. 많이 사용 됨!



## 🌟 사용법

```java
import java.util.Scanner;

public class Main{
    public static void main(String[] args){
        Scanner s = new Scanner(System.in); //Scanner 생성
        
        int i = s.nextInt(); //int 입력
        float f = s.nextFloat(); //float 입력
        String str = s.next(); //String 입력 
    }
}
```

여기서 str을 nextLine으로 받으면 개행을 기준으로 해서 한 줄을 읽을 수 있다. 원래는 공백을 기준으로 함!
