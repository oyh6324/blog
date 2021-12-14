---
title: "알고리즘. Recursion(순환)-최대공약수"
categories:
  - Algorithm
tags:
  - 알고리즘
  - 순환
  - 기초
---



## 🌟 유클리드 알고리즘

유클리드 알고리즘은 최대공약수(GCD)를 구하는 알고리즘이다.



## 🌟 최대공약수

```c
int gcd(int a, int b)
{
    if(b==0)
        return a;
    else
        return gcd(b, a%b);
}

int main()
{
    printf("%d", gcd(10, 20));
    
    return 0;
}
```

이렇게 하면 10과 20의 최대공약수인 10이 출력될 것이다.
