---
title: "C언어. #error와 #line 매크로 알아보기"
categories:
  - C
tags:
  - C언어
  - 프로그래밍 언어
  - 중급
  - 매크로
---

## 🌟 #error

#error는 보통 조건문과 같이 사용되고, #error가 출력되면 프로그램을 작동을 중지한다.



```c
#ifndef UNICODE
#error 유니코드가 없습니다. 실행을 중지합니다.
#else

int main()
{
    printf("실행 완료");
    
    return 0;
}
#endif
```

 컴퓨터가 유니코드 매크로를 지원해준다면 메인이 실행될 것이고, 지원하지 않는다면 #error문을 출력하고 프로그램은 중지될 것이다.



이렇게 #error는 시스템이 중지되길 바라는 조건과 함께 상단에 주로 쓰임!





## 🌟 #line

#line을 쓰면 현재 라인과 파일 이름을 수정할 수 있다.



```c
#inculde <stdio.h>

int main()
{
#line 1 "FileName"
    
    int a = 10;
    int b = 20;
    
    printf("%d, %s", __LINE__, __FILE__); //5, FileName을 출력함
        
    return 0;
}
```

원래라면 소스 첫 줄부터 라인을 세겠지만, #line으로 재정의 되어 메인 안에서부터 다시 줄을 세기 때문에 5와 내가 지정한 파일 이름이 나올 것이다.



간단!



________________________________________

> 참고한 블로그 [Programog](https://m.blog.naver.com/PostView.naver?isHttpsRedirect=true&blogId=skout123&logNo=50130054161)

