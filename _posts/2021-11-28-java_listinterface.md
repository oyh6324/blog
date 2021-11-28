---
title: "Java. List 인터페이스 알아보기"
categories:
  - Java
tags:
  - Java
  - 기초
  - 프로그래밍 언어
---



ArrayList는 저번에 했으니 패스! Stack이랑 Queue도 패스! Vector와 LinkedList에 대해 알아볼 거임.



_______



## 🌟 Vector

Vector 클래스는 어떤 타입의 객체라도 저장할 수 있으며, 가변 크기의 배열로 ArrayList와 비슷하다.



Vector는 멀티쓰레드 상태에서 리소스에 대한 동기화가 필요할 때 주로 사용하고 보통은 ArrayList를 사용한다. 잘 쓰지 않는 클래스! 



### 사용법

```java
Vector v = new Vector(); //생성
v.add(1); //추가
v.add("영현");
v.add(new Integer(2));

System.out.println(v.get(0)); //0번째 데이터 출력
System.out.println(v.size()); //vector의 크기 출력
```



## 🌟 LinkedList

LinkedList는 각 노드? 데이터들이 다음 노드와 연결되어 있다. 예전에 C++ 할 때 공부했었는데...아무튼 대충 이런 느낌!

![image-center]({{ site.url }}{{ site.baseurl }}/assets/images/java/java.linkedList.jpg){: .align-center}

다음 노드에 대한 주소값을 가지고 있어서 각 노드는 다음 노드의 위치를 알고 있고, 연결된 것이다. 위 그림은 한쪽 방향으로밖에 안 흘러가지만, 자바는 더블링크드리스트로, 이전 노드의 위치도 알고 있어서 양쪽으로 흘러갈 수 있다.



### 사용법

```java
LinkedList <Integer> list = new LinkedList<Integer>();

list.add(1);
list.add(10);
list.add(5);
```



다른 클래스와 같이 add와 get으로 값을 추가하고 얻으면 된다. 



링크드리스트는 데이터의 삽입과 삭제에 빠른 편이고, ArrayList는 위치, index를 통해 데이터를 부르는 게 빠른 편이다. 상황에 맞게 사용!
