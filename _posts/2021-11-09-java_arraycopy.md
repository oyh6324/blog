---
title: "Java. 배열 복사하기"
categories:
  - Java
tags:
  - Java
  - 기초
  - 프로그래밍 언어
---

## 🌟 System.arrayCopy

byt[] 형태의 데이터를 다룰 때 사용한다. 제목처럼 배열 복사하고 붙여넣기에 쓸 수 있음!



```java
System.arraycopy(src, srcPos, dest, destPos, length);
```

- **src**: 배열 이름
- **srcPos**: 배열의 읽어올 첫 번째 위치
- **dest**: 복사 받을 배열 이름
- **destPos**: 복사 받을 배열의 첫 번째 위치
- **length**: src에서 dest로 복사할 개수



## 사용법

```java
public static void main(String[] args) {
    int[] araay1 = new int[10];
    int[] array2 = new int[10];
    
    //array1에 데이터 넣기
    
    System.arraycopy(a, 0, b, 0, a.length);
    
    }
```



array1에 원하는 데이터를 넣고 `System.arraycopy(a, 0, b, 0, a.length);`를 사용하면 원하는 데이터가 array2에 들어감!
