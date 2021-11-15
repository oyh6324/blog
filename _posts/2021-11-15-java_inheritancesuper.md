---
title: "Java. 상속의 super 키워드 알아보기"
categories:
  - Java
tags:
  - Java
  - 기초
  - 프로그래밍 언어
---

## 🌟 super

자식 클래스에서 부모 클래스의 멤버에 접근할 때 사용할 수 있는 키워드가 바로 super 키워드다.

## 🌟 사용법

```java
class Customer{
    public String name;
}

class VipCustomer extends Customer{
    public VipCustomer(){
        System.out.println("Vip: "+super.name);
    }
}
```

Customer를 상속 받은 VipCustomer가 생성될 때 부모의 멤버 변수인 name을 가져온다.

