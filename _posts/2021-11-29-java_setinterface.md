---
title: "Java. Set 인터페이스 알아보기"
categories:
  - Java
tags:
  - Java
  - 중급
  - 프로그래밍 언어
---



Set은 집합을 뜻하고, Set 인터페이스의 클래스들은 대부분 중복되는 원소가 없으며, null은 저장할 수 있고, 인덱스가 없다. 다만 LinkedHashSet은 저장 순서를 유지함!



_______



## 🌟 HashSet이란?

HashSet은 데이터를 정렬하지 않고, 다른 Set의 구현 클래스인 TreeSet은 데이터를 자동으로 정렬해준다. HashSet은 Set의 성질을 그대로 받아 원수가 중복될 수 없으며 저장 순서가 유지되지 않음!



### 사용법

```java
HashSet<String> set = new HashSet<String>();
set.add("영현");
set.add("배고파");

set.remove("배고파");
set.clear();
```

리스트랑 비슷한 듯!



## 🌟 TreeSet이란?

TreeSet은 이진 탐색 트리 구조(레드-블랙 트리)로 이루어져 있다. HashSet보다는 데이터 추가와 삭제에 느리지만, 정렬이나 검색에서는 빠른 편이다.



### 사용법

```java
TreeSet<Integer> set = new TreeSet<Integer>();
set.add(2);
set.add(5);
set.add(10);

System.out.println(set.last()); //최대값 출력
System.out.println(set.first()); //최소값 출력
System.out.println(set.lower(5)); //인자보다 작은 데이터 중에서 가장 큰 값 출력, 없으면  null 반환
System.out.println(set.higher(5)); //인자보다 큰 데이터 중에서 가장 작은 값 출력, 없으면 null 반환
```

추가하고 삭제하는 건 앞부분이랑 똑같고, last나 first, lower 등이 있어서 값을 가져도는 데에 다양하게 쓸 수 있다.
