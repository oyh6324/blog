---
title: "알고리즘. Prim 알고리즘 알아보기"
categories:
  - Algorithm
tags:
  - 알고리즘
  - 트리
  - 최소 신장 트리
---

## 🌟  Prim 알고리즘이란?

최소 신장 트리 구현에 사용됨!

시작 정점에서 정점을 추가하며 트리를 확장하는 알고리즘이다.



## 🌟 과정

1. 시작 노드만 최소 신장 트리(MST) 집합에 속함
2. 인접한 정점 중 가장 낮은 비용의 간선과 연결된 정점을 MST 집합에 넣는다. (사이클이 안 되게!)
3. 집합의 원소 개수가 그래프의 모든 정점의 개수가 될 때까지 반복



> 자세한 건 요기! [스터디룸](https://8iggy.tistory.com/159?category=997927)

## 🌟 코드

```python
from collections import defaultdict
import heapq
 
def mst():
    V, E = 6, 9
    edges = [[1, 2, 6], [1, 3, 3], [2, 3, 2], [2, 4, 5],
             [3, 4, 3], [3, 5, 4], [4, 5, 2], [4, 6, 3], [5, 6, 5]]
    graph = defaultdict(list)
    for srt, dst, weight in edges:
        graph[srt].append((dst, weight))
        graph[dst].append((srt, weight))
    mst_graph = [[0] * V for _ in range(V)]
    mst_nodes = [-1 for _ in range(V)]
    visited = [True for _ in range(V)]
    q = [(0, 1, 1)]
    while q:
        cost, node, prev = heapq.heappop(q)
        if visited[node - 1] is False:
            continue
        visited[node - 1] = False
        mst_graph[node - 1][prev - 1] = 1
        mst_graph[prev - 1][node - 1] = 1
        mst_nodes[node - 1] = cost
        for dst, weight in graph[node]:
            if visited[dst - 1] is True:
                heapq.heappush(q, (weight, dst, node))
    print(f'MST cost is {sum(mst_nodes)}')
    mst_graph[0][0] = 1
    for row in mst_graph:
        print(*row)
 
mst()
```
