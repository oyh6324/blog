---
title: "알고리즘. 힙 정렬(Heap Sort) 알아보기"
categories:
  - Algorithm
tags:
  - 알고리즘
  - 기초
  - 정렬
---

## 🌟 힙 정렬이란?

힙은 자료 구조 중 하나로, 최솟값 또는 최댓값을 빠르게 찾기 위해 완전 이진트리로 만들어져 있다. 



힙 자료구조는 우선 순위 큐를 구현하는데 기반이 됐고, 여기서 배열을 힙으로 만들어서 정렬할 수도 있다. 하지만 메모리 낭비가 있어서 비효율적인 방법이다. 



힙 정렬은 부분 정렬을 할 때 좋고, 안정 정렬이 아니다.



우선 순위 큐를 사용하지 않고 만들려면, 배열을 힙 트리 상태로 만들어야 한다!

정렬을 진행하면 트리는 배열 순서 그대로 넣은 초기 상태에서 최댓값을 루트로 한 최대 힙 트리, 그리고 오름차순으로 정리된 정렬 트리로 바뀔 것이다. 자세한 건 참조 블로그 그림~!

## 🌟 코드

### 우선 순위 큐 사용

```java
import java.util.PriorityQueue;
 
public class test {
	public static void main(String[] args) {
    
		int[] arr = {3, 7, 5, 4, 2, 8};
		System.out.print(" 정렬 전 original 배열 : ");
		for(int val : arr) {
			System.out.print(val + " ");
		}
		
		PriorityQueue<Integer> heap = new PriorityQueue<Integer>();
		
		// 배열을 힙으로 만든다.
		for(int i = 0; i < arr.length; i++) {
			heap.add(arr[i]);
		}
		
		// 힙에서 우선순위가 가장 높은 원소(root노드)를 하나씩 뽑는다.
		for(int i = 0; i < arr.length; i++) {
			arr[i] = heap.poll();
		}
		
		
		System.out.print("\n 정렬 후 배열 : ");
		for(int val : arr) {
			System.out.print(val + " ");
		}
		
	}
}
```



### 코드

> Top-Down 방식

```java
public class HeapSort {
 
	public static void sort(int[] a) {
		sort(a, a.length);
	}
	
	private static void sort(int[] a, int size) {
 
		/*
		 * 부모노드와 heaify과정에서 음수가 발생하면 잘못 된 참조가 발생하기 때문에
		 * 원소가 1개이거나 0개일 경우는 정렬 할 필요가 없으므로 바로 함수를 종료한다.
		 */
		if(size < 2) {
			return;
		}
 
		/*
		 * left child node = index * 2 + 1
		 * right child node = index * 2 + 2
		 * parent node = (index - 1) / 2
		 */
		
		// 가장 마지막 요소의 부모 인덱스 
		int parentIdx = getParent(size - 1);
		
		// max heap
		for(int i = parentIdx; i >= 0; i--) {
			heapify(a, i, size - 1);
		}
 
		
		for(int i = size - 1; i > 0; i--) {
			
			/*
			 *  root인 0번째 인덱스와 i번째 인덱스의 값을 교환해준 뒤
			 *  0 ~ (i-1) 까지의 부분트리에 대해 max heap을 만족하도록
			 *  재구성한다.
			 */
			swap(a, 0, i);
			heapify(a, 0, i - 1);
		}
		
	}
	
	
	// 부모 인덱스를 얻는 함수
	private static int getParent(int child) {
	    return (child - 1) / 2;
	}
 
	// 두 인덱스의 원소를 교환하는 함수
	private static void swap(int[] a, int i, int j) {
		int temp = a[i];
		a[i] = a[j];
		a[j] = temp;
	}
	
	// 힙을 재구성 하는 함수
	private static void heapify(int[] a, int parentIdx, int lastIdx) {
		
		/*
		 * 현재 트리에서 부모 노드의 자식노드 인덱스를 각각 구해준다.
		 * 현재 부모 인덱스를 가장 큰 값을 갖고있다고 가정한다.
		 */
		int leftChildIdx = 2 * parentIdx + 1;
		int rightChildIdx = 2 * parentIdx + 2;
		int largestIdx = parentIdx;
		
		/*
		 *  left child node와 비교
		 *  
		 *  자식노드 인덱스가 트리의 크기를 넘어가지 않으면서
		 *  현재 가장 큰 인덱스보다 왼쪽 자식노드의 값이 더 클경우
		 *  가장 큰 인덱스를 가리키는 largestIdx를 왼쪽 자식노드인덱스로 바꿔준다.
		 *  
		 */
		if(leftChildIdx <= lastIdx && a[largestIdx] < a[leftChildIdx]) {
			largestIdx = leftChildIdx;
		}
		
		/*
		 *  left right node와 비교
		 *  
		 *  자식노드 인덱스가 트리의 크기를 넘어가지 않으면서
		 *  현재 가장 큰 인덱스보다 오른쪽 자식노드의 값이 더 클경우
		 *  가장 큰 인덱스를 가리키는 largestIdx를 오른쪽 자식노드인덱스로 바꿔준다.
		 *  
		 */
		if(rightChildIdx <= lastIdx && a[largestIdx] < a[rightChildIdx]) {
			largestIdx = rightChildIdx;
		}
		
		/*
		 * largestIdx 와 부모노드가 같지 않다는 것은
		 * 위 자식노드 비교 과정에서 현재 부모노드보다 큰 노드가 존재한다는 뜻이다.
		 * 그럴 경우 해당 자식 노드와 부모노드를 교환해주고,
		 * 교환 된 자식노드를 부모노드로 삼은 서브트리를 검사하도록 재귀 호출 한다.
		 */
		if(parentIdx != largestIdx) {
			swap(a, largestIdx, parentIdx);
			heapify(a, largestIdx, lastIdx);
		}
	}
}
```

> Bottom-Up 방식

```java
public class HeapSort {
 
	public static void sort(int[] a) {
		sort(a, a.length);
	}
	
	private static void sort(int[] a, int size) {
 
		/*
		 * 부모노드와 heaify과정에서 음수가 발생하면 잘못 된 참조가 발생하기 때문에
		 * 원소가 1개이거나 0개일 경우는 정렬 할 필요가 없으므로 바로 함수를 종료한다.
		 */
		if(size < 2) {
			return;
		}
 
		/*
		 * left child node = index * 2 + 1
		 * right child node = index * 2 + 2
		 * parent node = (index - 1) / 2
		 */
		
		// 가장 마지막 요소의 부모 인덱스 
		int parentIdx = getParent(size - 1);
		
		// max heap
		for(int i = parentIdx; i >= 0; i--) {
			heapify(a, i, size - 1);
		}
 
		
		for(int i = size - 1; i > 0; i--) {
			
			/*
			 *  root인 0번째 인덱스와 i번째 인덱스의 값을 교환해준 뒤
			 *  0 ~ (i-1) 까지의 부분트리에 대해 max heap을 만족하도록
			 *  재구성한다.
			 */
			swap(a, 0, i);
			heapify(a, 0, i - 1);
		}
		
	}
	
	
	// 부모 인덱스를 얻는 함수
	private static int getParent(int child) {
	    return (child - 1) / 2;
	}
 
	// 두 인덱스의 원소를 교환하는 함수
	private static void swap(int[] a, int i, int j) {
		int temp = a[i];
		a[i] = a[j];
		a[j] = temp;
	}
 
	
	private static void heapify(int[] a, int parentIdx, int lastIdx) {
		
	    int leftChildIdx;
	    int rightChildIdx;
	    int largestIdx;
 
	    /*
	     * 현재 부모 인덱스의 자식 노드 인덱스가 
	     * 마지막 인덱스를 넘지 않을 때 까지 반복한다.
	     * 
	     * 이 때 왼쪽 자식 노드를 기준으로 해야 한다.
	     * 오른쪽 자식 노드를 기준으로 범위를 검사하게 되면
	     * 마지막 부모 인덱스가 왼쪽 자식만 갖고 있을 경우
	     * 왼쪽 자식노드와는 비교 및 교환을 할 수 없기 때문이다. 
	     */
	    while((parentIdx * 2) + 1 <= lastIdx) {
	        leftChildIdx = (parentIdx * 2) + 1;
	        rightChildIdx = (parentIdx * 2) + 2;
	        largestIdx = parentIdx;
 
	        /*
	         * left child node와 비교 
	         * (범위는 while문에서 검사했으므로 별도 검사 필요 없음)
	         */
	        if (a[leftChildIdx] > a[largestIdx]) {
	            largestIdx = leftChildIdx;
	        }
 
	        /*
	         * right child node와 비교 
	         * right child node는 범위를 검사해주어야한다. 
	         */
	        if (rightChildIdx <= lastIdx && a[rightChildIdx] > a[largestIdx]) {
	            largestIdx = rightChildIdx;
	        }
 
	        /*
	         * 교환이 발생했을 경우 두 원소를 교체 한 후
	         * 교환이 된 자식노드를 부모 노드가 되도록 교체한다. 
	         */
	        if (largestIdx != parentIdx) {
	            swap(a, parentIdx, largestIdx);
	            parentIdx = largestIdx;
	        } 
	        else {
	            return;
	        }
	    }
	}
}
```



## 🌟 시간 복잡도

최선, 평균, 최악 모두 nlogn으로 똑같음!



> [Stranger's LAB](https://st-lab.tistory.com/225)

