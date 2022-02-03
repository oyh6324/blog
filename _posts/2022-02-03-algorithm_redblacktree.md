---
title: "알고리즘. Red-Black Tree 알아보기"
categories:
  - Algorithm
tags:
  - 알고리즘
  - 이진 트리
---

## 🌟 Red-Black Tree란?

효율적인 탐색을 위해 이진 검색 트리의 height를 낮추는 방식의 트리다. 레드 블랙 트리는 다음 조건을 만족해야 함!

1. 루트 노드와 외부 노드는 Black 노드다.
2. Red 노드가 연속해서 올 수 없다.
3. 루트부터 외부 노드까지 가는 경로에서 Black 노드의 수는 같다.



## 🌟 삽입

1. 삽입할 노드는 레드라고 가정

2. 부모 노드가 블랙이면 문제 없이 삽입 가능, 레드면 경우의 수를 나눠 삽입함

   2-1. 부모 노드의 형제 노드가 똑같은 레드라면 부모 노드와 부모 노드의 형제 노드를 레드로 바꿈

   2-2. 부모 노드의 형제 노드가 블랙이라면 부모 노드가 자신의 부모 노드와 자리를 바꾸고, 삽입한 노드는 바뀐 부모 노드 밑에 붙임

   2-3. 부모의 형제 노드가 블랙이면서 삽입한 노드가 부모 노드의 오른쪽으로 갔을 때, 부모 노드와 삽입한 노드의 자리를 바꿈



> [레몬자몽](https://lemonlemon.tistory.com/135)



```c
// C program for Red-Black Tree insertion
#include<stdio.h>
#include<stdlib.h>
 
//A Red-Black tree node structure
struct node
{
    int data;     // for data part
    char color;  // for color property
 
    //links for left, right children and parent
    struct node *left, *right, *parent;
};
 
 
// Left Rotation
void LeftRotate(struct node **root,struct node *x)
{
    //y stored pointer of right child of x
    struct node *y = x->right;
 
    //store y's left subtree's pointer as x's right child
    x->right = y->left;
 
    //update parent pointer of x's right
    if (x->right != NULL)
        x->right->parent = x;
 
    //update y's parent pointer
    y->parent = x->parent;
 
    // if x's parent is null make y as root of tree
    if (x->parent == NULL)
        (*root) = y;
 
    // store y at the place of x
    else if (x == x->parent->left)
        x->parent->left = y;
    else    x->parent->right = y;
 
    // make x as left child of y
    y->left = x;
 
    //update parent pointer of x
    x->parent = y;
}
 
 
// Right Rotation (Similar to LeftRotate)
void rightRotate(struct node **root,struct node *y)
{
    struct node *x = y->left;
    y->left = x->right;
    if (x->right != NULL)
        x->right->parent = y;
    x->parent =y->parent;
    if (x->parent == NULL)
        (*root) = x;
    else if (y == y->parent->left)
        y->parent->left = x;
    else y->parent->right = x;
    x->right = y;
    y->parent = x;
}
 
// Utility function to fixup the Red-Black tree after standard BST insertion
void insertFixUp(struct node **root,struct node *z)
{
    // iterate until z is not the root and z's parent color is red
    while (z != *root && z->parent->color == 'R')
    {
        struct node *y;
 
        // Find uncle and store uncle in y
        if (z->parent == z->parent->parent->left)
            y = z->parent->parent->right;
        else
            y = z->parent->parent->left;
 
        // If uncle is RED, do following
        // (i)  Change color of parent and uncle as BLACK
        // (ii) Change color of grandparent as RED
        // (iii) Move z to grandparent
        if (y->color == 'R')
        {
            y->color = 'B';
            z->parent->color = 'B';
            z->parent->parent->color = 'R';
            z = z->parent->parent;
        }
 
        // Uncle is BLACK, there are four cases (LL, LR, RL and RR)
        else
        {
            // Left-Left (LL) case, do following
            // (i)  Swap color of parent and grandparent
            // (ii) Right Rotate Grandparent
            if (z->parent == z->parent->parent->left &&
                z == z->parent->left)
            {
                char ch = z->parent->color ;
                z->parent->color = z->parent->parent->color;
                z->parent->parent->color = ch;
                rightRotate(root,z->parent->parent);
            }
 
            // Left-Right (LR) case, do following
            // (i)  Swap color of current node  and grandparent
            // (ii) Left Rotate Parent
            // (iii) Right Rotate Grand Parent
            if (z->parent == z->parent->parent->left &&
                z == z->parent->right)
            {
                char ch = z->color ;
                z->color = z->parent->parent->color;
                z->parent->parent->color = ch;
                LeftRotate(root,z->parent);
                rightRotate(root,z->parent->parent);
            }
 
            // Right-Right (RR) case, do following
            // (i)  Swap color of parent and grandparent
            // (ii) Left Rotate Grandparent
            if (z->parent == z->parent->parent->right &&
                z == z->parent->right)
            {
                char ch = z->parent->color ;
                z->parent->color = z->parent->parent->color;
                z->parent->parent->color = ch;
                LeftRotate(root,z->parent->parent);
            }
 
            // Right-Left (RL) case, do following
            // (i)  Swap color of current node  and grandparent
            // (ii) Right Rotate Parent
            // (iii) Left Rotate Grand Parent
            if (z->parent == z->parent->parent->right &&
                z == z->parent->left)
            {
                char ch = z->color ;
                z->color = z->parent->parent->color;
                z->parent->parent->color = ch;
                rightRotate(root,z->parent);
                LeftRotate(root,z->parent->parent);
            }
        }
    }
    (*root)->color = 'B'; //keep root always black
}
 
// Utility function to insert newly node in RedBlack tree
void insert(struct node **root, int data)
{
    // Allocate memory for new node
    struct node *z = (struct node*)malloc(sizeof(struct node));
    z->data = data;
    z->left = z->right = z->parent = NULL;
 
     //if root is null make z as root
    if (*root == NULL)
    {
        z->color = 'B';
        (*root) = z;
    }
    else
    {
        struct node *y = NULL;
        struct node *x = (*root);
 
        // Follow standard BST insert steps to first insert the node
        while (x != NULL)
        {
            y = x;
            if (z->data < x->data)
                x = x->left;
            else
                x = x->right;
        }
        z->parent = y;
        if (z->data > y->data)
            y->right = z;
        else
            y->left = z;
        z->color = 'R';
 
        // call insertFixUp to fix reb-black tree's property if it
        // is voilated due to insertion.
        insertFixUp(root,z);
    }
}
 
// A utility function to traverse Red-Black tree in inorder fashion
void inorder(struct node *root)
{
    if (root == NULL)
        return;
    inorder(root->left);
    printf("%d ", root->data);
    inorder(root->right);
}
 
/* Drier program to test above function*/
int main()
{
    struct node *root = NULL;
    insert(&root,10);
    insert(&root,20);
    insert(&root,40);
    insert(&root,30);
    insert(&root,50);
    insert(&root,35);
    insert(&root,25);
    insert(&root,37);
    printf("inorder Traversal Is : ");
    inorder(root);
 
    return 0;
}
```



> [Bale의 Devlog](https://woongsin94.tistory.com/36)



## 🌟 삭제

삭제하는 노드가 레드면 바로 삭제 해도 되고, 블랙이면 자식 노드가 레드일 때 삭제할 노드 삭제하고 자식의 색을 블랙으로 바꾸면 된다.



하지만 다음과 같은 경우 주의!



1. 삭제한 노드의 부모 노드를 제외하고 다 블랙일 때, 부모 노드를 블랙으로 만들고 삭제한 노드의 형제 노드를 레드로 만든다.
2. 전부 다 블랙일 때, 삭제한 노드의 형제 노드를 레드로 만들어 놓고 부모 노드를 두고 다시 문제 해결해야 함
3. 형제 노드가 블랙이고 자식 중 하나가 레드일 때, 형제 노드가 부모 노드로 올라가고 부모 노드와 하나였던 레드 노드가 형제 노드의 자식이 됨!
4. 형제 노드가 레드고 나머지가 다 블랙일 때, 부모 노드를 삭제할 노드 위치에 두고 형제 노드가 부모 노드가 된 다음, 원래 부모 노드는 레드가 된다.





자세한 건 요기

> [레몬자몽](https://lemonlemon.tistory.com/135)

