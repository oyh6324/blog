---
title: "알고리즘. 기수 정렬(Radix Sort) 알아보기"
categories:
  - Algorithm
tags:
  - 알고리즘
  - 기초
  - 정렬
---

## 🌟 기수 정렬이란?

기수 정렬은 비교를 하지 않고 정렬을 하는 정렬 알고리즘이다. 기수란 수의 자릿수를 의미하고, 기수 정렬은 각각의 자릿수를 비교해서 버킷에 담고 순차적으로 빼준다. 여기서 버킷은 임시 저장 공간!



버킷은 0~9까지 존재하며, 각 숫자의 1의 자리에 해당된다. 51과 61이 있다면 1번 버킷에 들어간다는 뜻! 이렇게 1의 자리 버킷, 10의 자리 버킷을 정리해서 배열하면 된다.



기수 정렬은 같은 수가 있어도 순서가 섞이지 않는 안정 정렬이고, 매우 빠르다. 대신 자릿수가 없는 건 정렬할 수 없다. 그리고 버킷 공간이 필요함!



## 🌟 코드

```java
#include<iostream>
#include<cstdlib>
#include<ctime>
#include<queue>
 
#define MAX 100
using namespace std;
 
int Max_Value;
int Arr[MAX];
bool Flag[10001];
queue<int> Q[10];
 
void Print()
{
    cout << "####################################################################################################################" << endl;
    int Cnt = 0;
    for (int i = 0; i < MAX; i++)
    {
        printf("%6d ", Arr[i]);
        Cnt++;
        if (Cnt == 20)
        {
            Cnt = 0;
            cout << endl;
        }
    }
    cout << "####################################################################################################################" << endl;
    cout << endl;
}
 
void Radix_Sort()
{
    int Radix = 1;
    while (1)
    {
        if (Radix >= Max_Value) break;
        Radix = Radix * 10;
    }
    for (int i = 1; i < Radix; i = i * 10)
    {
        for (int j = 0; j < MAX; j++)
        {
            int K;
            if (Arr[j] < i) K = 0;
            else K = (Arr[j] / i) % 10;
            Q[K].push(Arr[j]);
        }
 
        int Idx = 0;
        for (int j = 0; j < 10; j++)
        {
            while (Q[j].empty() == 0)
            {
                Arr[Idx] = Q[j].front();
                Q[j].pop();
                Idx++;
            }
        }
    }
}
 
int main(void)
{
    srand((unsigned)time(NULL));
    for (int i = 0; i < MAX; )
    {
        Arr[i] = (rand() % 10000) + 1;
        if (Flag[Arr[i]] == false)
        {
            Flag[Arr[i]] = true;
            if (Max_Value < Arr[i]) Max_Value = Arr[i];
 
            i++;
        }
    }
    
    cout << "[ Initialize Array State ] " << endl;
    Print();
    Radix_Sort();
    cout << "[ After Sort Array State ] " << endl;
    Print();
 
    return 0;
}
```

## 🌟 시간 복잡도

숫자의 자릿수가 d라면 dN으로 매우 빠름!



> [[얍문's Coding World..](https://yabmoons.tistory.com/248)

