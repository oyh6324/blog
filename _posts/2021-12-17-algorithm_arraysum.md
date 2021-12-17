---
title: "알고리즘. 배열의 합 구하기"
categories:
  - Algorithm
tags:
  - 알고리즘
  - 기초
---



## 🌟 코드

```c
#include <stdio.h>
int sum_array(int *array, int num);
int main()
{    
    int array[10] = { 1, 2, 3, 4, 10, 6, 7, 8, 9, 10 };
    int sum;
    sum = sum_array(array, 10);
    printf("Sum of the array is %d\n", sum);
    return 0;
}
int sum_array(int *array, int num)
{    
    int i, sum = 0;
    for (i = 0; i < num; i++)
        sum += array[i];
    return (sum);
}
```

간단!

