---
title: "알고리즘. 우선순위 큐(Priority Queue) 알아보기"
categories:
  - Algorithm
tags:
  - 알고리즘
  - 기초
---

## 🌟 우선순위 큐란?

일반적인 큐와 달리, 들어간 순서 상관없이 우선순위가 높은 데이터가 가장 먼저 나오는 자료구조다. 모든 데이터에 우선순위가 있고, 두 데이터의 우선순위가 같으면 들어간 순서에 따라 밖을 나오게 된다.



앞에서 봤듯이 구현 방법에는 힙도 있음.



## 🌟 코드

```c++
#include <iostream>
using namespace std;

#define MAX_ELEMENT 200      // heap array size

template <typename T>
struct Node{
private:
    int key;
    T data;
public:
    Node(){
        key = 0;
    }
    Node(int _key, T _data){
        key = _key;
        data = _data;
    }
    ~Node(){}

    // getter/setter
    int getKey(){
        return key;
    }
    void setKey(int _key){
        key = _key;
    }
    T getData(){
        return data;
    }
    void setData(T _data){
        data = _data;
    }
};

template <typename T>
class MaxHeap{
private:
    Node<T> node[MAX_ELEMENT];
    int size;   // heap 요소 개수
public:
    MaxHeap(){
        size = 0;
    }
    ~MaxHeap(){}

    // search node
    Node<T>& getParent(int index){
        return node[index/2];
    }
    Node<T>& getLeftChild(int index){
        return node[index*2];
    }
    Node<T>& getRightChild(int index){
        return node[index*2+1];
    }

    // 삽입
    void insert(int key, T data){
        if(isFull()){
            cout << "Heap is Full" << endl;
            return;
        }

        int index = ++size;     // 힙트리 마지막 노드의 다음 위치에서 시작

        // 힙트리를 거슬러 올라가며 부모 노드와 비교
        while(index != 1 && key > getParent(index).getKey()){
            node[index] = getParent(index);
            index /= 2;
        }

        // 최종 위치에 데이터 삽입
        node[index].setKey(key);
        node[index].setData(data);
    }

    // 삭제
    T remove(){
        if(isEmpty()){
            cout << "Heap is Empty" << endl;
            exit(EXIT_FAILURE);
        }

        Node<T> itemNode = node[1];         // root node (삭제 대상)
        Node<T> lastNode = node[size--];    // 힙트리의 마지막 노드
        int index = 1;                      // 마지막 노드의 index (root 부터 시작)

        // root 부터 내려가며 자식 노드와 비교
        while(index <= size){
            if(index*2 > size){             // leaf node인 경우 (자식 노드가 없는 경우)
                break;
            }else if(index*2 == size){      // 자식노드가 하나인 경우
                if(lastNode.getKey() < getLeftChild(index).getKey()){
                    node[index] = getLeftChild(index);
                    index *= 2;
                }else{
                    break;
                }
            }else{                          // 자식노드가 두개인 경우
                int leftChildKey = getLeftChild(index).getKey();
                int rightChildKey = getRightChild(index).getKey();

                // 둘 중 key가 더 큰 자식노드와 교환
                if(lastNode.getKey() < leftChildKey || lastNode.getKey() < rightChildKey){
                    node[index] = leftChildKey > rightChildKey ? getLeftChild(index) : getRightChild(index);
                    index = leftChildKey > rightChildKey ? index*2 : index*2+1;
                }else{
                    break;
                }
            }
        }
        node[index] = lastNode;     // 마지막 노드를 최종 위치에 저장
        return itemNode.getData();  // 삭제 노드의 data 반환
    }

    // 출력
    void display(){
        int level = 1;
        for(int i=1; i<= size; i++){
            if(i == level){
                cout << endl;
                level *= 2;
            }
            cout << node[i].getData() << "(" << node[i].getKey() << ")  ";
        }
        cout << '\n' << "-------------------------" << endl;
    }

    bool isEmpty(){
        return size == 0;
    }
    bool isFull(){
        return size == MAX_ELEMENT - 1;
    }

};

int main(){
    MaxHeap<int> priorityQueue;

    // 삽입
    priorityQueue.insert(10, 10);
    priorityQueue.insert(5, 5);
    priorityQueue.insert(30, 30);
    priorityQueue.insert(8, 8);
    priorityQueue.insert(9, 9);
    priorityQueue.insert(3, 3);
    priorityQueue.insert(7, 7);
    priorityQueue.display();

    // 삭제
    priorityQueue.remove();
    priorityQueue.display();
    priorityQueue.remove();
    priorityQueue.display();

    return 0;
}
```



> [Suyeon's Blog](https://suyeon96.tistory.com/31)
