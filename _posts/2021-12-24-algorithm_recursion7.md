---
title: "알고리즘. Recusion(순환)-N Queens Problem"
categories:
  - Algorithm
tags:
  - 알고리즘
  - 기초
  - 순환
---



## 🌟 N Queens Problem

n개의 말을 두는데 그 말의 대각선, 행, 열에 다른 말들이 있으면 안되는 알고리즘이다!



## 🌟 코드

```java
public class NQueensProblem {
  private final static int N = 8;
  private static int[] cols = new int[N + 1];

  public static void main(String[] args) {
    queens(0);
  }

  private static boolean queens(int level) {
    if (!promising(level))
      return false;
    else if (level == N) {
      for (int i = 1; i <= N; i++)
        System.out.println("(" + i + ", " + cols[i] + ")");
      return true;
    }
    for (int i = 1; i <= N; i++) {
      cols[level + 1] = i;
      if (queens(level + 1))
        return true;
    }
    return false;
  }

  private static boolean promising(int level) {
    for (int i = 1; i < level; i++) {
      if (cols[i] == cols[level])
        return false;
      else if ((level - i) == Math.abs(cols[level] - cols[i]))
        return false;
    }
    return true;
  }
}
```





> [개발자의 기록 습관](https://ict-nroo.tistory.com/50)

