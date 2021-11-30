---
title: "Java. Map 인터페이스 알아보기"
categories:
  - Java
tags:
  - Java
  - 중급
  - 프로그래밍 언어
---





구현한 하위 클래스에는 HashMap, LinkedHashMap, TreeMap이 있고 HashMap은 했으니까 LinkedMap이랑 TreeMap만 알아보겠음!

___

## 🌟 LinkedHashMap

HashMap을 상속받았고, HashMap과는 달리 입력한 순서대로 데이터를 저장한다.



### 사용법

```java
Map<String, Integer> map = new LinkedHashMap<String, Integer>();
map.add("영현", 1);
map.add("길동", 2);
```



사용법은 동일함



## 🌟 TreeMap

트리가 그렇듯 정렬을 지원하고 데이터 가져오는 속도가 다른 클래스보다 빠르다. HashMap과는 달리 오름차순으로 key를 저장함!



### 사용법

```java
Map<String, Integer> map = new TreeMap<String, Integer>();
map.add("영현", 1);
map.add("길동", 2);
```



똑같음!
