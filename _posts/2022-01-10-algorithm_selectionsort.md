---
title: "알고리즘. 선택 정렬(Selection Sort) 알아보기"
categories:
  - Algorithm
tags:
  - 알고리즘
  - 기초
  - 정렬
---

## 🌟 선택 정렬이란?

제자리 정렬 알고리즘의 하나로, 제자리 정렬 알고리즘은 추가 메모리를 요구하지 않는 정렬 방법이다.



선택 정렬은 배열에서 최솟값을 찾고, 그 값을 맨 앞에 놓인 값과 교체하고 교체한 원소를 제외한 뒤에 원소들을 계속 반복하며 정렬하는 방법이다.



이동 횟수가 미리 결정된다는 장점이 있지만, 안정성이 없다는 단점이 있다.



## 🌟 코드

```c
# include <stdio.h>
# define SWAP(x, y, temp) ( (temp)=(x), (x)=(y), (y)=(temp) )
# define MAX_SIZE 5

// 선택 정렬
void selection_sort(int list[], int n){
  int i, j, least, temp;

  // 마지막 숫자는 자동으로 정렬되기 때문에 (숫자 개수-1) 만큼 반복한다.
  for(i=0; i<n-1; i++){
    least = i;

    // 최솟값을 탐색한다.
    for(j=i+1; j<n; j++){
      if(list[j]<list[least])
        least = j;
    }

    // 최솟값이 자기 자신이면 자료 이동을 하지 않는다.
    if(i != least){
        SWAP(list[i], list[least], temp);
    }
  }
}

void main(){
  int i;
  int n = MAX_SIZE;
  int list[n] = {9, 6, 7, 3, 5};

  // 선택 정렬 수행
  selection_sort(list, n);

  // 정렬 결과 출력
  for(i=0; i<n; i++){
    printf("%d\n", list[i]);
  }
}
```



## 🌟 시간 복잡도

최선, 평균, 최악이 모두 n^2으로 같다.



> [Heee's Development Blog](https://gmlwjd9405.github.io/2018/05/06/algorithm-selection-sort.html)

