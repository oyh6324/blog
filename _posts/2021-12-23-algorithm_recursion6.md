---
title: "알고리즘. Recusion(순환)-Counting Cells in a Blob"
categories:
  - Algorithm
tags:
  - 알고리즘
  - 기초
  - 순환
---



## 🌟 Counting Cells in a Blob

Binary 이미지의 셀을 세는 거!



각 픽셀은 background pixel(흰색)이거나 image pixel(파란색)이다. 서로 연결된 image pixel들의 집합을 blob이라고 한다. 상하좌우 대각선으로 연결된 것을 blob이라고 묶음!

![image-center]({{ site.url }}{{ site.baseurl }}/assets/images/algorithm/algorithm.pixel.jpg){: .align-center}



여기서 파란색이 image pixel! 저 뭉텅이들이 blob이다.



## 🌟 코드

1. 현재 픽셀이 image color가 아니면 0 반환
2. 인접한 8개의 픽셀에 순환을 돌림



```java
public class CountingCellsBlob {
  private static int BACKGROUND_COLOR = 0;
  private static int IMAGE_COLOR = 1;
  private static int ALREADY_COUNTED = 2;
  private static int N = 8;
  private static int[][] grid = {
      {1, 0, 0, 0, 0, 0, 0, 1},
      {0, 1, 1, 0, 0, 1, 0, 0},
      {1, 1, 0, 0, 1, 0, 1, 0},
      {0, 0, 0, 0, 0, 1, 0, 0},
      {0, 1, 0, 1, 0, 1, 0, 0},
      {0, 1, 0, 1, 0, 1, 0, 0},
      {1, 0, 0, 0, 1, 0, 0, 1},
      {0, 1, 1, 0, 0, 1, 1, 1},
  };

  public static int countCells(int x, int y) {
    if (x < 0 || x >= N || y < 0 || y >= N)
      return 0;
    else if (grid[x][y] != IMAGE_COLOR)
      return 0;
    else {
      grid[x][y] = ALREADY_COUNTED;
      return 1 + countCells(x, y + 1) + countCells(x + 1, y + 1)
          + countCells(x + 1, y) + countCells(x + 1, y - 1)
          + countCells(x, y - 1) + countCells(x - 1, y - 1)
          + countCells(x - 1, y) + countCells(x - 1, y + 1);
    }
  }

  public static void main(String[] args) {
    printGrid();
    int blobCount = countCells(3, 5);
    System.out.println();
    System.out.println("BlobCount : " + blobCount);
    printGrid();
  }

  private static void printGrid() {
    for (int x = 0; x < N; x++) {
      System.out.print("[");
      for (int y = 0; y < N; y++)
        System.out.print(grid[x][y] + ", ");
      System.out.println("]");
    }
  }
}

```



> [개발자의 기록 습관](https://ict-nroo.tistory.com/49)

