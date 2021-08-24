---
title: "C언어. 문자열 함수 알아보기"
categories:
  - C
tags:
  - C언어
  - 프로그래밍 언어
  - 기초
---

- **strlen()**: 문자열의 길이 알려줌
- **strcat()**: `strcat(str1, str2)` str1에 str2 내용을 붙여줌
- **strcmp()**: `strcmp("A", "A")` 글을 비교함. 같으면 0, 앞의 아스키 코드가 크면 1 뒤가 크면 -1을 반환함
- **strcpy()**: `strcpy(str1, str2, 5)` 5글자만큼 str2를 str1에 복붙함
- **strchr()**: `strchr("Hello", 'e')` ello를 출력함
- **strpbrk()**: `strpbrk("Hello", "abcde")` 먼저 찾아지는 부분부터 반환함. ello를 출력!
- **strrchr()**: `strrchr(str1, 'a')` str1의 끝에서 a를 찾아냄. 끝 글자가 banana라면 anana를 출력!
- **strstr()**: `strstr("world", "wor")` 단어를 찾아냄. world 반환