---
title: "알고리즘. 허프만 코드(Huffman Code) 알아보기"
categories:
  - Algorithm
tags:
  - 알고리즘
  - 기초
  - 탐욕 알고리즘
---



## 🌟 허프만 코드란?

탐욕 알고리즘 중 하나로 입력 파일의 문자 빈도 수를 가지고 최소 힙을 사용해 파일을 압축할 수 있다. Unix에서 파일 압축에 사용되고, 이미지 파일이나 음악 파일을 압축할 때 서브 루틴으로도 사용됨!



## 🌟 압축 방법

1. 우선 압축할 파일에서 각 문자의 빈도 수를 계산한다.

2. 빈소 수를 우선 순위로 최소 힙을 구성한다.

   ex) A는 10, B는 5, C는 2...이렇게 정렬함

3. 빈도 수가 가장 작은 두 노드를 삭제

4. 삭제한 두 노드 중 가장 작은 노드는 왼쪽에, 큰 건 오른쪽에 삽입한 노드를 맨 뒤에 둔다

5. 노드가 하나 남을 때까지 반복!

6. 마지막 노드가 루트 노드가 됨



자세한 설명은 여기 !



> [kjh.log](https://velog.io/@junhok82/%ED%97%88%ED%94%84%EB%A7%8C-%EC%BD%94%EB%94%A9Huffman-coding)



## 🌟 코드

```java
public class Entry {
	private int frequency;	//  빈도 수
	private String word; 	// 노드의 문자 또는 내부노드의 합성된 문자열
	private Entry left;		// 왼쪽 자식
	private Entry right;	// 오른쪽 자식
	private String code;	// 허프만 코드
	public Entry (int newFreq, String newVal, Entry l, Entry r, String newCode) {
		frequency = newFreq;
		word = newVal;
		left = l;
		right = r;
		code = newCode;
	}
	public int getFrequency() {
		return frequency;
	}
	public void setFrequency(int frequency) {
		this.frequency = frequency;
	}
	public String getWord() {
		return word;
	}
	public void setWord(String word) {
		this.word = word;
	}
	public Entry getLeft() {
		return left;
	}
	public void setLeft(Entry left) {
		this.left = left;
	}
	public Entry getRight() {
		return right;
	}
	public void setRight(Entry right) {
		this.right = right;
	}
	public String getCode() {
		return code;
	}
	public void setCode(String code) {
		this.code = code;
	}
```

```java
    
public class Huffman {
	private Entry[] harray;	// a[0]은 사용안함 (트리이기때문)
	private int size;		// 힙 사이즈
	public Huffman(Entry[] heapArray, int initialSize) { 	// 생성자
		harray = heapArray;
		size = initialSize;
	}
	
	private boolean greater(int i, int j) {
		return harray[i].getFrequency() > harray[j].getFrequency();
	}
	
	public Entry createTree() {
		while(size() > 1) {
			Entry e1 = deleteMin();		// 힙에서 최소 빈도수를 가진 노드 제거
			Entry e2 = deleteMin();		// 힙에서 최소 빈도수를 가진 노드 제거
			
			Entry temp = new Entry(e1.getFrequency() + e2.getFrequency(),	// 빈도수 합
								e1.getWord() + e2.getWord(),				// 단어 이어붙이기
								e1,e2," ");						//	e1,e2가 각각 새로운 노드의 오른쪽,왼쪽 자식노드로 붙기
			insert(temp);	// 새 노드를 힙에 삽입
		}
		
		return deleteMin();	// 1개 남은 노드(루트 노드)를 힙에서 제거하며 리턴
	}
}
```

