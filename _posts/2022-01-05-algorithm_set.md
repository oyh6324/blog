---
title: "알고리즘. 멱집합 알고리즘"
categories:
  - Algorithm
tags:
  - 알고리즘
  - 기초
---



## 🌟 멱집합이란?

멱집합은 한 집합의 모든 부분 집합을 말한다. 원소가 a, b, c인 집합이 있다면 이 집합의 부분 집합은 `a, b, c, ab, bc, ca, abc` 그리고 공집합 해서 총 8개! 2^집합의 원소 개수이 성립된다.



## 🌟 코드

```java
private static char data[] = {'a','b','c','d','e','f'};
private static int n = data.length;
private static boolean[] include = new boolean[n];
​
public static void powerSet(int k) {
  if (k == n) {
    for (int i = 0; i < n; i++)
      if (include[i])
        System.out.print(data[i] + " ");
    System.out.println();
    return;
  }
  include[k] = false;
  powerSet(k + 1);
  include[k] = true;
  powerSet(k + 1);
}
```





> [개발자의 기록습관](https://ict-nroo.tistory.com/51)

