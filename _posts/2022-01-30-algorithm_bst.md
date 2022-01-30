---
title: "알고리즘. 이진 탐색 트리(Binary Search Tree) 알아보기"
categories:
  - Algorithm
tags:
  - 알고리즘
  - 이진 트리
  - 기초
---

## 🌟 이진 탐색 트리란?

이진 탐색 트리의 속성

1. 왼쪽 자식에는 부모 노드보다 작은 값이 들어 있음
2. 오른쪽 자식에는 부모 노드보다 큰 값이 들어 있음
3. 위 조건은 자식 트리에도 적용
4. 중복된 값은 허용하지 않음

## 🌟 검색

검색 과정

1. 검색 값을 루트와 비교
2. 검색 값이 루트보다 크면 오른쪽, 작으면 왼쪽 자식 노드로 감
3. 찾을 때까지 반복, 없으면 null 반환

```c++
struct node* search (struct node* root, int key)
{
// root값이 null이거나 key값과 같다면 종료한다.
  if (root == NULL || root->data == key)
    return root;

// key가 root->data 보다 작으면 왼쪽 서브트리로 재귀한다.
  if (root->data > key)
    return search(root->left, key)

// key가 root->data 보다 크면 오른쪽 서브트리로 재귀한다. 
  return search(root->left, key)
}
```



## 🌟 삽입

삽입 과정

1. 루트와 삽입할 값 비교, 크면 오른쪽 작으면 왼쪽 노드로
2. 리프 노드에 도달하면 크기 비교 후, 왼쪽이나 오른쪽에 삽입



```c++
struct node {
  int data;
  struct node *left, *right;
};

// 새로운 BST node 생성
struct node* newNode (int key) {
  struct node* temp = (struct *node)malloc(sizeof(struct node));
  temp->data = key;
  temp->left = NULL;
  temp->right = NULL;
  return temp;
}

struct node* insert(struct node *root, int key) {
  // 트리가 비어있다면 새로운 노드를 만든다.
  if (root == NULL)
    return newNode(key);

  // 루트값보다 크면 오른쪽으로 재귀하고, 작다면 왼쪽으로 재귀한다.
  if (key > root->data)
    root->right = insert(root->right, key);
  else if (key < root->data)
    root->left = insert(root->left, key); 
  // 같은 값을 가지고 있는 경우 삽입을 하지 않는다.(중복 불가)
  return root;
}
```



## 🌟 삭제

삭제 경우

1. 삭제할 노드가 리프 노드면 바로 삭제 가능
2. 자식이 하나 있는 노드를 삭제한다면 자식을 삭제할 노드의 부모와 연결
3. 삭제할 노드에 자식이 두 개 있다면 successor 노드를 찾아야함
   1. successor 노드는 오른쪽 서브 트리의 최소값 (inorder 순회에서 다음 노드를 말함)
   2. 삭제할 노드와 successor 노드의 위치를 바꿈
   3. 노드 삭제



```c++
struct node {
  int data;
  struct node *left, *right;
};

// 노드의 최소값을 가져오는 함수
struct node* minValueNode (struct node* node){
  struct node* current = node;
  
  while(current && current->left != NULL)
    current = current->left;

  return current;
}

struct node* deleteNode (struct node* root, int key) {
// base case  
  if(root == NULL)
    return root;
// 삭제할 노드를 찾는다.    
  if (key < root->data)
    root->left = deleteNode(root->left,key);

  else if (key > root->data)
    root->right = deleteNode(root->right, key);

// 삭제할 노드를 찾은 경우
  else {
    struct node* temp;
// 노드에 자식이 하나 이거나 없는 경우
    if (root->left == NULL) {
      temp = root->right;
      free(root);
      return temp;
    }
    else if (root->right == NULL) {
      temp = root->left;
      free(root);
      return temp;
    }

// 노드에 자식이 둘 있는 경우
// successor 노드를 찾는다.
    temp = minValueNode(root->right);
// successor 노드 키와 삭제할 노드 키를 바꾼다.
    root->key = temp->key;
// 노드를 삭제한다.
    root->right = deleteNode(root->right, temp->key);
  }
  return root;
}
```



> [yoongrammer](https://yoongrammer.tistory.com/71)
