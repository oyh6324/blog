---
title: "알고리즘. Recusion(순환)-최대값 구하기"
categories:
  - Algorithm
tags:
  - 알고리즘
  - 기초
  - 순환
---



## 🌟 암시적 매개변수와 명시적 매개변수

반복문은 보통 암시적 매개변수를 사용한다. 0부터 n-1까지 반복하라고, 암시적으로 0부터 돌기 때문! 이걸 begin과 end를 정해서 명시적으로 바꾸면 순환이 된다.



## 🌟 최대값 구하기

### 반복문

```c
#include <stdio.h>

int main()
{
    int array[] = {1, 10, 6, 7, 56, 20};
    int max = 0;
    
    for(i = 0; i < sizeof(array) / sizeof(int); i++)
    {
        if(array[i] > max)
            max = array[i];
    }
    
    printf("%d", max);
    
    return 0;
}
```

이렇게 하면 array의 0부터 끝까지 돌아 56을 찾아낼 것이다!



### 순환

```c
#include <stdio.h>

int max(int list[], int low, int high) { //순환
	int middle;
	int max_left, max_right;

	if (low == high)
		return list[low]; //절반으로 나눈 끝에 low=high이면 자기 자신 반환

	middle = (low + high) / 2;

	max_left = max(list, low, middle); //중앙에서 왼쪽 부분의 최대값
	max_right = max(list, middle + 1, high); //중앙에서 오른쪽 부분의 최대값

	return max_left >= max_right ? max_left : max_right; //조건 연산자 사용하여 왼쪽의 최대값과 오른쪽의 최대값을 비교하여 더 큰것을 반환한다.
	
}

int main(void)
{
	int list[] = { 10, 20, 100, 4, 5, 45, 3, 99, 11, 22 };
	printf("가장 큰 수는 %d\n", max(list, 0, 9)); // 100
	printf("가장 큰 수는 %d\n", max(list, 5, 9)); // 99
	printf("가장 큰 수는 %d\n", max(list, 3, 6)); // 45
}
```



배열을 반으로 나눠서 순차탐색을 함!



> [조이의 개발새발 블로그](https://devyul.tistory.com/entry/C-%EC%88%9C%ED%99%98%EC%9D%84-%EC%9D%B4%EC%9A%A9%ED%95%9C-%EB%B0%B0%EC%97%B4%EC%97%90%EC%84%9C-%EC%B5%9C%EB%8C%80%EA%B0%92-%EC%B0%BE%EA%B8%B0)

