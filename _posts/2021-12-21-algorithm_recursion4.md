---
title: "알고리즘. Recusion(순환)-이진 탐색"
categories:
  - Algorithm
tags:
  - 알고리즘
  - 기초
  - 순환
---



## 🌟 이진 탐색

이진 탐색은 배열에서 원하는 값을 찾아내는 알고리즘 중 하나다.

방법은 다음과 같다.

1. 배열의 중간값과 x(찾는 값)을 비교한다.
2. 중간값보다 x가 작으면 배열의 왼쪽으로, 크면 오른쪽으로 가서 다시 중간값을 찾는다.
3. 반복

## 🌟 최대값 구하기

```c
#include <stdio.h>

int BSearchRecursive(int arr[], int target, int low, int high) {
    if (low > high)
        return -1;

    int mid = (low + high) / 2;
    if (arr[mid] == target)
        return mid;
    else if (arr[mid] > target)
        return BSearchRecursive(arr, target, low, mid-1);
    else
        return BSearchRecursive(arr, target, mid+1, high);
}

int main()
{
    int arr[] = {10, 12, 20, 25, 30, 56, 70};
    
    printf("%d", BSearchRecursive(arr, 56, 0, 6));
    
    return 0;
}
```

> # 참고 블로그! [Jihun's Development Blog](https://cjh5414.github.io/binary-search/)

