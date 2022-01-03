---
title: "알고리즘. Backtracking 알아보기"
categories:
  - Algorithm
tags:
  - 알고리즘
  - 기초
---



## 🌟 백트래킹

해를 찾아가는데 그 경로에 해가 없으면 다시 되돌아가는 알고리즘이다. 이전 포스트의 N Queens가 여기에 해당됨



## 🌟 코드

```java
#include <stdio.h>
#include <stdlib.h>

int count = 0;
int n;
int board[15];

// 유망한지 판단하는 함수
int promising(int cdx) {

	// 같은 열이면 안되고, 대각선상에 있어서도 안 된다.
	for (int i = 0; i < cdx; i++) {
		if (board[cdx] == board[i] || cdx - i == abs(board[cdx] - board[i])) {
			return 0;
		}
	}
	return 1;
}

// nqueen 알고리즘 수행
void nqueen(int cdx) {

	// cdx가 마지막 행까지 수행하고 여기까지 오면, 찾기 완료
	if (cdx == n) {
		count++;
		return;
	}

	for (int i = 0; i < n; i++) {
		board[cdx] = i; // cdx번째 행, i번째 열에 queen을 놓아본다.	
		// 이후 그 행에 둔 것에 대한 유망성을 판단한다.
		if (promising(cdx)) { // 그 자리에 두어도 괜찮았다면,
			nqueen(cdx + 1); // 그 다음 행에 대해 퀸을 놓는 것을 해 본다.
		}
	}
}

int main() {

	scanf("%d", &n);
	nqueen(0);
	printf("%d", count);

}
```





> [ChanBLOG](https://chanhuiseok.github.io/posts/baek-1/)
