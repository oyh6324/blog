---
title: "알고리즘. 삽입 정렬(Insertion Sort) 알아보기"
categories:
  - Algorithm
tags:
  - 알고리즘
  - 기초
  - 정렬
---

## 🌟 삽입 정렬이란?

카드를 정렬하는 방법과 비슷하다.



새로운 카드를 가지고 있던 카드에 올바른 자리를 찾아 삽입! 새로 삽입될 카드의 수만큼 반복하면 전체 카드가 정렬된다.



즉, 앞에서부터 차례대로 졍렬된 배열과 비교하여 새 원소가 알맞은 위치에 삽입되는 것.



이미 정렬되어 있는 데이터에 사용할 때 유용하다. 하지만 크기가 큰 데이터의 경우 알맞지 않다.



## 🌟 코드

```c
# include <stdio.h>
# define MAX_SIZE 5

// 삽입 정렬
void insertion_sort(int list[], int n){
  int i, j, key;

  // 인텍스 0은 이미 정렬된 것으로 볼 수 있다.
  for(i=1; i<n; i++){
    key = list[i]; // 현재 삽입될 숫자인 i번째 정수를 key 변수로 복사

    // 현재 정렬된 배열은 i-1까지이므로 i-1번째부터 역순으로 조사한다.
    // j 값은 음수가 아니어야 되고
    // key 값보다 정렬된 배열에 있는 값이 크면 j번째를 j+1번째로 이동
    for(j=i-1; j>=0 && list[j]>key; j--){
      list[j+1] = list[j]; // 레코드의 오른쪽으로 이동
    }

    list[j+1] = key;
  }
}

void main(){
  int i;
  int n = MAX_SIZE;
  int list[n] = {8, 5, 6, 2, 4};

  // 삽입 정렬 수행
  insertion_sort(list, n);

  // 정렬 결과 출력
  for(i=0; i<n; i++){
    printf("%d\n", list[i]);
  }
}
```



## 🌟 시간 복잡도

최선은 n, 평균은 n^2, 최악도 n^2이다.



> [Heee's Development Blog](https://gmlwjd9405.github.io/2018/05/06/algorithm-insertion-sort.html)

