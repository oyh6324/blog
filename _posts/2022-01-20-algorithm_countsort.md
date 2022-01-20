---
title: "알고리즘. 계수 정렬(Count Sort) 알아보기"
categories:
  - Algorithm
tags:
  - 알고리즘
  - 기초
  - 정렬
---

## 🌟 계수 정렬이란?

앞서 배웠던 정렬은 비교 정렬로 아무리 빨라도 하한 값이 nlogn이었는데, 계수 정렬은 그보다 더 빨리 정렬을 할 수 있다.



계수 정렬 방법!

1. 숫자가 몇 개인지 기록
2. x라는 입력은 x보다 작은 원소의 개수가 i-1라면 정렬 후에 i 자리에 위치해야 함
3. x보다 작은 원소의 개수는 원소의 수를 세서 확인



계수 정렬은 같은 수가 있어도 섞이지 않는 안정 정렬이지만, 메모리가 추가적으로 필요하고 큰 데이터를 정렬할 때 맞지 않다는 단점이 있다.

## 🌟 코드

```java
public static void main(String[] args){
    final int MAX = 5;
    int[] nums = {0, 2, 5, 1, 6, 4, 7};
    int len = nums.length;
    int[] counts = new int[MAX + 1];
    int[] sorted = new int[len];
    
    for(int i=0; i<len; ++i)
        ++counts[nums[i]];
    
    for(int i=1; i<=MAX; ++i)
        counts[i] += counts[i-1];
    
    for(int i=0; i<len; ++i)
        sorted[--counts[nums[i]]] = nums[i];
}
```



## 🌟 시간 복잡도

최선, 평균, 최악 모두 n이다!



> [기내식은수박바](https://soobarkbar.tistory.com/101)

> [IT 언어와 자격증](https://taemtaem-it.tistory.com/entry/91)

