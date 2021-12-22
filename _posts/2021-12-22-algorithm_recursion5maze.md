---
title: "알고리즘. Recusion(순환)-미로 찾기"
categories:
  - Algorithm
tags:
  - 알고리즘
  - 기초
  - 순환
---



## 🌟 미로 찾기

0은 벽이고 1은 길로 해서 미로 길을 탐색하는 함수를 순환 알고리즘으로 짜보기!



findPath는 현재 위치가 출구이거나, 이웃한 셀 중, 현재 위치를 지나지 않고 출구가지 가는 경로를 찾아야 한다.

## 🌟 코드

```java
public class Test {
	private static int N = 8; //미로범위
	private static int[][] maze = {
			{0, 0, 0, 0, 0, 0, 0, 1},
			{0, 1, 1, 1, 1, 1, 0, 1},
			{0, 0, 0, 1, 0, 0, 0, 1},
			{0, 1, 0, 0, 1, 1, 0, 0},
			{0, 1, 1, 1, 0, 0, 1, 1},
			{0, 1, 0, 0, 0, 1, 0, 1},
			{0, 0, 0, 1, 0, 0, 0, 1},
			{0, 1, 1, 1, 0, 1, 0, 0}
	};

	private static final int PATHWAY = 0;
	private static final int WALL = 1;
	private static final int BLOCKED = 2; //꽝
	private static final int PATH = 3; //방문했고 아직 꽝인지 모름

	public static void main(String[] args) {
		printMaze();
		findMazePath(0,0);
		printMaze();
	}

	public static boolean findMazePath (int x, int y) {
		if (x<0 || y<0 || x>=N || y>=N) { //미로 범위 넘어갔는지 체크
			return false;
		}else if(maze[x][y] != PATHWAY){ //방문했거나, 꽝, 또는 벽이면 검사할 필요 없지
			return false;
		}else if(x==N-1 && y==N-1){ //출구 일때
			maze[x][y] = PATH;
			return true;
		}else {
			maze[x][y] = PATH;
			if(findMazePath(x-1, y) || findMazePath(x, y+1) ||
					findMazePath(x+1, y) || findMazePath(x, y-1)) {
				return true;
			}
			maze[x][y] = BLOCKED; //꽝
			return false;
		}
	}

	public static void printMaze() {
		System.out.println("---------------------------------");
		for (int i = 0; i < maze.length; i++) {
			for (int j = 0; j < maze.length; j++) {
				System.out.print(maze[i][j] +" ");
			}
			System.out.println();
		}
		System.out.println("---------------------------------");
	}
```



음~~ 이해는 나중에.



> [사적인 저장공간](https://haileyjohj.github.io/algorithm/2020/07/25/algorithm_04/)

