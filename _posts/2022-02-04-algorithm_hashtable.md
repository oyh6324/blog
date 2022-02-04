---
title: "알고리즘. 해시 테이블(HashTable) 알아보기"
categories:
  - Algorithm
tags:
  - 알고리즘
  - 기초
  - 자료구조
---

## 🌟 해시 테이블이란?

키와 값을 가지고 있는 자료구조다. 해시맵과 비슷한데 해시 테이블은 동기화가 걸려 있어서 Thread-Safe 함! 안전한건 해시 테이블이고, 빠른 건 해시맵이다.



## 🌟 코드

### put과 get

```java
public class Main{
    public static void main(String[] args){
        Map<String,Integer> ht=new Hashtable();
		ht.put("key1", 50);
		ht.put("key2",100);
		ht.put("key2",250);	//같은 키가 들어갈 경우에는?
		System.out.println(ht);
		System.out.println(ht.get("key1"));
		System.out.println(ht.get("key2"));
		System.out.println(ht.get("key3"));	//키가 없을 경우에는?
    }
}
```



### 키 순회

```java
public static void main(String[] args) {
	Map<String,Integer> ht=new Hashtable();
	ht.put("foo",100);
	ht.put("bar",250);
	for(String key:ht.keySet()) {
		System.out.println("{"+key+","+ht.get(key)+"}");
	}
}
```



### 해시 테이블에 해시 테이블 추가

```java
public static void main(String[] args) {
	Map<String,Integer> ht1=new Hashtable();
	ht1.put("key1",9999);
	ht1.put("key2",2020);
		
	Map<String,Integer> ht2=new Hashtable();
	ht2.put("key3",3030);
	ht2.put("key4",8888);
		
	ht2.putAll(ht1);
	System.out.println(ht2);
		
	ht1.put("key5",5555);	//ht1에 데이터 추가
	System.out.println(ht2);
}
```



자세한 건 아래 쪽!

> [REAKWON](https://reakwon.tistory.com/152)

