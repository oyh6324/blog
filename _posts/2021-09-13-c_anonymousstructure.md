---
title: "C언어. 익명 구조체 알아보기"
categories:
  - C
tags:
  - C언어
  - 프로그래밍 언어
  - 중급
---

## 🌟 익명 구조체란?

보통 구조체는 `struct Person...`이런 식으로 이름을 지정해서 사용하지만, 이름을 정하지 않아도 되는 구조체가 있다. 익명 구조체는 typedef로 정의하면서 이름 대신 별칭으로 구분할 수 있게 한다.

## 🌟 사용법

```c
typedef struct {
	char name[10];
	int price;
} Book; //구조체 별칭

int main()
{
Book book1;

strcpy(book1.name, "별주부전");
book1.price = 10000;

return 0;
}
```

별 차이는 없는 것 같지만 단어 하나를 덜 쓰니까 편한 것 같기도...!