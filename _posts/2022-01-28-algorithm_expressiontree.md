---
title: "알고리즘. 식 트리(Expression Tree) 알아보기"
categories:
  - Algorithm
tags:
  - 알고리즘
  - 이진 트리
---

## 🌟 식 트리란?

자료 구조의 일종으로, 이진 트리를 통해 수식을 표현한 걸 식 트리라고 한다.



식 트리는 컴파일러나 인터프리터를 제작하는 데 응용됨. 컴파일러는 프로그래머가 작성한 코드를 분석해서 식 트리로 만든 후 이를 바탕으로 실행 파일을 만듬!



예시를 들어 `2 * 3 + 2 * 1`을 식 트리로 바꾸면

![image-center]({{ site.url }}{{ site.baseurl }}/assets/images/algorithm/algorithm.expressiontree.jpg){: .align-center}

이렇게 된다!



## 🌟 코드

```c++
// C++ program for expression tree
#include <bits/stdc++.h>
using namespace std;
class node {
public:
	char value;
	node* left;
	node* right;
	node* next = NULL;
	node(char c)
	{
		this->value = c;
		left = NULL;
		right = NULL;
	}
	node()
	{
		left = NULL;
		right = NULL;
	}
	friend class Stack;
	friend class expression_tree;
};
class Stack {
	node* head = NULL;

public:
	void push(node*);
	node* pop();
	friend class expression_tree;
};
class expression_tree {
public:
	void inorder(node* x)
	{
		// cout<<"Tree in InOrder Traversal is: "<<endl;
		if (x == NULL)
			return;
		else {
			inorder(x->left);
			cout << x->value << " ";
			inorder(x->right);
		}
	}
};

void Stack::push(node* x)
{
	if (head == NULL) {
		head = x;
	}
	// We are inserting here nodes at the top of the stack [following LIFO principle]
	else {
		x->next = head;
		head = x;
	}
}
node* Stack::pop()
{
	// Popping out the top most[ pointed with head] element
	node* p = head;
	head = head->next;
	return p;
}
int main()
{
	string s = "ABC*+D/";
	// If you wish take input from user:
	//cout << "Insert Postorder Expression: " << endl;
	//cin >> s;
	Stack e;
	expression_tree a;
	node *x, *y, *z;
	int l = s.length();
	for (int i = 0; i < l; i++) {
		// if read character is operator then popping two
		// other elements from stack and making a binary
		// tree
		if (s[i] == '+' || s[i] == '-' || s[i] == '*'
			|| s[i] == '/' || s[i] == '^') {
			z = new node(s[i]);
			x = e.pop();
			y = e.pop();
			z->left = y;
			z->right = x;
			e.push(z);
		}
		else {
			z = new node(s[i]);
			e.push(z);
		}
	}
	cout << " The Inorder Traversal of Expression Tree: ";
	a.inorder(z);
	return 0;
}
```



> [GeeksforGeeks](https://www.geeksforgeeks.org/expression-tree/)

