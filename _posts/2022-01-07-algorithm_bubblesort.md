---
title: "알고리즘. 버블 정렬(Bubble Sort) 알고리즘 알아보기"
categories:
  - Algorithm
tags:
  - 알고리즘
  - 기초
  - 정렬
---

## 🌟 버블 정렬이란?

인접한 두 원소를 비교하여 정렬하는 알고리즘이다.



간단한 예시를 들어 보겠다. 배열 `1, 5, 10, 3, 6`있다고 가정하면, 1과 5를 비교하고, 그 다음에 5와 10을 비교하고, 10과 3을 비교해 3이 더 작으므로 앞으로 교환하여 계속 반복한다. 그래서 배열을 한 번 돌고 두 번 돌고 반복함!



매우 간단하지만 작업이 길어서 잘 쓰이지 않는다. 



## 🌟 코드

```c
# include <stdio.h>
# define MAX_SIZE 5

// 버블 정렬
void bubble_sort(int list[], int n){
  int i, j, temp;

  for(i=n-1; i>0; i--){
    // 0 ~ (i-1)까지 반복
    for(j=0; j<i; j++){
      // j번째와 j+1번째의 요소가 크기 순이 아니면 교환
      if(list[j]<list[j+1]){
        temp = list[j];
        list[j] = list[j+1];
        list[j+1] = temp;
      }
    }
  }
}

void main(){
  int i;
  int n = MAX_SIZE;
  int list[n] = {7, 4, 5, 1, 3};

  // 버블 정렬 수행
  bubble_sort(list, n);

  // 정렬 결과 출력
  for(i=0; i<n; i++){
    printf("%d\n", list[i]);
  }
}
```



시간복잡도나 그런 건 다음에...



> [Heee's Development Blog](https://gmlwjd9405.github.io/2018/05/06/algorithm-bubble-sort.html)

