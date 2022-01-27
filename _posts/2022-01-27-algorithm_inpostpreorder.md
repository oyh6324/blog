---
title: "알고리즘. 이진 트리와 순회 알아보기"
categories:
  - Algorithm
tags:
  - 알고리즘
  - 이진 트리
---

## 🌟 이진 트리 순회하기

이진 트리는 분할 정복 탐색 알고리즘으로 평소 보던 그 트리!



이진 트리를 순회하는 방법은 세 가지가 있는데

1. 전위 순회 (Preorder Traversal)
2. 중위 순회 (Inorder Traversal)
3.  후위 순회 (Posterorder Traversal)

이렇게 나뉜다.



### 전위 순회

전위 순회는 자식을 먼저 도는 순회로, 부모 노드에서 출발하여 자식이 있으면 왼쪽 자식, 그리고 오른쪽 자식도 있다면 오른쪽 자식까지 들린 다음 다시 부모 노드로 돌아가는 순회다.



### 중위 순회

중위 순회는 자식을 먼저 돌지만 오른쪽 자식을 우선하여 도는 순회다. 부모 노드에서 출발하여 오른쪽 자식 노드, 그리고 다시 부모 노드로 돌아온 다음에 왼쪽 자식 노드를 돈다.



### 후위 순회

후위 순회는 왼쪽 자식을 우선하여 도는 순회다. 왼쪽 자식 노드 다음에 오른쪽 자식, 그리고 부모 노드로 올라온다.



자세한 그림은 아래 블로그!

> [IT에 취.하.개.](https://hongku.tistory.com/160)

## 🌟 코드

```c
#include <stdio.h>

typedef struct TreeNode {
	int data;
	struct TreeNode* left, * right;
} TreeNode;
/*
		 15
	  4	     20
 	1	   16  25
*/
TreeNode n1 = { 1, NULL, NULL };
TreeNode n2 = { 4, &n1, NULL };
TreeNode n3 = { 16, NULL, NULL };
TreeNode n4 = { 25, NULL, NULL };
TreeNode n5 = { 20, &n3, &n4 };
TreeNode n6 = { 15, &n2, &n5 };
TreeNode* root = &n6;
// 전위 순회
void preorder(TreeNode* root) {
	if (root) {
		printf("%d-", root->data); 	
		preorder(root->left);	
		preorder(root->right);	
	}
}
// 중위 순회
void inorder(TreeNode* root) {
	if (root) {
		inorder(root->left);	
		printf("%d-", root->data); 
		inorder(root->right);	
	}
}
// 후위 순회
void postorder(TreeNode* root) {
	if (root) {
		postorder(root->left);	
		postorder(root->right);	
		printf("%d-", root->data);
	}
}
// 메인
int main(void)
{
	printf("중위 순회 : ");
	inorder(root);
	printf("\n");

	printf("전위 순회 : ");
	preorder(root);
	printf("\n");

	printf("후위 순회 : ");
	postorder(root);
	printf("\n");
	return 0;
}
/*
중위 순회 : 1-4-15-16-20-25-
전위 순회 : 15-4-1-20-16-25-
후위 순회 : 1-4-16-25-20-15-
*/
```



> [yjglab](https://yjg-lab.tistory.com/131)

