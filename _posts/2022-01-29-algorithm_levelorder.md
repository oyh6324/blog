---
title: "알고리즘. 이진 트리의 Level Order 순회 알아보기"
categories:
  - Algorithm
tags:
  - 알고리즘
  - 이진 트리
---

## 🌟 Level Order 순회란?

이것도 앞에서 알아본 이진 트리의 순회 방법 중 하나로, 트리의 레벨 순서대로 순회하는 순회 방법이다.



레벨 1부터 차례대로 돌아서, 루트 노드를 방문하고, 루트 노드의 왼쪽, 오른쪽 자식 노드를 방문하고, 아래로 내려가서 왼쪽 자식 노드부터 오른쪽까지 또 차례대로 방문하면 됨!



자세한 건 여기에

> [ChanBLOG](https://chanhuiseok.github.io/posts/ds-2/)

## 🌟 코드

```c
#include <stdio.h>
#include <stdlib.h>

#define MAX_QUEUE_SIZE 100

typedef struct _node{
	int data;
	struct _node * leftChild;
	struct _node * rightChild;
}node;
typedef node* treePointer;

treePointer Create(int data) {
	treePointer nd;
	nd = (treePointer)malloc(sizeof(node));
	nd->leftChild = NULL;
	nd->rightChild = NULL;
	nd->data = data;

	return nd;
}

int front = 0; int rear = 0; // 전역변수 선언
treePointer Queue[MAX_QUEUE_SIZE];

void Enqueue(treePointer ptr) {
	Queue[++rear] = ptr;
}

treePointer Dequeue() {
	return Queue[++front];
}

void levelOrder(treePointer ptr) {
	if (!ptr)
		return;
	
	Enqueue(ptr);  

	while (1) {
		ptr = Dequeue();
		if (ptr)
		{
			printf("%d ", ptr->data);

			if (ptr->leftChild)
				Enqueue(ptr->leftChild);
			if (ptr->rightChild)
				Enqueue(ptr->rightChild);
		}
		else
			break; 
	}
}

int main(void)
{
	/* 예시를 위한 트리 생성 */
	treePointer ONE = Create(1);
	treePointer TWO = Create(2);
	treePointer THREE = Create(3);
	treePointer FOUR = Create(4);
	treePointer FIVE = Create(5);

	ONE->leftChild = TWO;
	ONE->rightChild = THREE;
	TWO->leftChild = FOUR;
	TWO->rightChild = FIVE;

	printf("[구현 결과] level order : ");
	levelOrder(ONE);

	return 0;
}
```
