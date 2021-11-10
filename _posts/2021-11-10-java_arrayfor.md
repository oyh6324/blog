---
title: "Java. 향상된 for문으로 배열 출력하기"
categories:
  - Java
tags:
  - Java
  - 기초
  - 프로그래밍 언어
---

## 🌟 향상된 for문이란?

원래 for문의 형태는

```java
for(int i=0; i<Num; i++) {...}
```

이런 식이지만, 배열을 읽기만 할 때 좀 더 편하게 읽으라고 향상된 for문이 나왔다.



```java
for(배열 자료형 변수명: 배열명) {...}
```

이렇게 하면 원하는 배열이 내가 지정한 변수에 들어가서 for문이 돌 때마다 값이 바뀜!

## 사용법

```java
public static void main(String[] args) {
    String[] strArray = {"영현", "공부하자", "놀면", "안돼!"};
    
    for(String str:strArray){ //배열 출력
        System.out.println(str);
    }
}

```

간단!
