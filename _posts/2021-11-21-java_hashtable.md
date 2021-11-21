---
title: "Java. Hashtable 알아보기"
categories:
  - Java
tags:
  - Java
  - 중급
  - 프로그래밍 언어
---

## 🌟 Hashtable이란?

값을 식별하기 위한 고유한 키, 그리고 키가 가진 값으로 이루어진 자료구조다. null 입력이 불가능하고, 값은 중복이 된다.



## 🌟 사용법

```java
Hashtable<Integer, Integer> ht = new Hashtable<Integer, Integer>(); //선언
ht.put(1, 10); //추가
ht.put(2, 20);

ht.remove(1); //삭제

ht.clear(); //전체 삭제
```

추가할 때 같은 키를 추가하면 원래 가지고 있던 키의 값이 업데이트된다.
