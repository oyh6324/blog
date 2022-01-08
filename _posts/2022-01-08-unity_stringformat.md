---
title: "Unity. C# string.Format과 문자열 보간 사용하기"
categories:
  - Unity
tags:
  - Unity
  - 기초
  - C#
---

## 🌟 string.Format 사용하기

Format 메소드를 사용하면 일반적으로 문자열을 출력할 때와 달리 간단한 조건을 중간에 넣어 문자열을 출력할 수 있다.



### 자리수 설정

```c#
int num = 10000;
Debug.Log(string.Format("{0:#,###}", num));
```

이렇게 하면 실제 돈 단위처럼 10,000 이렇게 출력됨!



```c#
double num = 100.1234567;
Debug.Log(string.Format("{0:0.###}", num));
```

이건 소수점을 세 자리까지 표현한다는 것! 여기에 # 대신 0을 넣으면 소수점 세 자리까지 만약 비었을 때 0으로 채워준다.



### 반올림

```c#
double num = 100.1234567;
Debug.Log(string.Format("{0:###}", num));
```

소수점 세 자리까지 나오고 반올림 된다.



이외에도 지수 표현, 전화번호 표현 기타 등등 많음!



## 🌟 문자열 보간 $ 

문자열 보간은 문자열 앞에 $를 넣어서 사용되고, 중간에 코드를 넣을 수 있게 해준다.



```c#
int num = 10;
int num2 = 20;
Debug.Log($"{num + num2}");
```



이런 느낌!
