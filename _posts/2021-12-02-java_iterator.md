---
title: "Java. Iterator 알아보기"
categories:
  - Java
tags:
  - Java
  - 중급
  - 프로그래밍 언어
---



## 🌟 Iterator란?

컬렉션에 저장되어 있는 데이터를 읽어오는 방법이다. 반복자라고 불리며, 한 반향으로만 데이터를 읽을 수 있다. 중간에 값을 변경하거나 추가하는 건 불가능하고, 삭제하는 건 할 수 있다.



그리고 데이터가 많을 때 속도가 느려짐!



## 🌟 사용법

```java
ArrayList<Integer> list = new ArrayList<Integer>();
list.add(10);
list.add(20);
list.add(30);

Iterator<Integer> iter = list.iterator();

while(iter.hasNext()){
    System.out.println(iter.next());
    iter.remove();
}
```

`hasNext`는 다음 값이 들어 있는지 bool로 반환하고, `next` 다음 값을 가져온다. 그리고 `remove`는 next를 해서 가져온 값을 해당 배열에서 삭제한다.
