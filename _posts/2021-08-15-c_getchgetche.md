---
title: "C언어. 문자 입력하기 (3) getch와 getche"
categories:
  - C
tags:
  - C언어
  - 프로그래밍 언어
  - 문자 입출력 함수
---

##  🌟 getch와 getche란?

입력 버퍼를 사용하지 않는 문자열 입력 함수다. 입력 버퍼를 사용하는 `getchar()`는 ‘/n’을 만날 때까지 버퍼에 넣어두어서 언제든지 실수로 입력한 문자를 백스페이스로 삭제할 수 있다.

`getch()`는 키보드로 입력한 순간 바로 값을 가져가버려서, 잘못 입력한 걸 지울 수 없다.

`getche()`는 `getch()`와 비슷하지만 출력문이 없어도 내가 출력한 걸 바로 보여준다는 차이점이 있다.

## 🌟 사용법

### getch

```c
int main()
{
	char str;
	str = getch();
	printf("%c", str);

	return 0;
}
```

`getch()`는 입력한 값을 보여주지 않으므로 바로 printf로 가서 내가 입력한 값이 하나만 보일 것이다.

### getche

```c
int main()
{
	char str;
	str = getche();

	return 0;
}
```

`getche()`는 입력한 값을 보여주므로 printf가 없어도 내가 무엇을 입력했는지 알 수 있다.