---
title: "알고리즘. 10진수를 2진수로 만들기"
categories:
  - Algorithm
tags:
  - 알고리즘
  - 기초
---



## 🌟 10진수를 2진수로 만드는 방법

![image-center]({{ site.url }}{{ site.baseurl }}/assets/images/algorithm/algorithm.binary.jpg){: .align-center}



이런 방식!! 알고 있겠지만.



## 🌟 재귀 사용

```c
void binary(unsigned n){
    if(n<2)
        printf("%d", n);
    else{
        binary(n/2);
        printf("%d", n%2);
    }
}
```



가장 간단하 방법!



나머지는



> [SHA Computing](https://shacoding.com/2020/01/10/c%EC%96%B8%EC%96%B4-10%EC%A7%84%EC%88%98%EB%A5%BC-2%EC%A7%84%EC%88%98%EB%A1%9C-%EB%B3%80%ED%99%98%ED%95%98%EC%9E%90-%EC%84%B8-%EA%B0%80%EC%A7%80-%EB%B0%A9%EB%B2%95-%EC%A0%9C%EA%B3%B5/)

여기서 확인!
