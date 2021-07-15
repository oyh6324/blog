---
title: "C언어. 문자 입력하기(1) - fgets와 fputs"
categories:
  - C
tags:
  - C
  - 프로그래밍 언어
  - 문자 입력 방법
---

## fgets와 fputs

키보드 또는 파일로부터 문자열을 입력 받고 출력할 수 있는 파일 입출력 함수다. 

fgets의 원형은 `char* fgets(char* s, int n, FILE* stream)`이고 각각 받은 문자열을 저장할 char 배열 포인터, 몇개의 문자를 받을 건지 결정하는 int 정수, 문자열을 읽을 스트림의 FILE 객체를 가리키는 포인터다. 표준 입력일 경우 stdin/out을 사용하면 됨! 

fputs는 `int fputs(const char* s, FILE* stream)`으로 설명은 int 인자가 없는 fgets와 동일하다.

## 표준 입력

```c
int max_size = 50;
char* c;
fgets(c, max_size, stdin);
```

이렇게 사용하면 char 포인터에 원하는 문자열을 50까지 입력할 수 있다. fgets의 장점은 공백도 넣을 수 있다는 것이다.

```c
char c[] = "문자열 출력하기";
fputs(c, stdout);
```

이렇게 하면 화면에 `"문자열 출력하기"`가 뜰 것이다. 

파일 입출력은 다음에 알아보겠음!